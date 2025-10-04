# Arcium

![GnDA1e4a0AAjJSQ](https://github.com/user-attachments/assets/bdc8dd66-1cfa-4201-ac4c-de1be1b8ba63)


| X        | Minimum              |
|------------------|----------------------------|
| **CPU**          | 12++ |
| **RAM**          | 32++ GB                    |
| **Disk**      | 50 GB+ NVME GB SDD                   |
| **Internet Hızı**      | 1 Gbps+  |
| **Ubuntu**      | Ubuntu 24.04++  |


| Server         | Link              | Features |
|------------------|----------------------------|----------------------------|
| **Contabo**          | [Link](https://www.dpbolvw.net/click-101330552-12454592)                     | Cheap / Paypal  |
| **NetCup**          | [Link](https://www.netcup.com/en/?ref=261820) | Cheap / Paypal |


## Server Güncelleme : 

```bash
sudo apt update -y && sudo apt upgrade -y
```
## Paketleri İndirelim :

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen file unzip lz4 -y
```

## Protobuf Compiler

```bash
sudo apt install -y protobuf-compiler
```

## Docker ; 

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io -y
docker version
```

## Docker Compose : 

```bash
VER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep tag_name | cut -d '"' -f 4)
curl -L "https://github.com/docker/compose/releases/download/$VER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

## Docker User

```bash
sudo groupadd docker
sudo usermod -aG docker $USER
```

## Rust ; 

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

<img width="505" height="164" alt="image" src="https://github.com/user-attachments/assets/5a8a34ad-5fbc-4b6e-a5c5-883f86c482d5" />


- 1, Enter.

```bash
source $HOME/.cargo/env
```

## Solana CLI ; 
```bash
curl --proto '=https' --tlsv1.2 -sSfL https://solana-install.solana.workers.dev | bash
```

<img width="498" height="206" alt="image" src="https://github.com/user-attachments/assets/29828be5-87e7-4c83-b1c4-8c0f9013832a" />


- Başarılı Bir Kurulum Sonrası Böyle Gözükecek : 

```bash
Installed Versions:
Rust: rustc 1.86.0 (05f9846f8 2025-03-31)
Solana CLI: solana-cli 2.2.12 (src:0315eb6a; feat:1522022101, client:Agave)
Anchor CLI: anchor-cli 0.31.1
Node.js: v23.11.0
Yarn: 1.22.1
```

<img width="548" height="439" alt="image" src="https://github.com/user-attachments/assets/ede58642-899e-4fa1-bdf7-06a7a25149ea" />


- Version Kontrolü 
```bash
rustc --version && solana --version && anchor --version && node --version && yarn --version
```

<img width="924" height="95" alt="image" src="https://github.com/user-attachments/assets/2dac1954-a0c6-439b-8e24-ba742e15fac6" />


- Solana komutu yok hatası alırsanız sunucudan çıkan bir daha girip deneyin Shell ( terminal'in ) yenilenmesi lazım arada oluyo.

## OpenSSL ; 
```bash
sudo apt update
sudo apt install build-essential checkinstall git zlib1g-dev -y
```

```bash
cd /usr/local/src
sudo wget https://www.openssl.org/source/openssl-3.5.4.tar.gz
```

```bash
sudo tar -xzf openssl-3.5.4.tar.gz
cd openssl-3.5.4
```

```bash
sudo ./Configure --prefix=/usr/local/openssl --openssldir=/usr/local/openssl shared zlib
```

<img width="1101" height="404" alt="image" src="https://github.com/user-attachments/assets/1a8bef03-0639-4253-bd96-67b5885939d5" />


```bash
sudo make -j$(nproc)
sudo make install
```

- Bu aşama hızlı sunucularda 4 ila 10 dakika arası sürer. Ona göre hesap yapın 

```bash
sudo ln -sf /usr/local/openssl/bin/openssl /usr/bin/openssl
```

```bash
echo "/usr/local/openssl/lib64" > /etc/ld.so.conf.d/openssl-3.5.4.conf
ldconfig
```

```bash
openssl version
```

## Arcium Kurulum

- Dosyaları Oluşturalım

```bash
mkdir arcium-node-setup
cd arcium-node-setup
```

- Sunucunuzun IP Adresini unutmayın.

## Arcium Tooling

```bash
curl --proto '=https' --tlsv1.2 -sSfL https://arcium-install.arcium.workers.dev/ | bash
```

<img width="625" height="510" alt="image" src="https://github.com/user-attachments/assets/f9651049-6f23-4024-8df7-f915503b3eb6" />

<img width="410" height="176" alt="image" src="https://github.com/user-attachments/assets/c8d02ef1-d364-4dba-9c44-8bd5e3bfc5d8" />


- Veriyon Kontrol 

```bash
arcium --version
arcup --version
```

<img width="515" height="89" alt="image" src="https://github.com/user-attachments/assets/d24651fa-6abb-4c36-b34e-ba8dba859f37" />

## Node Auth Key

- TÜM KELİMELERİ VB. KAYIT EDİN ÖNEMLİ !

```bash
solana-keygen new --outfile node-keypair.json --no-bip39-passphrase
```

<img width="918" height="162" alt="image" src="https://github.com/user-attachments/assets/e978753b-9de6-4376-9196-225c5094e926" />

## Geri Çağırma (Callback) Key

```bash
solana-keygen new --outfile callback-kp.json --no-bip39-passphrase
```

<img width="891" height="161" alt="image" src="https://github.com/user-attachments/assets/da9c890f-eae3-46b9-972a-9c0adde3e0ea" />


## Kimlik (Identity) Key 

```bash
openssl genpkey -algorithm Ed25519 -out identity.pem
```

<img width="811" height="85" alt="image" src="https://github.com/user-attachments/assets/2c41c8f2-d6f7-4b93-baf2-d470488b7f78" />

- Sunucunuza FTP yada Termius'daki gibi SFTP olarak bağlanıp bu dosyaların tümünü yedek alın.

<img width="1670" height="285" alt="image" src="https://github.com/user-attachments/assets/339888c1-3a9d-488a-865b-5c9f44962e5b" />

## Cüzdanları Dolduralım ; 
```bash
solana address --keypair node-keypair.json
```

```bash
solana address --keypair callback-kp.json
```

- 2 Cüzdan Adresinizde Kaydedin.

<img width="920" height="105" alt="image" src="https://github.com/user-attachments/assets/83754d9b-23b0-4c59-8a42-983c7f945a8d" />

## Testnet Tokeni Alalım

- Burada <node-pubkey> alanına node keypair'in adresi yapıştırıcaz örnek benimki : solana airdrop 2 2vttqQh2vaCipSMtxHZswh1thSVARw1JXRhZeG6Fwj4b -u devnet

```bash
solana airdrop 2 <node-pubkey> -u devnet
```

- Faucet kullanıldığından Rate Limit hatası vardı 2. denemede aldı.

<img width="1172" height="176" alt="image" src="https://github.com/user-attachments/assets/dcbf420f-735d-4d93-a5f2-bca509e999d8" />

- Burada <callback-pubkey> alanına call back'in adresi yapıştırıcaz örnek benimki : solana airdrop 2 BP6edbgweoK4rZYsdYjChiBT8dJjzpm6b9rhyFbB7fHJ -u devnet

```bash
solana airdrop 2 <callback-pubkey> -u devnet
```

<img width="1217" height="265" alt="image" src="https://github.com/user-attachments/assets/8d22e161-8ca8-4245-a43f-f019bf8b0879" />

- Hata alırsanız siteden alabilirsiniz benim gibi - Githubla giriş yapmadan alamazsınız. ; https://faucet.solana.com/

<img width="1211" height="944" alt="image" src="https://github.com/user-attachments/assets/4eaf57a6-4392-4c57-8590-c49d5020f581" />

## Init İşlemleri 

- Bize RPC lazım - Ben Helius Free kullancam yeterli olur demişler ; https://dashboard.helius.dev/

- QuickNode'dee Kullanabilirsiniz Demişler : https://www.quicknode.com/

- Sağlacılarınızda Api Key alırken Devnet'in Api'sini almayı unutmayın ; 

<img width="1892" height="472" alt="image" src="https://github.com/user-attachments/assets/0c38372b-4f8c-42b0-abae-508f0e876831" />

- Keyimizi Config'e ekleyelim örnek ;

```bash
solana config set --url https://devnet.helius-rpc.com/?api-key=gel-yanima-gel-gel-neset-ertas
```

<img width="437" height="126" alt="image" src="https://github.com/user-attachments/assets/1b4e0301-5954-4670-9dbd-694cacb3dfc9" />


## Önemli Kısım ; 

```bash
arcium init-arx-accs \
  --keypair-path node-keypair.json \
  --callback-keypair-path callback-kp.json \
  --peer-keypair-path identity.pem \
  --node-offset <your-node-offset> \
  --ip-address <your-node-ip> \
  --rpc-url https://api.devnet.solana.com
```

- "--ip-address <your-node-ip> \" <your-node-ip> kısmına sunucu ip adresi.
- "--node-offset <your-node-offset> \" burada <your-node-offset> kısmına 8 ila 10 haneli random ID yazacaksınız amaç çakışmaması için farklı seçmek node offset'ide kaydedin bir kenara.
-  "--rpc-url https://api.devnet.solana.com" rpc'mizi almıştık zaten api devnet olan rpc'yi kendi RPC'miz ile değiştiriyoruz https://devnet.helius-rpc.com/?api-key=gel-yanima-gel-gel-neset-ertas.

- Örnek ( 777777777 Benim ) : 

<img width="943" height="284" alt="image" src="https://github.com/user-attachments/assets/4644d947-e2d8-49c6-8b80-3a300e50ac10" />

## Yapılandırma İşlemleri ; 

```bash
nano node-config.toml
```
