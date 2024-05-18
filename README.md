<div align="Center">
<h1>Initia Node</h1>

</div>

# Official Links
### [Official Document](https://docs.initia.xyz/run-initia-node/running-initia-node)
### [Initia Official Discord](https://discord.gg/initia)
### [Initia Faucet](https://faucet.testnet.initia.xyz)

# Explorer
### [Explorer](https://scan.testnet.initia.xyz/initiation-1)

## Minimum Requirements 
- 4 CPU cores
- At least 1TB of SSD disk storage
- At least 16GB of memory (RAM)
- At least 100 Mbps Bandwidth


## Update Packages
```
sudo apt update && sudo apt upgrade -y
```

## Install Dependencies
```
sudo apt install curl tar wget clang pkg-config libssl-dev jq build-essential bsdmainutils git make ncdu gcc git jq chrony liblz4-tool -y
```
## Install Golang
```
cd $HOME && \
ver="1.22.0" && \
wget "https://golang.org/dl/go$ver.linux-amd64.tar.gz" && \
sudo rm -rf /usr/local/go && \
sudo tar -C /usr/local -xzf "go$ver.linux-amd64.tar.gz" && \
rm "go$ver.linux-amd64.tar.gz" && \
echo "export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin" >> ~/.bash_profile && \
source ~/.bash_profile && \
go version
```
## Build with Binaries
```
cd $HOME
rm -rf initia/
git clone https://github.com/initia-labs/initia.git
cd initia
git checkout v0.2.14
make install
```

# Init the node
```
initiad init YOUR_MONIKER_NAME  --chain-id initiation-1
```

## Download Genesis
```
curl -Ls https://initia.s3.ap-southeast-1.amazonaws.com/initiation-1/genesis.json > \ $HOME/.initia/config/genesis.json
```
## Set Gas Fee
```
sed -i -e "s|^minimum-gas-prices *=.*|minimum-gas-prices = \"0.15uinit,0.01uusdc\"|" $HOME/.initia/config/app.toml
```

