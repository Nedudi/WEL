# WEL

## https://ico.meetngreetme.com

Changing the way people travel.
A crowdsourced ecosystem for travel concierge service and lifestyle management.

--------------

## WelCoinCrowdsale.sol

This smart contract is written by *meetngreetme.com* based on Zepplin-solidity.

Zepplin-solidity is well audited and tested set of opensource contracts, avaliable here https://github.com/OpenZeppelin/zeppelin-solidity.

Zepplin-solidity is following the best practicas of writing smart contracts(https://github.com/ConsenSys/smart-contract-best-practices) as well as main solidity security considerations (http://solidity.readthedocs.io/en/latest/security-considerations.html

This smart contract is specially designed to provide a limited emision of ERC20 (https://github.com/ethereum/EIPs/blob/master/EIPS/eip-20-token-standard.md) standard tokens named **WEL** (**WEL Coin**) during pre-sale and main-sale periods of an ICO.

![](https://bitbucket.org/nedudi/WEL/raw/master/ico.png)

-------

## ERC20 WEL Token Contract (based on Zepplin-solidity MintableToken)

  - Contract name **WELToken**
  - Name **WEL Coin**
  - Symbol **WEL**
  - Decimals **18**

--------

## Crowdsale Contract

### Constructor

- *uint256* `preSaleStartTime`  start timestamp (in seconds) when pre-investments are allowed (inclusive)
- *uint256* `preSaleEndTime`    end timestamp (in seconds) when pre-investments are allowed (inclusive)
- *uint256* `preSaleWeiCap`     maximum amount of Wei that can be minted during pre-sale period
- *uint256* `mainSaleStartTime` start timestamp (in seconds) when main investments are allowed (inclusive)
- *uint256* `mainSaleEndTime`   end timestamp (in seconds) when main investments are allowed (inclusive)
- *uint256* `mainSaleWeiCap`    maximum amout of Wei that can be minted during main-sale period
- *uint256* `goal`              crowdsale soft cap
- *uint256* `rate`              how many token units a buyer gets per 1 wei
- *address* `wallet`            address of multisig, where the contract collects the ether
- *address* `tokenWallet`       address where the contract collects bounty tokens WEL tokens will be collected after crowdsale finalization

### 2 Ways to buy tokens

There are 2 ways that allow to buy tokens

1. **Call public method `buyTokens`** and pass the ether as well as the address off the wallet where you want to collect WEL tokens.
2. **Send ether to the contract address**. In this case WEL tokens will be added to the sender's address.

### Bonuses (example)

The contract has a `rate` of 2577 tokens per 1 ether.
You are sending to the contract the amount of 10 Ether during pre-sale period (expected 25% bonus).
You'll get `( 10 * 2577 ) * ((100 + 25) / 100) = 32212.5 WEL`

<!-- ### Finalisation

The contract creator are allowed to finalize sales with the public method `finaliseCrowdsale`.

*This method fixes the whole amount of minted tokens `token.totalSupply` as **90%** and mint **10%** more tokens, for the address `tokenWallet`. Then it forever stops minting of this token (means, stopping emission) -->

---------

## Important

The code of the contract as well as this readme.md will be updated few times before the beginning of the ICO.
We are focused on deep audit and testing, that may require minor changes.

-----------