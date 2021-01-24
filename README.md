# Conflux internal contracts

[![npm](https://img.shields.io/npm/v/conflux-internal-contracts.svg)](https://www.npmjs.com/package/conflux-internal-contracts)
-----------------------

Conflux Network have three [internal contracts](https://github.com/Conflux-Chain/conflux-rust/tree/master/internal_contract): `AdminControl`, `SponsorWhitelistControl`, `Staking`. 
This is a npm module wrapper of the internal contracts, so you can easily get them throught npm.


### Install
```sh
$ npm install conflux-internal-contracts
```


### How to use
If you are using `truffle` or `cfxtruffle`, you can import internal contracts like below.
After importing you can initalize contract instance and invoke their methods.

```js
// SPDX-License-Identifier: MIT
// pragma solidity >= 0.5.0 < 0.7.0;
pragma solidity >= 0.5.0;
import "conflux-internal-contracts/contracts/AdminControl.sol";
import "conflux-internal-contracts/contracts/SponsorWhitelistControl.sol";
import "conflux-internal-contracts/contracts/Staking.sol";

contract YourContract {
  AdminControl adminControl = AdminControl(0x0888000000000000000000000000000000000000);
  SponsorWhitelistControl sponsor = SponsorWhitelistControl(0x0888000000000000000000000000000000000001);
  Staking staking = Staking(0x0888000000000000000000000000000000000002);
  
  constructor() public {
  }
}
```

### Internal Contract APIs

AdminControl:
* getAdmin(address contractAddr) view returns (address)
* setAdmin(address contractAddr, address newAdmin)
* destroy(address contractAddr)

SponsorWhitelistControl:
* getSponsorForGas(address contractAddr) view returns (address)
* getSponsoredBalanceForGas(address contractAddr) view returns (uint)
* getSponsoredGasFeeUpperBound(address contractAddr) view returns (uint)
* getSponsorForCollateral(address contractAddr) view returns (address)
* getSponsoredBalanceForCollateral(address contractAddr) view returns (uint)
* isWhitelisted(address contractAddr, address user) view returns (bool)
* isAllWhitelisted(address contractAddr) view returns (bool)
* addPrivilegeByAdmin(address contractAddr, address[] memory addresses)
* removePrivilegeByAdmin(address contractAddr, address[] memory addresses)
* setSponsorForGas(address contractAddr, uint upperBound) payable
* setSponsorForCollateral(address contractAddr) payable
* addPrivilege(address[] memory)
* removePrivilege(address[] memory)

Staking:
* getStakingBalance(address user) view returns (uint)
* getLockedStakingBalance(address user, uint blockNumber) view returns (uint)
* getVotePower(address user, uint blockNumber) view returns (uint)
* deposit(uint amount) external
* withdraw(uint amount) external
* voteLock(uint amount, uint unlockBlockNumber) external

For detail explanation of these APIs [check here](https://github.com/Conflux-Chain/conflux-rust/tree/master/internal_contract)