# Pengaturan Node Titan Galileo - Linux Arm

![gambar](https://github.com/user-attachments/assets/4c227290-b685-40f1-ae70-fe8524f85e3a)

### Persyaratan Minimum Perangkat Keras:

| CPU      | RAM     | Penyimpanan | Kecepatan Upload | NAT                |
|----------|---------|-----------|--------------|--------------------|
| 2c VPU   | 2G RAM  | 50G SSD + | 10Mbps +     | TCP1, 2, 3 UDP1, 2, 3 |

VPU : Intel VT-x - Mode SVM AMD


#### Jalankan perintah berikut untuk memperbarui paket sistem:

```bash
sudo apt update -y && sudo apt upgrade -y
```
## 2. Instal paket yang diperlukan:

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen unzip lz4 -y
```

## 3. Unduh dan Ekstrak Paket Instalasi

##### Unduh paket instalasi

```bash
wget https://pcdn.titannet.io/test4/bin/agent-arm.zip
```

##### Buat direktori instalasi

```bash
mkdir -p /opt/titanagent
```
##### Ekstrak paket instalasi

```bash
unzip agent-arm.zip -d /opt/titanagent
```

## 4. Buka Screen: 

```bash
screen -S titan
```

## 5. Masuk ke Direktori: 

```bash
cd /opt/titanagent
```

## 6. Mari Dapatkan Kunci Titan: 

- Tautan: https://test4.titannet.io/ - Kita login menggunakan Keplr. Kita mendapatkan kunci dari Bagian Manajemen Node.

![gambar](https://github.com/user-attachments/assets/1e2864ef-ba38-43a1-800d-37093b3b5f73)

## 7. Mari Mulai: 

- Masukkan kunci Anda di your-key dan tempel versi finalnya lalu jalankan. Hapus tanda <>.

```bash
./agent --working-dir=/opt/titanagent --server-url=https://test4-api.titannet.io --key=<kunci-anda>
```

- Anda dapat keluar dari screen dengan CTRL A + D.

## Panduan Utama / Sumber: https://titannet.gitbook.io/titan-network-en/galileo-testnet/node-participation-guide

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=FurkanL0&style=flat-square&color=brightgreen&label=Profile+Views+/+Repo+Views+" alt="Repo / Profile Views" />
</p>
