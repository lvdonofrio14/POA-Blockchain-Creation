# POA-Blockchain-Creation

## Step 1: Download necessary software 
  - Download MyCrypto and create and account
  - Download Geth and save files to a folder on your desktop 
![software downloads ](https://user-images.githubusercontent.com/78940231/123216435-89ae8c00-d497-11eb-9e3f-a68dd026a819.png)


## Step 2: Create Your nodes
  - Open up gitbash and locate your geth blockchain tools folder 
  - Run both of these commands to create your two nodes
      -> ./geth --datadir node1 account new
      -> ./geth --datadir node2 account new
   - Write down the public address keys for both of your nodes 
 ![creating nodes](https://user-images.githubusercontent.com/78940231/123216329-6683dc80-d497-11eb-8c49-311cd9cc279a.png)

 
## Creating your Gensis Block 
  - Enter the following commands in a new git bash window (be sure to access the correct folder first)
      -> ./puppeth
        -> select a name
        -> select option 2 (configure new genesis)
        -> select option 1 (create new genesis from scratch)
        -> select option 2 (proof of authority)
        -> hit eneter for default amount of seconds on block time 
        -> enter in both node address keys and then hit enter
        -> enter in both node address keys and hit enter to pre fund your account 
        -> enter "no" for precompile addresses 
        -> enter a random number for chain id (make sure to write it down)
        -> select option 2 (manage existing genesis)
        -> select option 2 (export genesis configurations), then hit eneter again 
        -> exit out using ctrl c function 
   ![puppeth scrennshot](https://user-images.githubusercontent.com/78940231/123215458-764ef100-d496-11eb-92ec-3996add561a3.png)
   
## Initialize your Nodes
  - In the same window as before enter the following (be sure to replace networkname with your created name) 
    -> ./geth --datadir node1 init networkname.json
    -> ./geth --datadir node2 init networkname.json
   ![datadir](https://user-images.githubusercontent.com/78940231/123216032-1c026000-d497-11eb-9a61-36f1cffea9ff.png)

   
 ##Begin Mining 
  - Enter the follwoing code in two seperate git bash windows (replace the sealer addresses with the ones you have written down) 
    -> ./geth --datadir node1 --unlock "SEALER_ONE_ADDRESS" --mine --rpc --allow-insecure-unlock
      -> copy down your enode address you will need it for node 2
    -> ./geth --datadir node2 --unlock "SEALER_TWO_ADDRESS" --mine --port 30304 --bootnodes "enode://SEALER_ONE_ENODE_ADDRESS@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock
  ![mine node 2](https://user-images.githubusercontent.com/78940231/123216170-3dfbe280-d497-11eb-979a-9f45021588f9.png)

  
## Add Custom Node to your Crypto Wallet 
  - Open mycrypto wallet
  - Click change network in the bottom left corner 
  - Select "add custom node"
    -> insert your blockchain name for both name fields
    -> insert your chain ID
    -> select ETH for currency 
    -> select custom for network
    -> use "http://127.0.0.1:8545" for URL 
   - Select "Save & Use Custom Node"
   - Connect to custom node
![custom node](https://user-images.githubusercontent.com/78940231/123215747-d2b21080-d496-11eb-9c12-d2febf10e631.png)


## Test Blockchain Transaction 
  - Select View & Send 
  - Select Keystore file
  - Click "select wallet file" and choose node 1 keystore file that you have created 
  - Select your node to address for address
  - Choose amount you would like to send 
  - Click Send Transaction
  - Click "check tx status" to see if your transaction went through 
![meta data](https://user-images.githubusercontent.com/78940231/123215524-8e267500-d496-11eb-8cb8-f0d7849cbc78.png)

## Congratulations you have configured your new blockcahin 

    
    
    
    
    
    
    
    
    
    
    
    
