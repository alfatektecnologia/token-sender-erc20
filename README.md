#### starkli

## 0 - Criando Pasta

mkdir ~/.alfa-wallets
mkdir ~/.alfa-wallets/alfaERC20

## 1.1 - Criando nova pvt key

starkli signer keystore new ~/.alfa-wallets/alfaERC20/alfa_keystore.json

export STARKNET_KEYSTORE="~/.alfa-wallets/alfaERC20/alfa_keystore.json"

## 1.2 - Conectando com private key local

starkli signer keystore from-key ~/.alfa-wallets/alfaERC20/alfa_keystore.json

## 2.1 - Criando conta

starkli account oz init ~/.alfa-wallets/alfaERC20/alfa_account.json

starkli account deploy ~/.alfa-wallets/alfaERC20/alfa_account.json

## 2.2 - Conectando com conta local

cat ~/.alfa-wallets/alfaERC20/alfa_account.json

starkli account fetch 0x051557d6fbfbf98cc9a7f6454d084e2e94b44669f2e554fea76ad424bd651df6 --rpc https://starknet-sepolia.public.blastapi.io/rpc/v0_7 --output ~/.alfa-wallets/alfaERC20/alfa_account.json

## 3 Declarando Alfa ERC20 Token

starkli declare target/dev/token_sender_AlfaERC20.contract_class.json --rpc https://starknet-sepolia.public.blastapi.io/rpc/v0_7 --account ~/.alfa-wallets/alfaERC20/alfa_account.json --keystore ~/.alfa-wallets/alfaERC20/alfa_keystore.json

## 4 Deployand Alfa ERC20 Token

starkli deploy 0x051557d6fbfbf98cc9a7f6454d084e2e94b44669f2e554fea76ad424bd651df6 u256:1000000000 0x01121c686b331F5b9D19dAF25E56F023bee7F6AC129518154a05f3Dd2b1dC0Ba --rpc https://starknet-sepolia.public.blastapi.io/rpc/v0_7 --account ~/.alfa-wallets/alfaERC20/alfa_account.json --keystore ~/.alfa-wallets/alfaERC20/alfa_keystore.json

## 5 Checando Supply do Token

starkli call 0x051557d6fbfbf98cc9a7f6454d084e2e94b44669f2e554fea76ad424bd651df6 total_supply --rpc https://starknet-sepolia.public.blastapi.io/rpc/v0_7
