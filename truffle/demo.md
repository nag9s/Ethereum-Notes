hadoop@hadoop-Inspiron-5547:~$ pwd

/home/hadoop

**hadoop@hadoop-Inspiron-5547:~$ mkdir helloworld**

**hadoop@hadoop-Inspiron-5547:~$ cd helloworld/**

**hadoop@hadoop-Inspiron-5547:~/helloworld$ pwd**

**/home/hadoop/helloworld**

**hadoop@hadoop-Inspiron-5547:~/helloworld$ truffle init**

Downloading...

Unpacking...

Setting up...

Unbox successful. Sweet!

Commands:

Compile:        truffle compile

Migrate:        truffle migrate

Test contracts: truffle test

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

Compiling ./contracts/HelloWorld.sol...

Compiling ./contracts/Migrations.sol...

Compilation warnings encountered:

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

module.exports = {

networks: {

```
development: {

  host: "localhost",

  port: 8545,

  network\_id: "\*" // Match any network id

}
```

}

};

