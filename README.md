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

* [AdminControl api](./docs/AdminControl.md)
* [SponsorWhitelistControl api](./docs/SponsorWhitelistControl.md)
* [Staking api](./docs/Staking.md)

For detail explanation of these APIs [check here](https://github.com/Conflux-Chain/conflux-rust/tree/master/internal_contract)