## Foundry-Fund-Me


## Setup 
- forge init 
- forge install smartcontractkit/chainlink-brownie-contracts@1.2.0 --no-commit


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
    

##
- private variables are more gas efficient than public 
- 

Questions : 
- What is pure ? 
    - function getSepoliaEthConfig() public pure returns (NetworkConfig memory)

