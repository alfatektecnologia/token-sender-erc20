## SEPOLIA - TESTNET

### 0 - Creating the folder (Criando a pasta do projeto)

mkdir ~/.alfa-wallets
mkdir ~/.alfa-wallets/erc20test

#### 1.1 - Creating a new private key (Criando nova pvt key)

starkli signer keystore new ~/.alfa-wallets/erc20test/alfa_keystore.json

#### 1.2 - Connecting with the private key (Conectando com private key local)

starkli signer keystore from-key ~/.alfa-wallets/erc20test/alfa_keystore.json

#### 2.1 - Creating an account (Criando conta)

starkli account oz init ~/.alfa-wallets/erc20test/alfa_account.json

starkli account deploy ~/.alfa-wallets/erc20test/alfa_account.json

#### 2.2 - Connecting with your account (Conectando com conta local)

cat ~/.alfa-wallets/erc20test/alfa_account.json

starkli account fetch 0x04b98b51d721bb437d659855a86971a30a807416bad1ed5e730dda530b2ed9a1 --rpc https://starknet-sepolia.public.blastapi.io/rpc/v0_7 --output ~/.alfa-wallets/erc20test/alfa_account.json

#### 3 Declaring Alfa ERC20 Token (Declarando Alfa ERC20 Token)

starkli declare target/dev/token_sender_AlfaERC20.contract_class.json --rpc https://starknet-sepolia.public.blastapi.io/rpc/v0_7 --account ~/.alfa-wallets/erc20test/alfa_account.json --keystore ~/.alfa-wallets/erc20test/alfa_keystore.json

result: Sierra compiler version not specified. Attempting to automatically decide version to use...
Network detected: sepolia. Using the default compiler version for this network: 2.7.1. Use the --compiler-version flag to choose a different version.
Compiling Sierra class to CASM with compiler version 2.7.1...
CASM class hash: 0x02bb88d1d1ff525ed1456c7b8a96f735b98e0e679b0a7632a16408e8a37e9fe8
Contract declaration transaction: 0x05f98e0b4cf1bea9f360b15a854311fbe2544be24f8c4b0c6d80f02fa4f5e6fa
Waiting for transaction 0x05f98e0b4cf1bea9f360b15a854311fbe2544be24f8c4b0c6d80f02fa4f5e6fa to confirm...
Transaction not confirmed yet...
Transaction 0x05f98e0b4cf1bea9f360b15a854311fbe2544be24f8c4b0c6d80f02fa4f5e6fa confirmed
Class hash declared:
0x04034b3f62918e9a2915985cb7e3a27fa31a5ae6f259a566f8a0f1235dedfa56

#### 4 Deploying Alfa ERC20 Token

starkli deploy 0x04034b3f62918e9a2915985cb7e3a27fa31a5ae6f259a566f8a0f1235dedfa56 u256:1000000000 0x051557d6fbfbf98cc9a7f6454d084e2e94b44669f2e554fea76ad424bd651df6  
--rpc https://starknet-sepolia.public.blastapi.io/rpc/v0_7 --account ~/.alfa-wallets/erc20test/alfa_account.json --keystore ~/.alfa-wallets/erc20test/alfa_keystore.json

result: Deploying class 0x04034b3f62918e9a2915985cb7e3a27fa31a5ae6f259a566f8a0f1235dedfa56 with salt 0x0472f20ea71414fbe8ed4e3eb8209bc1cfc3c2c81d7bdeb652f9d3e645567273...
The contract will be deployed at address 0x06bf18a1351f59989e6861390fa76fc7ec99a8a8ea017f3936de1c0e1f39ca81
Contract deployment transaction: 0x05a28b00baec0bb4a7e460e824db24d019191022b87b7959f618568893201080
Contract deployed:
0x06bf18a1351f59989e6861390fa76fc7ec99a8a8ea017f3936de1c0e1f39ca81

#### 5 Checking Token´s total_supply (Checando Supply do Token)

