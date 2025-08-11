# Xhash Vault Contract Document

## Main Vault Contract Addresses

1. mellow vault [0x3EE460eFfBDEb6d5e1E2345435263c19cd68975f](https://eth.blockscout.com/address/0x3EE460eFfBDEb6d5e1E2345435263c19cd68975f?tab=contract)
2. Symbiotic vault [0xD6A7933D2Ac0BAf297944d254Eb62A48dEa6E19b](https://eth.blockscout.com/address/0xD6A7933D2Ac0BAf297944d254Eb62A48dEa6E19b?tab=contract)
3. Withdrawal queue [0xa38Cd4aD4f81E71Aa86fafaE3FFf43cA7FB855F2](https://eth.blockscout.com/address/0xa38Cd4aD4f81E71Aa86fafaE3FFf43cA7FB855F2?tab=contract)
4. Deposit ETH [0xfD4a4922d1AFe70000Ce0Ec6806454e78256504e](https://eth.blockscout.com/address/0xfD4a4922d1AFe70000Ce0Ec6806454e78256504e?tab=read_write_contract)

## Main ABIs for webUI

### [mellow vault contract](https://eth.blockscout.com/address/0x3EE460eFfBDEb6d5e1E2345435263c19cd68975f?tab=contract)

1. balanceOf for mellow vault. Get account's balance.
   | name | type | description |
   | -------- | -------- | -------------------- |
   | account | address | user's address |
2. maxRedeem

   #### Returns the maximum amount of Vault shares that can be redeemed from the owner balance in the Vault

3. maxWithdraw

   #### Returns the maximum amount of the underlying asset that can be withdrawn from the owner balance in the Vault

4. withdraw. Withdraw account's asset or pending in the withdrawal queue
   | name | type | description |
   | -------- | ------- | ----------- |
   | assests | uint256 | withdraw amount as shares |
   | receiver | address | address to receive assets|
   | owner | address | assets's owner |

### [Deposit ETH contract](https://eth.blockscout.com/address/0xfD4a4922d1AFe70000Ce0Ec6806454e78256504e?tab=read_write_contract)

1. deposit. deposit eth to vault
   | name | type | description |
   | -------- | -------- | -------------------- |
   | depositToken| address| ETH, WETH, wstETH or stETH, token addresses showed in the contract read ABI|
   | amount | uint256 | deposit amount as wei |
   | vault | address | [mellow vault](https://eth.blockscout.com/address/0x3EE460eFfBDEb6d5e1E2345435263c19cd68975f?tab=contract) |
   | receiver | address | user's address |
   | referral | address | referrer's address, not activated at present |

### [Withdrawal queue](https://eth.blockscout.com/address/0xa38Cd4aD4f81E71Aa86fafaE3FFf43cA7FB855F2?tab=contract)

1. claimableAssetsOf.
   | name | type | description |
   | -------- | -------- | -------------------- |
   | account | address | user's address |

   #### Return claimableAssets The total amount of claimable collateral for the account.

2. getAccountData
   | name | type | description |
   | -------- | -------- | -------------------- |
   | account | address | user's address |
   #### Returns the data for a specific account
   | name              | type    | description                                                                  |
   | ----------------- | ------- | ---------------------------------------------------------------------------- |
   | sharesToClaimPrev | uint256 | The amount of shares to claim for the epoch before the last requested epoch. |
   | sharesToClaim     | uint256 | The amount of shares to claim for the last requested epoch                   |
   | claimableAssets   | uint256 | The total amount of assets that can be claimed                               |
   | claimEpoch        | uint256 | The most recent epoch requested for withdrawal                               |
3. getCurrentEpoch
   #### The current epoch of the Symbiotic Vault.
4. pendingAssetsOf
   #### The total amount of pending collateral for the account.
5. claim
   | name | type | description |
   | ----------------- | ------- | ---------------- |
   | account | uint256 | The address of the account requesting the withdrawal |
   | recipient | uint256 | The address of the recipient receiving the withdrawn assets |
   | claimableAssets | uint256 | The maximum amount of assets to withdraw |
   | maxAmount | uint256 | The most recent epoch requested for withdrawal |
   #### Return the actual amount of assets withdrawn

### [Symbiotic vault](https://eth.blockscout.com/address/0xD6A7933D2Ac0BAf297944d254Eb62A48dEa6E19b?tab=contract)

1. currentEpoch

   #### Get a current vault epoch

2. currentEpochStart
   #### Get a start of the current vault epoch as timestamp.
3. epochDuration

   #### Get a time point of the epoch duration set as seconds.

4. epochDurationInit
   #### Get a time point of the epoch duration set as timestamp.

## Mellow api

### Get mellow points by account address

[https://points.mellow.finance/v1/users/{0x1CB7B54AAB4283782b8aF70d07F88AD795c952E9}](https://points.mellow.finance/v1/users/0x1CB7B54AAB4283782b8aF70d07F88AD795c952E9)
