# simple-faucet
## Usage
We are going to use the Truffle Console to interact with the smart contract. To launch the console run the following command: `truffle console` 

(dont mind version errors its fine)


<img width="573" alt="image" src="https://github.com/user-attachments/assets/0ee76c1f-749b-49ed-8e32-fe3aa5f194c1" />

> NOTE: > means we are currently working in Truffle Console

First, we need to establish the deployed meta-coin instance and the accounts created by Ganache:


` > let instance = await MetaCoin.deployed()`

` > let accounts = await web3.eth.getAccounts()`


<img width="573" alt="image" src="https://github.com/user-attachments/assets/6a36c64b-3d33-48b2-956e-3ee70a72fc76" />

We can check the meta-coin balance of the account which has deployed the contract:


`> let balance = await instance.getBalance(accounts[0])`

`> balance.toNumber()`


<img width="573" alt="image" src="https://github.com/user-attachments/assets/f6d67fa2-a022-41a2-8c3a-4c53f654e8fa" />

We can transfer some meta-coin from one account to another:


`> instance.sendCoin(accounts[1], 500)`


<img width="573" alt="image" src="https://github.com/user-attachments/assets/6c47ae7d-7606-4f53-beaa-b2de652a955d" />


Check the balance of the meta-coin receiving account:


`> let received = await instance.getBalance(accounts[1])`

`> received.toNumber()`


<img width="573" alt="image" src="https://github.com/user-attachments/assets/4dc73942-9673-4930-bf52-d7f6ac0b134d" />


Check the balance of the meta-coin sending account:


`> let newBalance = await instance.getBalance(accounts[0])`

`> newBalance.toNumber()`


<img width="573" alt="image" src="https://github.com/user-attachments/assets/e38aa41a-e72b-4c76-8b36-9ac4535be7d5" />

# License
This simple faucet is realead under [MIT License](https://github.com/arxshi/simple-faucet/blob/main/LICENSE)