starkli call 0x06bf18a1351f59989e6861390fa76fc7ec99a8a8ea017f3936de1c0e1f39ca81 total_supply --rpc https://starknet-sepolia.public.blastapi.io/rpc/v0_7

result: [
    "0x000000000000000000000000000000000000000000000000000000003b9aca00",
    "0x0000000000000000000000000000000000000000000000000000000000000000"
]


## MAINNET

#### 0 - Creating the project folder (Criando a pasta do projeto)
 
mkdir ~/.wallets
mkdir ~/.wallets/mainnet

#### 1.1 - Creating a new private key (Criando nova pvt key)

starkli signer keystore new ~/.wallets/mainnet/mainnet_ketstore.json

#### 1.2 - Connecting with the private key (Conectando com private key local)

starkli signer keystore from-key ~/.wallets/mainnet/mainnet_ketstore.json

#### 2.1 - Creating an account (Criando conta)

starkli account oz init --account ~/.wallets/mainnet/mainnet_account.json --keystore ~/.wallets/mainnet/mainnet_ketstore.json

starkli account deploy ~/.wallets/mainnet/mainnet_account --rpc https://free-rpc.nethermind.io/mainnet-juno --keystore ~/.wallets/mainnet/mainnet_keystore.json

#### 2.2 - Connecting with the created account (Conectando com conta local)

cat ~/.wallets/mainnet/mainnet_account.json

starkli account fetch 0x02700ce498c01ffc0af8426b465dcb3a615e408092a76fb0390d56c1b6c45c0e --output C:\Users\eoliveira/.wallets/mainnet/mainnet_account2.json --rpc https://free-rpc.nethermind.io/mainnet-juno

#### 3 Declaring Alfa ERC20 Token (Declarando Alfa ERC20 Token)

starkli declare ./target/dev/token_sender_AlfaERC20.contract_class.json --account C:\Users\eoliveira/.wallets/mainnet/mainnet_account2.json --rpc https://free-rpc.nethermind.io/mainnet-juno --keystore ~/.wallets/mainnet/mainnet_ketstore.json

result: class hash 0x02bb88d1d1ff525ed1456c7b8a96f735b98e0e679b0a7632a16408e8a37e9fe8
class hash declared: 0x04034b3f62918e9a2915985cb7e3a27fa31a5ae6f259a566f8a0f1235dedfa56

#### 4 Deploying Alfa ERC20 Token

starkli deploy 0x04034b3f62918e9a2915985cb7e3a27fa31a5ae6f259a566f8a0f1235dedfa56 u256:1000000000 0x02700ce498c01ffc0af8426b465dcb3a615e408092a76fb0390d56c1b6c45c0e --account C:\Users\eoliveira/.wallets/mainnet/mainnet_account2.json --rpc https://free-rpc.nethermind.io/mainnet-juno --keystore ~/.wallets/mainnet/mainnet_ketstore.json

result: Deploying class 0x04034b3f62918e9a2915985cb7e3a27fa31a5ae6f259a566f8a0f1235dedfa56 with salt 0x07afbeb60da1a3001f13d13a4f38087f0169fc38af09b071ed731dd961cded29...
The contract will be deployed at address 0x002ca95b283dd7069514102ca3ef66cc6b072be9ddd1f050123595931ac8d571
Contract deployment transaction: 0x04727f1a6f3cf3865c07edcb4fda7d9725f00fbbad2f757b1b03c8c6c0eacf7f
Contract deployed:
0x002ca95b283dd7069514102ca3ef66cc6b072be9ddd1f050123595931ac8d571

#### 5 Checking Token´s total_supply (Checando Supply do Token)

starkli call 0x002ca95b283dd7069514102ca3ef66cc6b072be9ddd1f050123595931ac8d571  total_supply --rpc https://free-rpc.nethermind.io/mainnet-juno

result: [
    "0x000000000000000000000000000000000000000000000000000000003b9c77b0",
    "0x0000000000000000000000000000000000000000000000000000000000000000"
]
