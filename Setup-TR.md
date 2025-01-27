# Titan Galileo Node Setup

![resim](https://github.com/user-attachments/assets/4c227290-b685-40f1-ae70-fe8524f85e3a)

### Minimum Hardware Requirements:

| CPU      | RAM     | Storage   | Upload Speed | NAT                |
|----------|---------|-----------|--------------|--------------------|
| 2c VPU   | 2G RAM  | 50G SSD + | 10Mbps +     | TCP1, 2, 3 UDP1, 2, 3 |

#### Sanallaştırma Desteği Kontrol : 

```bash
grep --color vmx|svm /proc/cpuinfo
```

- SVM Desteği : 
```bash
lscpu | grep -i virtualization
```

#### Sistem paketlerini güncellemek ve yükseltmek için aşağıdaki komutu çalıştırın:

```bash
sudo apt update -y && sudo apt upgrade -y
```
## 2. Gerekli paketleri kurun:

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen unzip lz4 -y
```

## 3. Snapd İndirelim : 

```bash
sudo apt install snapd
```

## 4. Kurulumdan sonra Snap'i etkinleştirelim : 

```bash
sudo systemctl enable --now snapd.socket
```

## 5. MultiPass İndirelim : 

```bash
sudo snap install multipass
```

## 6. MultiPass indirmemizi Doğrulayalım : 

```bash
multipass --version
```

- Size versiyon numarasını gösterecek.

## 7. Dosyaları İndirelim : 

```bash
wget https://pcdn.titannet.io/test4/bin/agent-linux.zip
```

```bash
mkdir -p /opt/titanagent
```

```bash
unzip agent-linux.zip -d /opt/titanagent
```

## 7. Screen Açalım : 

```bash
screen -S titan

```
## 8. Dizine Girelim : 

```bash
cd /opt/titanagent
```

## 9 . Titan Keyimizi Alalım : 

- Link : https://test4.titannet.io/ - Keplr İle Giriş yapıyoruz. Node Management Kısmından keyimizi alıyoruz.

![resim](https://github.com/user-attachments/assets/1e2864ef-ba38-43a1-800d-37093b3b5f73)

## 10. Başlatalım : 

- your-key kısmına aldığınız keyi koyup son halini yapıştırıp çalıştırın. <> kısmını kaldırın.

```bash
./agent --working-dir=/opt/titanagent --server-url=https://test4-api.titannet.io --key=<your-key>
```

- CTRL A + D ile screeenden çıkabilirsiniz.

## Main Rehber / Source : https://titannet.gitbook.io/titan-network-en/galileo-testnet/node-participation-guide

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=FurkanL0&style=flat-square&color=brightgreen&label=Profile+Views+/+Repo+Views+" alt="Repo / Profile Views" />
</p>
