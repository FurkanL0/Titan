# Konfigurasi Node Titan Galileo

![resim](https://github.com/user-attachments/assets/4c227290-b685-40f1-ae70-fe8524f85e3a)

## Persyaratan Minimum Perangkat Keras:

| CPU      | RAM     | Penyimpanan      | Kecepatan Unggah       | NAT                |
|----------|---------|------------------|------------------------|--------------------|
| 2c VPU   | 2G RAM  | 50G SSD +        | 10Mbps +               | TCP1, 2, 3 UDP1, 2, 3 |

VPU: Intel VT-x - Mode SVM AMD

### Perbarui dan tingkatkan paket sistem:

```bash
sudo apt update -y && sudo apt upgrade -y
```

### Instal paket yang diperlukan:

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen unzip lz4 -y
```

### Unduh Snapd:

```bash
sudo apt install snapd
```

### Aktifkan Snap:

```bash
sudo systemctl enable --now snapd.socket
```

### Unduh MultiPass:

```bash
sudo snap install multipass
```

### Verifikasi MultiPass:

```bash
multipass --version
```

- Ini akan menampilkan nomor versi.

### Unduh file:

```bash
wget https://pcdn.titannet.io/test4/bin/agent-linux.zip
mkdir -p /opt/titanagent
unzip agent-linux.zip -d /opt/titanagent
```

### Buka Screen:

```bash
screen -S titan
```

### Masuk ke direktori:

```bash
cd /opt/titanagent
```

### Dapatkan kunci Titan:

- [Testnet Titan Galileo](https://test4.titannet.io/) – Masuk dengan Keplr dan dapatkan kunci di bagian "Node Management".

![resim](https://github.com/user-attachments/assets/1e2864ef-ba38-43a1-800d-37093b3b5f73)

### Jalankan node:

- Masukkan kunci Anda di `<your-key>`, hapus `< >`, dan jalankan perintah:

```bash
./agent --working-dir=/opt/titanagent --server-url=https://test4-api.titannet.io --key=<your-key>
```

- Keluar dari Screen dengan `CTRL A + D`.

### Panduan utama / Sumber:

[Panduan Partisipasi Node Titan Galileo](https://titannet.gitbook.io/titan-network-en/galileo-testnet/node-participation-guide)

