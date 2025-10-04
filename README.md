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

```bash

```

```bash

```
