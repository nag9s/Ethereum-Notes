hadoop@hadoop-Inspiron-5547:~$ pwd

/home/hadoop

**hadoop@hadoop-Inspiron-5547:~$ mkdir helloworld**

**hadoop@hadoop-Inspiron-5547:~$ cd helloworld/**

**hadoop@hadoop-Inspiron-5547:~/helloworld$ pwd**

**/home/hadoop/helloworld**

**hadoop@hadoop-Inspiron-5547:~/helloworld$ truffle unbox webpack**

Downloading...

Unpacking...

Setting up...

Unbox successful. Sweet!

Commands:

Compile:              truffle compile

Migrate:              truffle migrate

Test contracts:       truffle test

Run linter:           npm run lint

Run dev server:       npm run dev

Build for production: npm run build

**hadoop@hadoop-Inspiron-5547:~/helloworld$ code .**

This opens visual code editor.

**add HelloWorld.sol under contracts.**

pragma solidity ^0.4.17;

contract HelloWorld {

```
function sayHello\(\) returns \(string\){

    return \(" Hello  World"\);

}
```

}

**then update 2\_deploy\_contracts.js to add hello world sol file.**

var ConvertLib = artifacts.require\("./ConvertLib.sol"\);

var MetaCoin = artifacts.require\("./MetaCoin.sol"\);

**var HelloWorld = artifacts.require\("./HelloWorld.sol"\);**

module.exports = function\(deployer\) {

deployer.deploy\(ConvertLib\);

deployer.link\(ConvertLib, MetaCoin\);

deployer.deploy\(MetaCoin\);

**  deployer.deploy\(HelloWorld\);**

};

**hadoop@hadoop-Inspiron-5547:~/helloworld$ truffle compile**

Compiling ./contracts/ConvertLib.sol...

Compiling ./contracts/HelloWorld.sol...

Compiling ./contracts/MetaCoin.sol...

Compiling ./contracts/Migrations.sol...

/home/hadoop/helloworld/contracts/HelloWorld.sol:4:5: Warning: No visibility specified. Defaulting to "public".

```
function sayHello\(\) returns \(string\){

^
```

Spanning multiple lines.

,/home/hadoop/helloworld/contracts/HelloWorld.sol:4:5: Warning: Function state mutability can be restricted to pure

```
function sayHello\(\) returns \(string\){

^
```

Spanning multiple lines.

**Writing artifacts to ./build/contracts**

The above step will create build directory with the helloworld contrac.t \( equivalent json file \) in it.

**open another tab and testrpc command ... this  opens ethereum testrpc session..**

**update truffle.js to include the following lines.**

// Allows us to use ES6 in our migrations and tests.

require\('babel-register'\)

module.exports = {

networks: {

```
development: {

  host: 'localhost',

  port: 8545,

  network\_id: '\*', // Match any network id

  gas: 4600000

}
```

}

}

**hadoop@hadoop-Inspiron-5547:~/helloworld$ truffle migrate**

Using network 'development'.

Running migration: 1\_initial\_migration.js

Deploying Migrations...

... 0x8b8eb0f6bb9d5873eed54a073e2e4b1065b8afe8efe10d07dcfb111e55f81140

Migrations: 0xd9d83c686f37df233df3e7e5350b71449e5f7cc0

Saving successful migration to network...

... 0xf14161b0d54e6f91713620a2d779211b30a2632cb2b6c1e8b80c71a45ab39cc2

Saving artifacts...

Running migration: 2\_deploy\_contracts.js

Deploying ConvertLib...

... 0xfcc74b199d59a3d232d1ecc175db91e576dabdc785e776e4f5b8f5c64179d5ac

ConvertLib: 0x7389e4373db3e761295f43ea2b8bb9193ce0ed5b

Linking ConvertLib to MetaCoin

Deploying MetaCoin...

... 0x80a9591826a7be5b8ff94bbbcab9b06d2894954d52b0fff7ccd5188076cdcdd3

MetaCoin: 0x3c67d7bac9ea8b6174e476ecd237d4f027559823

