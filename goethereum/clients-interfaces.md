Geth Clients provides three ways of interacting with the ethereum network.

1. IPC RPC \( default\)
2. JSON RPC  \(disabled by default \)
3. WS RPC \(disabled by default \)

![](/assets/clients1.png)IPC can only be used when Dapp \( which is accessing Ethereum \) and ethereum node colocated in the same machine. It can not be used for remote connection ...

In remote way of accessing, you could use json or web socket \(ws\) api

default apis avialble for jspn and ws rpc are eth, web3,net and others are disabled and can be enabled using options ..

![](/assets/client2.png)

#### JSON RPC

default 8545

to enable

geth  -rpc

#### WS RPC

![](/assets/clients3.png)![](/assets/client4.png)

