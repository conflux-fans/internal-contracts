## `SponsorWhitelistControl`






### `getSponsorForGas(address contractAddr) → address` (public)



get gas sponsor address of specific contract


### `getSponsoredBalanceForGas(address contractAddr) → uint256` (public)



get current Sponsored Balance for gas


### `getSponsoredGasFeeUpperBound(address contractAddr) → uint256` (public)



get current Sponsored Gas fee upper bound


### `getSponsorForCollateral(address contractAddr) → address` (public)



get collateral sponsor address


### `getSponsoredBalanceForCollateral(address contractAddr) → uint256` (public)



get current Sponsored Balance for collateral


### `isWhitelisted(address contractAddr, address user) → bool` (public)



check if a user is in a contract's whitelist


### `isAllWhitelisted(address contractAddr) → bool` (public)



check if all users are in a contract's whitelist


### `addPrivilegeByAdmin(address contractAddr, address[] addresses)` (public)



contract admin add user to whitelist


### `removePrivilegeByAdmin(address contractAddr, address[] addresses)` (public)



contract admin remove user from whitelist


### `setSponsorForGas(address contractAddr, uint256 upperBound)` (public)





### `setSponsorForCollateral(address contractAddr)` (public)





### `addPrivilege(address[])` (public)





### `removePrivilege(address[])` (public)






