

sudo apt-get install git nodejs npm

npm i web3@0.20.1^C

**Solidity, Solc, EVM**

**  
**

**Computation power, memory, storage**

**  
**

**Sidechain**

**  
**

**Public key and private key = digital signature**

**  
**

**Gas, gas price**

**  
**

**-------**

**  
**

**--create an account  
1 geth --datadir=data account new  
2 give the password  
3 what you get is the public key  
  
-- in genesis.json  
1.wirte a values in chainID : 77 \(do not give number between 1-20\)  
2. geth --datadir=data --networkid=77 init genesis.json  
  
--start networkid  
geth --datadir=data --networkid=77 --nodiscover console  
  
-- get the details of the block in the network  
eth.getBlock\('latest'\)  
2 eth \(type this to get all the functions\)  
3 web3 to look into more details  
  
to check the accounts which is created  
1 eth.accounts  
  
\(myetherallet.com \) got to keystore json file and put in the file in keystore folder in your local system and give the password  
to see the private key  
  
-- to run parallel consoles \(open new cmd terminal\)  
geth attach ipc:data/geth.ipc \(to opens up a console\)  
-- to check the ether value to that account  
1. eth.accounts  
2. eth.getBalance\(\[0\]\) to check the balance  
3. miner.start\(1\); \(give the value \(if value is not given system crashes\)\)  
4. miner.stop\(\) ; to stop the miner thing  
  
browse for ethstats.net \(dig in the variables\)  
coinmarketcap.com  
remix.etereum.org \(to compile solidity code in browser\) - go to the details section on the right side to check the gas used for the contract  
check what is ABI : application basic interface  
  
--to unlock the account1.  
personal.unlockaccount\(eth.accounts\[0\]\)  
then give ur password  
it returns true...this says ur account is unlocked and anything can be added into ur json  
  
**

**  
**

**-----------**

**  
**

**Web3 framework using nodejs**

**  
**

**Sudo apt-get install nodejs npm git**

**Npm i web3@0.20.1**





--------------------------------------

open web3

admin.startRPC\("127.0.0.1",8545,"\*","web3,net,eth,personal,admin"\)\)**  
**



open node js from a console

--- go to dir where web3 in installed, type nodejs, IT will open

up nodejs 

var web3 = require\('web3'\);

var Web3 = new web3\(new web3.providers.HttpProvider\("http://localhost:8545"\)\);

Web3

 

