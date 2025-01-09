# Titan Galileo Node Kurulumu - Linux Arm

![resim](https://github.com/user-attachments/assets/4c227290-b685-40f1-ae70-fe8524f85e3a)

### Minimum Donanım Gereksinimleri:

| CPU      | RAM     | Storage   | Upload Speed | NAT                |
|----------|---------|-----------|--------------|--------------------|
| 2c VPU   | 2G RAM  | 50G SSD + | 10Mbps +     | TCP1, 2, 3 UDP1, 2, 3 |

VPU : Intel VT-x - SVM Mode AMD


#### Sistem paketlerini güncellemek ve yükseltmek için aşağıdaki komutu çalıştırın:

```bash
sudo apt update -y && sudo apt upgrade -y
```
## 2. Gerekli paketleri yükleyin:

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen unzip lz4 -y
```

## 3. Kurulum Paketini İndirin

##### Kurulum paketini indirin

```bash
wget https://pcdn.titannet.io/test4/bin/agent-arm.zip
```

##### Kurulum dizini oluşturun

```bash
mkdir -p /opt/titanagent
```
##### Kurulum için indirdiğimiz paketi zip'den çıkartalım

```bash
unzip agent-linux.zip -d /opt/titanagent
```

## 4. Screen Açalım : 

```bash
screen -S titan

```
## 5. Dizine Girelim : 

```bash
cd /opt/titanagent
```

## 6 . Titan Keyimizi Alalım : 

- Link : https://test4.titannet.io/ - Keplr ile giriş yapıyoruz. Anahtarımızı Node Yönetim ( Managament )  Bölümünden alıyoruz.

![resim](https://github.com/user-attachments/assets/1e2864ef-ba38-43a1-800d-37093b3b5f73)

## 7. Çalıştırın : 

- anahtarınızı Yapıştırın ve son sürümü yapıştırın ve çalıştırın. <> işaretini kaldırın.

```bash
./agent --working-dir=/opt/titanagent --server-url=https://test4-api.titannet.io --key=<your-key>
```

- CTRL A + D ile screen'den çıkabilirsiniz.

## Main Guide / Source : https://titannet.gitbook.io/titan-network-en/galileo-testnet/node-participation-guide