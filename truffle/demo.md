hadoop@hadoop-Inspiron-5547:~$ pwd

/home/hadoop

hadoop@hadoop-Inspiron-5547:~$ mkdir helloworld

hadoop@hadoop-Inspiron-5547:~$ cd helloworld/

hadoop@hadoop-Inspiron-5547:~/helloworld$ pwd

/home/hadoop/helloworld

hadoop@hadoop-Inspiron-5547:~/helloworld$ truffle init

Downloading...

Unpacking...

Setting up...

Unbox successful. Sweet!



Commands:



  Compile:        truffle compile

  Migrate:        truffle migrate

  Test contracts: truffle test

hadoop@hadoop-Inspiron-5547:~/helloworld$ code .

This opens visual code editor.

add HelloWorld.sol under contracts.

pragma solidity ^0.4.17;



contract HelloWorld {

    function sayHello\(\) returns \(string\){

        return \(" Hello  World"\);

    }

}

hadoop@hadoop-Inspiron-5547:~/helloworld$

