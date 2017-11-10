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

---

**          
**

\*\*--create an account  
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

INFO \[11-05\|11:03:51\] Generating DAG in progress               epoch=1 percentage=99 elapsed=3m31.469s

stop the miner as soon as the percentage is 99, so that mining will not consume the resources

1. miner.stop\(\) ; to stop the miner thing

browse for ethstats.net \(dig in the variables\)  
coinmarketcap.com  
remix.etereum.org \(to compile solidity code in browser\) - go to the details section on the right side to check the gas used for the contract  
check what is ABI : application basic interface

--to unlock the account1.  
personal.unlockaccount\(eth.accounts\[0\]\)  
then give ur password  
it returns true...this says ur account is unlocked and anything can be added into ur json

\*\*

**          
**

---

**          
**

**Web3 framework using nodejs**

**          
**

**Sudo apt-get install nodejs npm git**

**Npm i web3@0.20.1**

---

open web3

admin.startRPC\("127.0.0.1",8545,"\*","web3,net,eth,personal,admin"\)\)**          
**

open node js from a console

--- go to dir where web3 in installed, type nodejs, IT will open

up nodejs

var web3 = require\('web3'\);

var Web3 = new web3\(new web3.providers.HttpProvider\("\[\[\[[http://localhost:8545"\)\]\(http://localhost:8545"\)\)\]\(http://localhost:8545"\)\]\(http://localhost:8545"\)\)\)\]\(http://localhost:8545"\)\]\(http://localhost:8545"\)\)\]\(http://localhost:8545"\)\]\(http://localhost:8545"\)\)\)\)\](http://localhost:8545"%29]%28http://localhost:8545"%29%29]%28http://localhost:8545"%29]%28http://localhost:8545"%29%29%29]%28http://localhost:8545"%29]%28http://localhost:8545"%29%29]%28http://localhost:8545"%29]%28http://localhost:8545"%29%29%29%29\)\);

Web3

&gt; Web3.eth.accounts

&gt; Web3.eth.getBalance\(Web3.eth.accounts\[0\]\)

{ \[String: '1.1111821111111111111111111e+25'\] s: 1, e: 25, c: \[ 111118211111, 11111111111111 \] }

&gt; Web3.eth.getBalance\(Web3.eth.accounts\[0\]\)

{ \[String: '1.1111821111111111111111111e+25'\] s: 1, e: 25, c: \[ 111118211111, 11111111111111 \] }

**WEB3DEPLOY from details - deploying Remix IDE**

1. modify the initialSupply
2. make the gas to  gas: '470000
3. take the code from 'WEB3DEPLOY and paste in the ethreum cosole
4. this will create a contract
5. the contract will have mehtods  
   1. **To Pass the gas**

   transer\(eth.accounts\[1\],50, {from:eth.accounts\[0\], gas:'470000'}\)



