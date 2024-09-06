## Foundry-Fund-Me

## Setup 
- forge init 
- forge install smartcontractkit/chainlink-brownie-contracts@1.2.0 --no-commit
- forge install Cyfrin/foundry-devops --no-commit
    - https://github.com/Cyfrin/foundry-devops
- 


## Commands 
```
// print console.log
$ forge test -vv

// run specific test 
$ forge test --match-test testMethodName -vv 

// Anvil spuns up but it will get a copy of the SEPOLIA_RPC_URL and it will simulate as if the 
// transactions are running on SEPOLIA Chain .
// Too many fork test runs on SEPOLIA can exceed the Limit of Alchemy calls.  
$ forge test --match-test testMethodName -vvv --fork-url $SEPOLIA_RPC_URL

$ forge test --fork-url $SEPOLIA_RPC_URL

$ forge test --fork-url $MAINNET_RPC_URL

$ forge test --match-test  testFundFailsWithoutEnoughEth

// With Stacktrace
$ forge test --match-test  testFundUpdatesFundedDataStructure -vvv

// Displays Code Coverage 
$ forge coverage --fork-url $SEPOLIA_RPC_URL

// Solidity language help , Can check small piece of Solidity code in terminal
$ chisel 

// Creates .gas-snapshot, estimates how much gas is used to run this test
$ forge snapshot --match-test testWithdrawFromMultipleFunders

// Creates snapshot for all the tests
$ forge snapshot

// Gives the storage layout json
// https://docs.soliditylang.org/en/latest/internals/layout_in_storage.html
$ forge inspect FundMe storageLayout

```

## Testing 
- Unit 
    - Testing a specific part of the code 
- Integration 
    - Testing how our code works with other parts of our code 
- Forked 
    - Testing our code on a simulated environment 
- Staging 
    - Testing our code on a real environment that is not prod

## References : 
- console logging 
    - https://book.getfoundry.sh/reference/forge-std/console-log
- Foundry Testing 
    - https://book.getfoundry.sh/cheatcodes/assertions
    - https://book.getfoundry.sh/cheatcodes/prank
    - https://book.getfoundry.sh/cheatcodes/deal
    - https://book.getfoundry.sh/reference/forge-std/hoax
    - https://book.getfoundry.sh/cheatcodes/tx-gas-price?highlight=txGasPrice#txgasprice
- Gas Optimisation 
    - https://docs.soliditylang.org/en/latest/internals/layout_in_storage.html

    

##
- private variables are more gas efficient than public 
- SLOAD ( Load word from Storage ) is very costly ( need 100 Gas) compared to MLOAD (Load word from Memory ) ( 3 Gas).
    - https://www.evm.codes/#55?fork=cancun
- 

Issues: 
    - failed to verify on etherscan 
        - https://github.com/foundry-rs/foundry/issues/2435
    - 

Questions : 
- pure 
    - function getSepoliaEthConfig() public pure returns (NetworkConfig memory)
- Style Guide 
    - Check on the style guide in cyfrin git repo 