Deploying HelloWorld...

... 0xc612875a1b900735eafee3016f4ab65742f8784576110781801de688d82e9575

HelloWorld: 0xdb343f0ba44ecd6501fce23764fb705a91a776ae

Saving successful migration to network...

... 0xc2dc16834323335fde708b56162e5ccf35c4d696cbcf1228af1d2d3002d0a530

Saving artifacts...

In testrpc console \( which was opened before\) you will see something like

\( transaction might be contract creation or state updates\)

**Transaction: 0x8b8eb0f6bb9d5873eed54a073e2e4b1065b8afe8efe10d07dcfb111e55f81140**

**  Contract created: 0xd9d83c686f37df233df3e7e5350b71449e5f7cc0**

Gas usage: 269607

Block Number: 1

Block Time: Wed Nov 22 2017 09:28:56 GMT+0530 \(IST\)

eth\_newBlockFilter

eth\_getFilterChanges

eth\_getTransactionReceipt

eth\_getCode

eth\_uninstallFilter

eth\_sendTransaction

**Transaction: 0xf14161b0d54e6f91713620a2d779211b30a2632cb2b6c1e8b80c71a45ab39cc2**

**  Gas usage: 41981**

Block Number: 2

Block Time: Wed Nov 22 2017 09:28:56 GMT+0530 \(IST\)

eth\_getTransactionReceipt

eth\_accounts

net\_version

net\_version

eth\_sendTransaction

**Transaction: 0xfcc74b199d59a3d232d1ecc175db91e576dabdc785e776e4f5b8f5c64179d5ac**

**  Contract created: 0x7389e4373db3e761295f43ea2b8bb9193ce0ed5b**

Gas usage: 99726

Block Number: 3

Block Time: Wed Nov 22 2017 09:28:56 GMT+0530 \(IST\)

eth\_newBlockFilter

eth\_getFilterChanges

eth\_getTransactionReceipt

eth\_getCode

eth\_uninstallFilter

eth\_sendTransaction

**Transaction: 0x80a9591826a7be5b8ff94bbbcab9b06d2894954d52b0fff7ccd5188076cdcdd3**

**  Contract created: 0x3c67d7bac9ea8b6174e476ecd237d4f027559823**

Gas usage: 332608

Block Number: 4

Block Time: Wed Nov 22 2017 09:28:56 GMT+0530 \(IST\)

eth\_newBlockFilter

eth\_getFilterChanges

eth\_getTransactionReceipt

eth\_getCode

eth\_uninstallFilter

net\_version

net\_version

eth\_sendTransaction

**Transaction: 0xc612875a1b900735eafee3016f4ab65742f8784576110781801de688d82e9575**

**  Contract created: 0xdb343f0ba44ecd6501fce23764fb705a91a776ae**

Gas usage: 142596

Block Number: 5

Block Time: Wed Nov 22 2017 09:28:56 GMT+0530 \(IST\)

eth\_newBlockFilter

eth\_getFilterChanges

eth\_getTransactionReceipt

eth\_getCode

eth\_uninstallFilter

eth\_sendTransaction

Transaction: 0xc2dc16834323335fde708b56162e5ccf35c4d696cbcf1228af1d2d3002d0a530

Gas usage: 26981

Block Number: 6

Block Time: Wed Nov 22 2017 09:28:56 GMT+0530 \(IST\)

eth\_getTransactionReceipt

hadoopf@hadoop-Inspiron-5547:~/helloworld$ truffle console \( if this is opened anotherwindow , make sure this is invoked from the corresponding truffle project \)

truffle\(development\)&gt; HelloWorld

it will the information about HelloWorld contract including ABI

create the instance of HelloWorld contract to invoke the methods

truffle\(development\)&gt; HelloWorld.deployed\(\).then\(function\(instance\) {hello = instance; }\)ell

as helllo is instance to asyn calls , we should invoke a method called call\(\) to retrieve the contents

truffle\(development\)&gt; hello.sayHello.call\(\)

' Hello  World'

truffle\(development\)&gt; .exit

