#### SEPOLIA - TESTNET

## 0 - Criando Pasta

mkdir ~/.alfa-wallets
mkdir ~/.alfa-wallets/erc20test

## 1.1 - Criando nova pvt key

starkli signer keystore new ~/.alfa-wallets/erc20test/alfa_keystore.json

## 1.2 - Conectando com private key local

starkli signer keystore from-key ~/.alfa-wallets/erc20test/alfa_keystore.json

## 2.1 - Criando conta

starkli account oz init ~/.alfa-wallets/erc20test/alfa_account.json

starkli account deploy ~/.alfa-wallets/erc20test/alfa_account.json

## 2.2 - Conectando com conta local

cat ~/.alfa-wallets/erc20test/alfa_account.json

starkli account fetch 0x04b98b51d721bb437d659855a86971a30a807416bad1ed5e730dda530b2ed9a1 --rpc https://starknet-sepolia.public.blastapi.io/rpc/v0_7 --output ~/.alfa-wallets/erc20test/alfa_account.json

## 3 Declarando Alfa ERC20 Token

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

## 4 Deployand Alfa ERC20 Token

starkli deploy 0x04034b3f62918e9a2915985cb7e3a27fa31a5ae6f259a566f8a0f1235dedfa56 u256:1000000000 0x051557d6fbfbf98cc9a7f6454d084e2e94b44669f2e554fea76ad424bd651df6  
--rpc https://starknet-sepolia.public.blastapi.io/rpc/v0_7 --account ~/.alfa-wallets/erc20test/alfa_account.json --keystore ~/.alfa-wallets/erc20test/alfa_keystore.json

result: Deploying class 0x04034b3f62918e9a2915985cb7e3a27fa31a5ae6f259a566f8a0f1235dedfa56 with salt 0x0472f20ea71414fbe8ed4e3eb8209bc1cfc3c2c81d7bdeb652f9d3e645567273...
The contract will be deployed at address 0x06bf18a1351f59989e6861390fa76fc7ec99a8a8ea017f3936de1c0e1f39ca81
Contract deployment transaction: 0x05a28b00baec0bb4a7e460e824db24d019191022b87b7959f618568893201080
Contract deployed:
0x06bf18a1351f59989e6861390fa76fc7ec99a8a8ea017f3936de1c0e1f39ca81

## 5 Checando Supply do Token

starkli call 0x06bf18a1351f59989e6861390fa76fc7ec99a8a8ea017f3936de1c0e1f39ca81 total_supply --rpc https://starknet-sepolia.public.blastapi.io/rpc/v0_7

result: [
    "0x000000000000000000000000000000000000000000000000000000003b9aca00",
    "0x0000000000000000000000000000000000000000000000000000000000000000"
]


#### MAINNET

## 0 - Criando Pasta

mkdir ~/.alfa-wallets
mkdir ~/.alfa-wallets/erc20test

## 1.1 - Criando nova pvt key

starkli signer keystore new ~/.alfa-wallets/erc20test/alfa_keystore.json

## 1.2 - Conectando com private key local

starkli signer keystore from-key ~/.alfa-wallets/erc20test/alfa_keystore.json

## 2.1 - Criando conta

starkli account oz init ~/.alfa-wallets/erc20test/alfa_account.json

starkli account deploy ~/.alfa-wallets/erc20test/alfa_account.json

## 2.2 - Conectando com conta local

cat ~/.alfa-wallets/erc20test/alfa_account.json

starkli account fetch 0x04b98b51d721bb437d659855a86971a30a807416bad1ed5e730dda530b2ed9a1 --rpc https://starknet-sepolia.public.blastapi.io/rpc/v0_7 --output ~/.alfa-wallets/erc20test/alfa_account.json

## 3 Declarando Alfa ERC20 Token

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

## 4 Deployand Alfa ERC20 Token

starkli deploy 0x04034b3f62918e9a2915985cb7e3a27fa31a5ae6f259a566f8a0f1235dedfa56 u256:1000000000 0x051557d6fbfbf98cc9a7f6454d084e2e94b44669f2e554fea76ad424bd651df6  
--rpc https://starknet-sepolia.public.blastapi.io/rpc/v0_7 --account ~/.alfa-wallets/erc20test/alfa_account.json --keystore ~/.alfa-wallets/erc20test/alfa_keystore.json

result: Deploying class 0x04034b3f62918e9a2915985cb7e3a27fa31a5ae6f259a566f8a0f1235dedfa56 with salt 0x0472f20ea71414fbe8ed4e3eb8209bc1cfc3c2c81d7bdeb652f9d3e645567273...
The contract will be deployed at address 0x06bf18a1351f59989e6861390fa76fc7ec99a8a8ea017f3936de1c0e1f39ca81
Contract deployment transaction: 0x05a28b00baec0bb4a7e460e824db24d019191022b87b7959f618568893201080
Contract deployed:
0x06bf18a1351f59989e6861390fa76fc7ec99a8a8ea017f3936de1c0e1f39ca81

## 5 Checando Supply do Token

starkli call 0x06bf18a1351f59989e6861390fa76fc7ec99a8a8ea017f3936de1c0e1f39ca81 total_supply --rpc https://starknet-sepolia.public.blastapi.io/rpc/v0_7

result: [
    "0x000000000000000000000000000000000000000000000000000000003b9aca00",
    "0x0000000000000000000000000000000000000000000000000000000000000000"
]
