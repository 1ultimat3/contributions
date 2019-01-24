# Contributions
Ethermat's open sourced security audit results are captured in this repo. In case you are an open source project and interested to be audited, get in touch with us.

## Manual Analysis
Finding descriptions and corresponding issues are listed for each project.

### WallETH: Libre Android Ethereum wallet
* [Keystore Insufficiently Protected](https://github.com/walleth/walleth/issues/319)
* [Intent Crashes App (Denial of Service)](https://github.com/walleth/walleth/issues/318)

### Vyper: Fuzzing
* Different error handling issues (which can lead to DoS or information disclosure) have been identified:
 1. https://github.com/ethereum/vyper/issues/1184
 2. https://github.com/ethereum/vyper/issues/1185
 3. https://github.com/ethereum/vyper/issues/1186
 4. https://github.com/ethereum/vyper/issues/1188
 5. https://github.com/ethereum/vyper/issues/1189
 6. https://github.com/ethereum/vyper/issues/1190
 7. https://github.com/ethereum/vyper/issues/1191
 8. https://github.com/ethereum/vyper/issues/1192
 9. https://github.com/ethereum/vyper/issues/1193
 10. https://github.com/ethereum/vyper/issues/1194
 11. https://github.com/ethereum/vyper/issues/1195
 12. https://github.com/ethereum/vyper/issues/1196

### Solc: Fuzzing
* [Fuzzing solc using AFL & Libfuzzer](https://github.com/Ethermat/solc-fuzzing)

## Fuzzing Results (Galactuzz)

### Settings
For each target:
* External attacker (no owner or special privileges)
* 1,000,000 transaction limit
* Mixed whitebox- and blackbox-approach, data is generated based on:
  * historical chain data and transactions
  * smart contract (Solidity only)
  * common payloads
  * random and mutated data (zzuf)

### Overview
| Project  | #Vulns  | Coverage  |  Blocknumber | Address |
|---|---|---|---|---|
| [OasisDex (old)](https://github.com/Ethermat/contributions/tree/master/targets/oasisdex)  | 0  |  46 % | 6809217 | 0x14fbca95be7e99c15cc2996c6c9d841e54b79425 |
|  |   |   |  |  |  


### Which vulnerabilities are covered?
We refer to weaknesses according to the [Smart Contract Weakness Classification Registry](https://github.com/SmartContractSecurity/SWC-registry).
The following table lists weaknesses targeted by [Galactuzz](https://github.com/Ethermat/galactuzz) in terms of the Open Source contributions:

| SWC  | Description  | Support  |  
|---|---|---|
|100|	Function Default Visibility |Yes|
|101|	Integer Overflow and Underflow |Yes|
|102|	Outdated Compiler Version	|No|
|103|	Floating Pragma	|No|
|104|	Unchecked Call Return Value	| Only in audit|
|105|	Unprotected Ether Withdrawal	|Yes|
|106|	Unprotected SELFDESTRUCT Instruction	|Yes|
|107|	Reentrancy	|Yes|
|108|	State Variable Default Visibility	|Yes|
|109|	Uninitialized Storage Pointer	|Indirect support|
|110|	Assert Violation	|No|
|111|	Use of Deprecated Solidity Functions	|Indirect support|
|112|	Delegatecall to Untrusted Callee	|Yes|
|113|	DoS with Failed Call	|Only in audit|
|114|	Transaction Order Dependence	|Only in audit|
|115|	Authorization through tx.origin	|No|
|116|	Timestamp Dependence	|No|
|117|	Signature Malleability	|Yes|
|118|	Incorrect Constructor Name	|Yes|
|119|	Shadowing State Variables	|No|
|120|	Weak Sources of Randomness from Chain Attributes	|No|
|121|	Missing Protection against Signature Replay Attacks	|Yes|
|122|	Lack of Proper Signature Verification	|No|
|123|	Requirement Violation	|Only in audit|
|124|	Write to Arbitrary Storage Location	|Indirect support|
|125|	Incorrect Inheritance Order	|No|
|127|	Arbitrary Jump with Function Type Variable	|Indirect support|
|128|	DoS With Block Gas Limit	|Only in audit|
|129|	Typographical Error	|Indirect support|