## Set Seed and Peer 
```
PEERS="5cf0f056fcff9a2a5bad1b3acbae7eec3e425979@158.220.90.188:26656, 1d34feab3765f17801ac6053d101b1671e6ad8b1@31.220.72.104:26656, 66abd758f6971eb8227fc54d11cb56ca1ca280e6@65.109.113.251:13656, e6e5d053f05427e2681741bb38ff26983b69ae15@38.242.155.134:26656, ec4adff20cbb1956b19a6776e52cdf85e99b18a1@192.145.37.94:26656, 5c2a752c9b1952dbed075c56c600c3a79b58c395@195.3.221.9:26686, 15d771bbab00194ce62e70526423961ade0d7083@152.42.220.211:26656, e2e51b1c0ade2eb2e515d71e3f791b41fd5923c4@40.160.7.110:26656, 5f934bd7a9d60919ee67968d72405573b7b14ed0@65.21.202.124:29656, 3582b6a9c5973b3d31aac468711c3a03f0ec8495@38.242.148.123:26656, 55e9720ee1c1c8f42ef9effb9ca4dd1d5e8cde5a@169.197.131.253:15656, 576569a43bb8d5f3d58ff8aa52c6906d576c211e@38.242.221.49:15656, 526d8c79450eb441668205f230aa17f43d496ba5@5.9.105.248:50756, 9161de16ea2dd3f31a930f8bc5643a551451317b@109.123.244.68:46656, 1677252f64d728aa9598cb7365f74af7c862d9df@65.109.57.221:25756, 23da888f82a785d5745b67eaca1c70597828e8b2@65.109.83.40:25756, c8a06a8e4f42464f9243fd1490967407a2ff3a81@152.42.194.121:26656, 943100db8ad47cedb4cd3f814e24407e298eb112@213.199.37.60:15656, 2284949b8fd2fdeffcc76d5ce94a3812a6e2a6b1@37.60.246.110:53456, 250be6a473b4482d99c71032f005f161b5c70902@193.163.205.50:26656, ca1724a769b0d8df5eefe6d5c3be398f3b0e50d5@65.108.58.227:26656, 10514d193490b990c79faf3be434039a6a1ca615@37.27.46.61:26656, d6403dadd23d54f0801efc9b9ebe64703deb92d7@154.38.162.231:26656, 9e8c308fa953c4eb06ff2e24030bd662ce901ee8@143.198.92.245:26656, 73c2832ede1227cf0b4da4b127073deb77a7b8ad@65.108.129.239:26656, fbe630336f54f3a0a6a84410b53e043d2671b134@167.71.57.255:26656, dc9112cb4b21b7512165ac86f58c0ab863efd858@80.240.31.114:26656, 39997f40cb4f7808011589086df79cfbfcb480b8@185.239.209.222:26656, 1e9d62a962e7d22042e11b913eac7b638e9383f1@31.220.75.114:26656, d1e84617cde778c0127b26570d1f949a36c5f426@139.162.50.162:26656, 12e54b686bc35d1884d05571b1e43427c2ecf944@15.164.118.189:26656, d17d2d48b4741b21b16cba7aa5a0496151dec2e3@65.109.37.125:26656, 3194727c8195c5819093b677a982be0d512fa033@13.209.148.118:26656, b366c8e689d41e05c651e9a2f5474a82196f04a1@5.252.53.3:15656, ab65fe0c814fa4a837bbcf9bf944a2e8d9eacfb4@195.3.221.44:33756, 5af4d6f42f02959e43aa021dfd8a361fc1d636da@95.179.248.55:26656, 54ba48626efb9854faf954fb7c7ca5277aca740c@38.242.138.42:26656, e007ba24a3f845442e555f18bd7a4c43c0d82663@37.60.249.152:26656, 915e9775c93112ab3362d2b7c91c493f56645741@65.109.106.113:26656, 04f0d493cb02a43d85b4fcd4bafd171500a433a0@162.55.27.107:46656, 5910b88302c0528a2464ecde549f84c88cd3c949@195.26.241.57:26656, 3b944bcae9db0b88d8419adde8e26188a6a5ef5d@65.109.59.22:25756, a867d1eda5af3225aaef0e98f7bcaa352a1e1f5b@38.242.138.70:26656, 2da714585d9207ace5897d7a8506b78074cc5af5@65.108.70.106:26606, 600d189ba0dc26fddf448a3c67a2c41980f7e43e@185.252.234.22:26656, 6cdaa2bafee744e749f09cc21b6f9d8df00f938e@185.197.251.183:26656, 9f356fd9a77253f7b13e3c500358bdc4318a41d5@38.242.149.83:26656, c8814cfb9e5a6837396400c644b1a65473fb6af7@77.90.8.70:26656, 90c1c1ee7942aef1930b272a02783fee75edaf39@88.99.61.53:37656, ec90788adebfae73ab7f790426df9ab7db2ecb1f@37.60.251.209:33756, 3dde66af98916c3e2c51efe313d566c4a969b86c@84.247.170.106:26656, af3e7211d71a070748dd2e1157cbdaa8f4a8e5a4@194.163.137.223:26656, 233dc308e77d27408c8ebcfa1e335260ecaed07c@43.128.147.198:26656, 02dd64b0a1dc5b1681b796a121ab71870330ca80@43.128.136.171:26656, 1e303d1015534d10ebd70bb50e461d1ce9732a2b@84.46.246.149:26656, 0c51b92a123bd4310dfe964a969106458e45b713@63.250.54.71:26656, e213fcda49e4aa93f7546002952fa309311b51dd@85.239.246.133:39656, 0409e99a7a3f8d07461ea1ce2593a7187c6c82cb@84.247.137.87:26656, 3b5dbd30c0ba7d616ecec0648337b8fc11ebe236@86.48.3.81:26656, d22ce5c3fd235362d36b913643e05854273c510e@65.109.133.126:15656, 634b4dd8ad6946e6d1ef4f7f6927c90eba3c42b8@85.10.201.125:17956, 541c535c7df17fd8d14e73bc3f1dec616364c41d@109.199.127.49:26656, bd3c1341b748bb14c6369122eb75311d4db304ad@104.236.199.180:26656, d893ae0cb0195c8de625cc75e803287fb6123534@65.21.193.80:15656, b4778656f255169b8b1d660b6af3a0df68d68e65@176.57.189.36:15656, fba93c5340823e74bc43f9135cc51d02aca9a4ec@43.134.32.129:26656, 769ec3e4cc3948923856aa78fe9210000b5669d5@65.109.112.148:21016, 0f564af6282b9d482afef942dab3e05682006b35@37.60.251.7:26656, 53eebd12c81059727c4a711084b6037451bdafb6@35.198.111.193:26656, 5d46d699b7abfbe83d0a9eb37a3202a64b4e5c2e@134.209.96.155:26656, a8ae28d54aadc27d7720c361d33a9ccc97e016b9@104.248.150.190:26656, 83dfef38ca8eb87e46c560215b47c0b513530dbc@213.231.8.42:26656, 51777c33bee9ff1761bcbccea62b600ae2e6f40c@193.193.226.66:26656, 0d81968d0186efa457d3c793ef84aadeaacff579@138.2.103.14:26656, cdb9469cc89aa649d2b39c968969a78463d9a814@128.199.209.150:18656, 20502af0d425f4d64e725addae22934f493c7412@85.239.246.132:39656, 04e6edb67134b1f00d81de8e0d77c7016e42857f@154.38.165.185:26656, 4a83d160338f4440fba5004a480ab8f89a8e4444@34.142.183.163:26656, ab0946f4b76f36b7d1e61ed88709182b22ef2210@194.238.25.174:26656, 4ad81b5631468f26545cb33337c262cd28794af7@167.71.200.47:26656, 39a12df7dfe508b5d7ad2ce172348276fc304da8@81.0.221.155:39656, c5bfe36e8100f8e1d64bba1455063aaaf6491fb7@45.151.122.92:26656, ead724282b82d3c9ebab34cce1e5cecd53d236b9@154.38.164.207:26656, 147da30fea230fac5b8940930890317db372e80e@209.250.236.158:26656, 82620f605fa8777c16a7b78d7be15ea43ecefefd@161.35.74.142:26656, ec3b262164cd2cb8bc726aba3d53477ac6b71164@65.21.145.221:26656, d7c6dcd7aab6165483e65cd5fe9e724c2acddcbd@199.247.16.34:26656, 2386ce79b98515184d1477ff67e50b41cd6df9f0@65.108.234.158:26606, 8627a9b4d436b45e3187f5d4cda87caa0a34d18e@45.63.116.203:26656, d2dcbdf75b0d12693b0da5ab5e258a270af1017f@38.242.211.147:26656, ca4224a3fbdbdaf5268b5712fc0b5851fc5597a9@43.157.61.234:26656, 6587d3d949442d659343d244eaf3cc1bc42cf8db@77.90.0.84:26656, 13dee1789a391e2646861c3c3da9faa296b213f5@43.133.71.240:26656, bdc48f1ae8ee4416913ac5eb45ba08c6b5cd26e3@85.239.246.128:39656, 2f4aa160398e2ac76cf801b7469dea00c861d49b@38.242.153.98:26656, 8bc7727329036ca993aef12e320618db1a18435c@62.169.17.147:26656, d9cef48445358d3d230c95aef3754c0e1005d7c1@37.27.108.81:31656, 73a5a9092285bf283fc429ec302b8b793be431d7@157.245.159.138:26656, 77e675f026d60d8391df724fb6bac2567bd2994c@85.239.246.130:39656, 75588c9d6ece63d0e2631244368c5c1a218f7a17@167.235.115.119:26656, 1cab405923904dfcc83c53a5a4a1881667cf4f9b@37.27.86.227:26656, 6024362f196b0f5df5f0abaf0552712d5b0333e7@37.27.43.80:26656, ee9d047efd2cbea485a922ef7a97e15a21755350@34.159.240.126:26656, 9149fcd768d13d5377fe5916cd00788be135adc7@43.163.209.16:26656, 1db61033a646718ff0656b3fa337398b2b45d216@173.231.40.186:25756, 3e6d431df4a14fb57bcb7a4888a3885c88ab8d5a@92.118.56.200:33756, 8ce9d23cc834c31b7d7d3882565db524534197ef@64.23.252.123:26656, 29ddd251eef0e2ca7a36cd5360a583abf248b05f@47.76.129.49:26656, a0b46b7821de927037b7a4a23da875cb12b8cb16@38.242.159.204:26656, af077a54a12c9844a90f5285ff7e2109068b1fa6@152.42.242.129:33756" && \

SEEDS="2eaa272622d1ba6796100ab39f58c75d458b9dbc@34.142.181.82:26656,c28827cb96c14c905b127b92065a3fb4cd77d7f6@testnet-seeds.whispernode.com:25756" && \
sed -i -e "s/^seeds *=.*/seeds = \"$SEEDS\"/; s/^persistent_peers *=.*/persistent_peers = \"$PEERS\"/" $HOME/.initia/config/config.toml
```

