## Sūrya's Description Report

### Files Description Table


|  File Name  |  SHA-1 Hash  |
|-------------|--------------|
| ERC/ERC1400/ERC1400.sol | b5023882742c1c4e221e6310d5d1ae4e1ac68520 |
| ERC/ERC1410/ERC1410.sol | 2ff5b60fa291baa0bbe31d9e67ff5cc42f1570c6 |
| ERC/ERC1410/IERC1410.sol | 960310022fe4917c48db82fd5b9cb624234b3484 |
| ERC/ERC1594/IERC1594.sol | 779458669335a1ed0a2d37b5091060792d0ac657 |
| ERC/ERC1643/ERC1643.sol | 43c6f59e80662acdf6a445b7d3b77cba5311d1ed |
| ERC/ERC1643/IERC1643.sol | 62177ffceba689c20bfb3881211afd82bddb8ab3 |
| ERC/ERC1644/IERC1644.sol | f323ebd9915d769d67192746da0d5f440859133e |
| ERC/ERC20/IERC20.sol | 057595249d07e6068ac63a5203378f3f2743ab19 |
| InterestDistribution/IInterestDistribution.sol | 1e8957279b5fb1b9e2767189e96854190b9a41ff |
| InterestDistribution/iEstate/InterestDistribution.sol | 8ffb342464644056792125b2d2004bb9e3310837 |
| SecurityToken.sol | 4f7b854672fd6315290698fb27425ad46dd323ac |
| TokenVoting.sol | b28105766c3d4351c350a0e50025c30b3fc347db |
| access/ReentrancyGuard.sol | 1d49b154313d96845c125f4f867234cf48531382 |
| access/RoleBasedAccessControl.sol | f279cd2407a5c5d9e1c1460c688471f951e50ef0 |
| access/iEstate/PlatformProviderRbac.sol | fda1acf285b492d5f8ebfa85748de29ae4151a99 |
| math/KindMath.sol | 371a5172dc4c991cd8699f0458a849eba59800a5 |
| math/SafeMath.sol | 78878dc3bbedb82dffa9c909d31017c15c5638d4 |
| ownership/OwnableNonTransferable.sol | 8123aabe4c0bd1a6580446f5c3536eeba3ade739 |
| whitelists/FungibleWhitelist.sol | 37dbfc7274708ad86152eb627ea44fce15f3d31f |
| whitelists/IFungibleWhitelist.sol | 59440a4b8b8f5d4059509e2fc47c4783bb843de1 |
| whitelists/iEstate/DefaultSecurityTokenWhitelist.sol | 6cc2a2f93a7d345ed96747f91cc20c9acfd81121 |


### Contracts Description Table


