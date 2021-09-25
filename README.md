![TGDAO](logo.png "TGDAO Token")

# TGDAO smart contracts

* _Standart_        : [BEP20](https://github.com/binance-chain/BEPs/blob/master/BEP20.md)
* _[Name](https://github.com/binance-chain/BEPs/blob/master/BEP20.md#5111-name)_            : TGDAO
* _[Ticker](https://github.com/binance-chain/BEPs/blob/master/BEP20.md#5112-symbol)_          : TGDAO
* _[Decimals](https://github.com/binance-chain/BEPs/blob/master/BEP20.md#5113-decimals)_        : 18
* _Emission_        : One-time, 30 000 000 tokens
* _Fiat dependency_ : No, Changable by owner
* _Token offers_    : 4
* _Token locks_     : Yes

## Smart contracts description

TGDAO smart-contract

### Contracts
1. _Configurator_
2. _CandaoToken_ - Token contract
3. _Sale_ - Sale contract

### Token distribution
1. _Cpmany Reserve_: 2 150 000 (Lock for 6 month - FreezeWallet)
2. _Launch tean_: 2 250 000 (Unlock 10% monthly after 3 months - FreezeWallet)
3. _Development team_: 250 000 000 (Unlock 2.5% monthly after 3 months - FreezeWallet)
4. _Liquidity_: 3 000 000
5. _Farming_: 600 000
6. _Marketing_ 4 500 000 (lock for 6 month)
7. _Advisors_ 1 500 000 (Unlock 10% monthly after 3 months - FreezeWallet)
8. _Seed round_ 3 750 000 (Unlock 10% monthly after 3 months - FreezeWallet)
9. _Funds round_ 3 500 000 (Unlock 10% monthly after 3 months - FreezeWallet)
11. _Public partners round_ 500 000
12. _Public sale_ 6 000 000

### How to work with this project
#### To start working with the contracts, please, follow theese steps for each contract:
1. Compile the contract using Remix with `enable optimization` flag and `compiler version` set to `0.8.0`.
2. Copy `.env.example` to `.env` and fill in the parameters.
2. Deploy the contract using deployment script:  
   ```truffle exec scripts/1_deploy_configurator.js --network NetworkName```  
   for example:  
   ```truffle exec scripts/1_deploy_configurator.js --network ropsten```
3. After deployment, run the following command with one or more contracts that you wish to verify:  
    ```truffle run verify SomeContractName@SomeContractAddress AnotherContractName@AnotherContractAddress --network NetworkName [--debug]```  
    for example:  
    ```truffle run verify  TGDAO@0xd4eE90e82FE10d37d028084f262fbC092E2aEF81 --network ropsten```  
    You can find all information about deployed smart contracts in the file `report.NetworkName.log`.
#### How to get constructor arguements generated during deployment
1. Browse to your contract on Etherscan and click on the hash of the transaction with which it was created.
2. On the top right, where it reads "Tools & utilities", click on the arrow to see more options and select "Parity Trace".
3. For the action pertaining the contract creation, click on "Click to see more" below to see the input/output.
4. Copy the content of the "Init" field and paste somewhere in text file.
5. Copy "bytecode" string from ContractName.json generated by truffle and place it near the string from the previous step.
6. The difference between theese two strings is your encoded constructor arguements.
7. Pass them to `truffle-verify-plugin` as paramter: `--forceConstructorArgs string:ABIEncodedArguments`

#### How to use frontend examples
1. `npx webpack build --config front/webpack.config.js`
2. Open `front/index.html` in browser.

### Wallets with BEP20 support
1. [MyEtherWallet](https://www.myetherwallet.com)
2. Parity
3. Mist/Ethereum wallet

EXODUS does not support BEP20, but provides the ability to export the private key to MyEtherWallet - http://support.exodus.io/article/128-how-do-i-receive-unsupported-erc20-tokens

## Main network configuration

### Contracts
* [Configurator](https://etherscan.io)
* [TGDAOToken](https://etherscan.io)
* [Sale](https://etherscan.io)

### Sale stages
Base price                          : 3000 TGDAO per BNB

#### Stage 1 - Funds Round 
* Bonus                             : 200% (price with bonus - 9000 TGDAO per BNB)
* HardCap                           : 3 500 000 TGDAO
* Start date                        : 15.10.2021
* End date                          : 25.10.2021

#### Stage 2 - Public Partners Round
* Bonus                             : 100% (price with bonus - 6000 TGDAO per BNB)
* HardCap                           : 500 000 TGDAO
* Start date                        : 25.10.2021
* End date                          : 03.11.2021

#### Stage 3 - Public Sale Round
* Bonus                             : 0% (price with bonus - 3000 TGDAO per BNB)
* HardCap                           : 6 000 000 TGDAO
* Start date                        : 03.11.2021
* End date                          : 10.11.2021

## Test network configuration (Kovan)
You can find kovan test log [here](docs/kovan.log.md)

