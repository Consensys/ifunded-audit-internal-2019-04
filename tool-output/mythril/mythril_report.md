```text
==== Multiple Calls in a Single Transaction ====
SWC ID: 113
Severity: Medium
Contract: TokenVoting
Function name: createVote(address,bytes32,bytes32,uint256,bytes32[],address[],uint256)
PC address: 1233
Estimated Gas Usage: 48311 - 270769
Multiple sends are executed in one transaction.
Consecutive calls are executed at the following bytecode offsets:
Offset: 4842
Offset: 5111
Try to isolate each external call into its own transaction, as external calls can fail accidentally or deliberately.

--------------------
In file: TokenVoting.sol:89

function createVote(
        SecurityToken securityToken,
        bytes32 partition,
        bytes32 topic,
        uint256 blockNumber,
        bytes32[] memory options,
        address[] memory targetAudience,
        uint256 durationInSeconds
        ) public
            nonReentrant
            controllableTokenOnly(securityToken, msg.sender) {

        address tokenAddress = address(securityToken);

        // Validate the voting options
        require(options.length > 1, "The voting options are required. You must define two voting options at least.");
        require(targetAudience.length > 0, "The target audience is required");

        // Make sure we are not debating the same thing over and over again (token + partition + topic + blocknumber)
        require(!isValidContext(tokenAddress, partition, topic, blockNumber), "The voting proposal already exists.");

        // Make sure the controller does not introduce an invalid voting option
        for (uint256 i = 0; i < options.length; i++) {
            require(options[i] != ZERO_BYTES32, "The voting option cannot be zero bytes");
            require(options[i] != EMPTY_VOTE, "The voting option cannot be an empty vote");
        }

        // Make sure the controller does not introduce duplicate addresses
        for (uint256 i = 0; i < targetAudience.length; i++) {
            require(_votes[tokenAddress][partition][topic][blockNumber][targetAudience[i]] == ZERO_BYTES32,
            "Duplicate voter. The voter already exists.");

            _votes[tokenAddress][partition][topic][blockNumber][targetAudience[i]] = EMPTY_VOTE;
        }

        // Set voters and options
        _votingOptions[tokenAddress][partition][topic][blockNumber] = options;
        _voters[tokenAddress][partition][topic][blockNumber] = targetAudience;

        // The caller will set the duration to zero if voting does not require a deadline
        uint256 closeTimeInUtc = (durationInSeconds > 0) ? now + durationInSeconds * 1 seconds : 0;

        // Enable voting
        _state[tokenAddress][partition][topic][blockNumber] = VOTING_OPEN;
        _votingDeadline[tokenAddress][partition][topic][blockNumber] = closeTimeInUtc;

        // Emit the event
        emit VoteCreated(tokenAddress, partition, topic, blockNumber, msg.sender, closeTimeInUtc);
    }

--------------------
```