|  Contract  |         Type        |       Bases      |                  |                 |
|:----------:|:-------------------:|:----------------:|:----------------:|:---------------:|
|     └      |  **Function Name**  |  **Visibility**  |  **Mutability**  |  **Modifiers**  |
||||||
| **ERC1400** | Implementation | IERC20, IERC1594, IERC1643, IERC1644, IERC1410, ERC1410 |||
| └ | \<Constructor\> | Public ❗️ | 🛑  | ERC1410 |
| └ | transfer | External ❗️ | 🛑  |NO❗️ |
| └ | transferFrom | External ❗️ | 🛑  |NO❗️ |
| └ | approve | External ❗️ | 🛑  |NO❗️ |
| └ | issue | External ❗️ | 🛑  | onlyIfIssuanceEnabled onlyIfNotPaused |
| └ | transferFromWithData | External ❗️ | 🛑  |NO❗️ |
| └ | transferWithData | External ❗️ | 🛑  |NO❗️ |
| └ | redeem | External ❗️ | 🛑  |NO❗️ |
| └ | redeemFrom | External ❗️ | 🛑  |NO❗️ |
| └ | allowance | External ❗️ |   |NO❗️ |
| └ | isIssuable | External ❗️ |   |NO❗️ |
| └ | canTransferFrom | External ❗️ |   |NO❗️ |
| └ | canTransfer | External ❗️ |   |NO❗️ |
| └ | name | Public ❗️ |   |NO❗️ |
| └ | symbol | Public ❗️ |   |NO❗️ |
| └ | decimals | Public ❗️ |   |NO❗️ |
| └ | _transferFromWithData | Private 🔐 | 🛑  | |
||||||
| **ERC1410** | Implementation | ReentrancyGuard, ERC1643, IERC1644, IERC1410 |||
| └ | \<Constructor\> | Public ❗️ | 🛑  | ERC1643 |
| └ | finalizeControllable | External ❗️ | 🛑  | onlyOwner onlyIfControllable |
| └ | authorizeOperator | External ❗️ | 🛑  | validOperatorAddressOnly |
| └ | revokeOperator | External ❗️ | 🛑  | validOperatorAddressOnly |
| └ | authorizeOperatorByPartition | External ❗️ | 🛑  | validOperatorAddressOnly |
| └ | revokeOperatorByPartition | External ❗️ | 🛑  | validOperatorAddressOnly |
| └ | issueByPartition | External ❗️ | 🛑  | onlyIfIssuanceEnabled |
| └ | redeemByPartition | External ❗️ | 🛑  |NO❗️ |
| └ | transferByPartition | External ❗️ | 🛑  |NO❗️ |
| └ | operatorTransferByPartition | External ❗️ | 🛑  |NO❗️ |
| └ | operatorRedeemByPartition | External ❗️ | 🛑  |NO❗️ |
| └ | controllerTransfer | External ❗️ | 🛑  | onlyIfControllable onlyController |
| └ | controllerRedeem | External ❗️ | 🛑  | onlyIfControllable onlyController |
| └ | isControllable | External ❗️ |   |NO❗️ |
| └ | balanceOf | External ❗️ |   |NO❗️ |
| └ | balanceOfByPartition | External ❗️ |   |NO❗️ |
| └ | partitionsOf | External ❗️ |   |NO❗️ |
| └ | totalSupply | External ❗️ |   |NO❗️ |
| └ | isOperator | External ❗️ |   |NO❗️ |
| └ | isOperatorForPartition | External ❗️ |   |NO❗️ |
| └ | canTransferByPartition | External ❗️ |   |NO❗️ |
| └ | isController | Public ❗️ |   |NO❗️ |
| └ | pause | Public ❗️ | 🛑  |NO❗️ |
| └ | unPause | Public ❗️ | 🛑  |NO❗️ |
| └ | isPaused | Public ❗️ |   |NO❗️ |
| └ | canPause | Public ❗️ |   |NO❗️ |
| └ | canIssue | Public ❗️ |   |NO❗️ |
| └ | canRedeem | Public ❗️ |   |NO❗️ |
| └ | canFreezeMinting | Public ❗️ |   |NO❗️ |
| └ | _isIssuable | Internal 🔒 |   | |
| └ | bytes32ToString | Internal 🔒 |   | |
| └ | toUpper | Internal 🔒 |   | |
| └ | _issueByPartition | Internal 🔒 | 🛑  | onlyIfIssuanceEnabled onlyIfNotPaused nonReentrant |
| └ | _isValidPartition | Internal 🔒 |   | |
| └ | _validateTokenTransfer | Internal 🔒 |   | |
| └ | _transferByPartition | Internal 🔒 | 🛑  | onlyIfNotPaused nonReentrant |
| └ | _redeemByPartition | Internal 🔒 | 🛑  | onlyIfNotPaused nonReentrant |
| └ | _operatorTransferByPartition | Internal 🔒 | 🛑  | onlyIfNotPaused |
| └ | _operatorRedeemByPartition | Internal 🔒 | 🛑  | onlyIfNotPaused |
| └ | _canTransferByPartition | Internal 🔒 |   | |
| └ | isSafeAddress | Internal 🔒 |   | |
| └ | _isControllable | Private 🔐 |   | |
| └ | _isController | Private 🔐 |   | |
| └ | _freezeMinting | Private 🔐 | 🛑  | onlyIfIssuanceEnabled |
| └ | _runBasicValidations | Private 🔐 |   | |
| └ | requireValidTransfer | Private 🔐 |   | |
| └ | _deletePartitionForHolder | Private 🔐 | 🛑  | |
||||||
| **IERC1410** | Interface |  |||
| └ | transferByPartition | External ❗️ | 🛑  |NO❗️ |
| └ | operatorTransferByPartition | External ❗️ | 🛑  |NO❗️ |
| └ | authorizeOperator | External ❗️ | 🛑  |NO❗️ |
| └ | revokeOperator | External ❗️ | 🛑  |NO❗️ |
| └ | authorizeOperatorByPartition | External ❗️ | 🛑  |NO❗️ |
| └ | revokeOperatorByPartition | External ❗️ | 🛑  |NO❗️ |
| └ | issueByPartition | External ❗️ | 🛑  |NO❗️ |
| └ | redeemByPartition | External ❗️ | 🛑  |NO❗️ |
| └ | operatorRedeemByPartition | External ❗️ | 🛑  |NO❗️ |
| └ | balanceOf | External ❗️ |   |NO❗️ |
| └ | balanceOfByPartition | External ❗️ |   |NO❗️ |
| └ | partitionsOf | External ❗️ |   |NO❗️ |
| └ | totalSupply | External ❗️ |   |NO❗️ |
| └ | isOperator | External ❗️ |   |NO❗️ |
| └ | isOperatorForPartition | External ❗️ |   |NO❗️ |
| └ | canTransferByPartition | External ❗️ |   |NO❗️ |
||||||
| **IERC1594** | Interface |  |||
| └ | transferWithData | External ❗️ | 🛑  |NO❗️ |
| └ | transferFromWithData | External ❗️ | 🛑  |NO❗️ |
| └ | redeem | External ❗️ | 🛑  |NO❗️ |
| └ | redeemFrom | External ❗️ | 🛑  |NO❗️ |
| └ | issue | External ❗️ | 🛑  |NO❗️ |
| └ | isIssuable | External ❗️ |   |NO❗️ |
| └ | canTransfer | External ❗️ |   |NO❗️ |
| └ | canTransferFrom | External ❗️ |   |NO❗️ |
||||||
| **ERC1643** | Implementation | IERC1643, OwnableNonTransferable |||
| └ | \<Constructor\> | Public ❗️ | 🛑  | OwnableNonTransferable |
| └ | setDocument | External ❗️ | 🛑  | onlyOwner |
| └ | removeDocument | External ❗️ | 🛑  | onlyOwner |
| └ | getDocument | External ❗️ |   |NO❗️ |
| └ | getAllDocuments | External ❗️ |   |NO❗️ |
||||||
| **IERC1643** | Interface |  |||
| └ | setDocument | External ❗️ | 🛑  |NO❗️ |
| └ | removeDocument | External ❗️ | 🛑  |NO❗️ |
| └ | getDocument | External ❗️ |   |NO❗️ |
| └ | getAllDocuments | External ❗️ |   |NO❗️ |
||||||
| **IERC1644** | Interface |  |||
| └ | controllerTransfer | External ❗️ | 🛑  |NO❗️ |
| └ | controllerRedeem | External ❗️ | 🛑  |NO❗️ |
| └ | isControllable | External ❗️ |   |NO❗️ |
||||||
| **IERC20** | Interface |  |||
| └ | transfer | External ❗️ | 🛑  |NO❗️ |
| └ | transferFrom | External ❗️ | 🛑  |NO❗️ |
| └ | approve | External ❗️ | 🛑  |NO❗️ |
| └ | totalSupply | External ❗️ |   |NO❗️ |
| └ | balanceOf | External ❗️ |   |NO❗️ |
| └ | allowance | External ❗️ |   |NO❗️ |
||||||
| **IInterestDistribution** | Interface |  |||
| └ | withdrawInterest | External ❗️ | 🛑  |NO❗️ |
| └ | setInterestPaymentforWithdrawals | External ❗️ | 🛑  |NO❗️ |
| └ | transferInterestPaymentByOwner | External ❗️ | 🛑  |NO❗️ |
| └ | adjustInterestPaymentforAnInvestor | External ❗️ | 🛑  |NO❗️ |
| └ | withdrawByOwner | External ❗️ | 🛑  |NO❗️ |
||||||
| **InterestDistribution** | Implementation | IInterestDistribution, OwnableNonTransferable |||
| └ | \<Constructor\> | Public ❗️ | 🛑  | OwnableNonTransferable |
| └ | \<Fallback\> | External ❗️ |  💵 |NO❗️ |
| └ | withdrawInterest | External ❗️ | 🛑  |NO❗️ |
| └ | setInterestPaymentforWithdrawals | External ❗️ | 🛑  |NO❗️ |
| └ | transferInterestPaymentByOwner | External ❗️ | 🛑  | onlyOwner |
| └ | adjustInterestPaymentforAnInvestor | External ❗️ | 🛑  |NO❗️ |
| └ | withdrawByOwner | External ❗️ | 🛑  | onlyOwner |
| └ | canSetOrTransferInterestPayment | Public ❗️ |   |NO❗️ |
| └ | makeInterestPaymentinEthers | Private 🔐 | 🛑  | |
| └ | makeInterestPaymentinTokens | Private 🔐 | 🛑  | |
| └ | validateInterestPaymentinEthers | Private 🔐 |   | |
| └ | validateInterestPaymentinTokens | Private 🔐 |   | |
||||||
| **SecurityToken** | Implementation | ERC1400 |||
| └ | \<Constructor\> | Public ❗️ | 🛑  | ERC1400 |
| └ | canPause | Public ❗️ |   |NO❗️ |
| └ | canIssue | Public ❗️ |   |NO❗️ |
| └ | canRedeem | Public ❗️ |   |NO❗️ |
| └ | canFreezeMinting | Public ❗️ |   |NO❗️ |
| └ | isWhitelisted | Public ❗️ |   |NO❗️ |
| └ | _validateTokenTransfer | Internal 🔒 |   | |
||||||
| **TokenVoting** | Implementation | ReentrancyGuard |||
| └ | createVote | Public ❗️ | 🛑  | nonReentrant controllableTokenOnly |
| └ | appendVoters | Public ❗️ | 🛑  | nonReentrant controllableTokenOnly |
| └ | submitVote | Public ❗️ | 🛑  | nonReentrant |
| └ | closeVoteManually | Public ❗️ | 🛑  | nonReentrant controllableTokenOnly |
| └ | votingIsClosed | Public ❗️ |   |NO❗️ |
| └ | requiresDeadline | Public ❗️ |   |NO❗️ |
| └ | getVotingOptions | Public ❗️ |   |NO❗️ |
| └ | getVote | Public ❗️ |   |NO❗️ |
| └ | getStats | Public ❗️ |   |NO❗️ |
| └ | getVotes | Public ❗️ |   |NO❗️ |
| └ | canRevealResults | Private 🔐 |   | |
| └ | isValidContext | Private 🔐 |   | |
| └ | isValidVotingOption | Private 🔐 |   | |
| └ | isValidVoter | Private 🔐 |   | |
| └ | hasVoted | Private 🔐 |   | |
||||||
| **ReentrancyGuard** | Implementation |  |||
| └ | \<Constructor\> | Internal 🔒 | 🛑  | |
||||||
| **RoleBasedAccessControl** | Implementation | OwnableNonTransferable |||
| └ | \<Constructor\> | Internal 🔒 | 🛑  | OwnableNonTransferable |
| └ | isSecurityOperator | Public ❗️ |   |NO❗️ |
| └ | addOperator | Public ❗️ | 🛑  | onlyContractOwner |
| └ | removeOperator | Public ❗️ | 🛑  | onlyContractOwner |
| └ | isMemberOf | Public ❗️ |   |NO❗️ |
| └ | addToRole | Public ❗️ | 🛑  | onlySecurityOperator |
| └ | removeFromRole | Public ❗️ | 🛑  | onlySecurityOperator |
||||||
| **PlatformProviderRbac** | Implementation | RoleBasedAccessControl |||
| └ | \<Constructor\> | Public ❗️ | 🛑  | RoleBasedAccessControl |
| └ | getAppIdentifier | Public ❗️ |   |NO❗️ |
| └ | addToLevel1 | Public ❗️ | 🛑  | onlySecurityOperator |
| └ | addToLevel2 | Public ❗️ | 🛑  | onlySecurityOperator |
| └ | removeFromLevel1 | Public ❗️ | 🛑  | onlySecurityOperator |
| └ | removeFromLevel2 | Public ❗️ | 🛑  | onlySecurityOperator |
| └ | isLevel1 | Public ❗️ |   |NO❗️ |
| └ | isLevel2 | Public ❗️ |   |NO❗️ |
||||||
| **KindMath** | Library |  |||
| └ | checkMul | Internal 🔒 |   | |
| └ | checkSub | Internal 🔒 |   | |
| └ | checkAdd | Internal 🔒 |   | |
||||||
| **SafeMath** | Library |  |||
| └ | mul | Internal 🔒 |   | |
| └ | div | Internal 🔒 |   | |
| └ | sub | Internal 🔒 |   | |
| └ | add | Internal 🔒 |   | |
| └ | mod | Internal 🔒 |   | |
||||||
| **OwnableNonTransferable** | Implementation |  |||
| └ | \<Constructor\> | Internal 🔒 | 🛑  | |
| └ | owner | Public ❗️ |   |NO❗️ |
| └ | isOwner | Public ❗️ |   |NO❗️ |
||||||
| **FungibleWhitelist** | Implementation | IFungibleWhitelist, OwnableNonTransferable |||
| └ | \<Constructor\> | Public ❗️ | 🛑  | OwnableNonTransferable |
| └ | addVerified | External ❗️ | 🛑  | onlyWhitelistOperator |
| └ | removeVerified | External ❗️ | 🛑  | onlyWhitelistOperator |
| └ | updateVerified | External ❗️ | 🛑  | onlyWhitelistOperator |
| └ | addVerifiedAsBulk | External ❗️ | 🛑  | onlyWhitelistOperator |
| └ | isWhitelistOperator | External ❗️ |   |NO❗️ |
| └ | hasHash | External ❗️ |   |NO❗️ |
| └ | isWhitelisted | External ❗️ |   |NO❗️ |
| └ | _addVerified | Private 🔐 | 🛑  | |
||||||
| **IFungibleWhitelist** | Interface |  |||
| └ | addVerified | External ❗️ | 🛑  |NO❗️ |
| └ | removeVerified | External ❗️ | 🛑  |NO❗️ |
| └ | updateVerified | External ❗️ | 🛑  |NO❗️ |
| └ | addVerifiedAsBulk | External ❗️ | 🛑  |NO❗️ |
| └ | isWhitelistOperator | External ❗️ |   |NO❗️ |
| └ | hasHash | External ❗️ |   |NO❗️ |
| └ | isWhitelisted | External ❗️ |   |NO❗️ |
||||||
| **DefaultSecurityTokenWhitelist** | Implementation | FungibleWhitelist |||
| └ | \<Constructor\> | Public ❗️ | 🛑  | FungibleWhitelist |
| └ | isWhitelistOperator | External ❗️ |   |NO❗️ |
| └ | isMemberOf | Public ❗️ |   |NO❗️ |


### Legend

|  Symbol  |  Meaning  |
|:--------:|-----------|
|    🛑    | Function can modify state |
|    💵    | Function is payable |