## Create Service
```
sudo tee /etc/systemd/system/initiad.service > /dev/null <<EOF
[Unit]
Description=Initia Node
After=network.target

[Service]
User=$USER
Type=simple
ExecStart=$(which initiad) start --home $HOME/.initia
Restart=on-failure
LimitNOFILE=65535

[Install]
WantedBy=multi-user.target
EOF
```
## Start Service
```
sudo systemctl daemon-reload && \
sudo systemctl enable initiad && \
sudo systemctl start initiad
```
## Create Screen and Check Logs
```
screen -Rd initiad
sudo journalctl -fu initiad -o cat
```
## Post Installation

```
source $HOME/.bash_profile
```

## Check syncing blocks
```
initiad status 2>&1 | jq
```
true = your node still catching up the block, false = your node has been synced

### You can create new or import your wallet, but make sure your wallet have faucet balances

#### Create Wallet
Create New Wallet & Don't Forget Save the Phrase
```
initiad keys add WALLET_NAME
```
Change WALLET_NAME to your own

#### Recover Phrase
```
initiad keys add $WALLET --recover
```

#### Your Wallet Lists
```
initiad keys list
```


#### Import Private Key From Metamask or Keplr
```
initiad keys import WALLET_NAME <mnemonic phrase> --keyring-backend file
```

Input your wallet name and secret mnemonic phrase

#### Check Wallet Balances
```
initiad q bank balances YOUR_INITIA_ADDRESS
```
### Regist Your Validator 
```
initiad tx mstaking create-validator \
--amount 1000000uinit \
--pubkey $(initiad tendermint show-validator) \
--moniker "YOUR_MONIKER_NAME" \
--identity "YOUR_KEYBASE_ID" \
--details "YOUR_DETAILS" \
--website "YOUR_WEBSITE_URL" \
--chain-id initiation-1 \
--commission-rate 0.05 \
--commission-max-rate 0.20 \
--commission-max-change-rate 0.05 \
--from YOUR_WALLET_NAME \
--gas-adjustment 1.4 \
--gas auto \
--gas-prices 0.15uinit \
-y
```
## Update Node
### Stop Node
```
sudo systemctl restart initiad
```
### Update to Latest Version (Change v0.X.XX to Latest Version)
```
cd initia
git fetch --all
git checkout v0.X.XX
make install
```
### Start the Node Again
```
sudo systemctl enable initiad
sudo systemctl start initiad
```
### Check Logs
```
sudo journalctl -u initiad -f -o cat
```
## Useful Commands
### Check Node Info
```
initiad status 2>&1 | jq .NodeInfo
```
### Check Sync
```
initiad status 2>&1 | jq .SyncInfo
```
### Check Logs
```
journalctl -u initiad -f -o cat
```
### Check Wallet Balances
```
initiad q bank balances YOUR_INITIA_ADDRESS
```
### Stop and Delete Node
```
sudo systemctl stop initiad && \
sudo systemctl disable initiad && \
rm /etc/systemd/system/initiad.service && \
sudo systemctl daemon-reload && \
cd $HOME && \
rm -rf .initiad && \
rm -rf initiad
