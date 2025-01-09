# Einrichtung des Titan Galileo-Knotens - Linux Arm

![resim](https://github.com/user-attachments/assets/4c227290-b685-40f1-ae70-fe8524f85e3a)

### Mindestanforderungen an die Hardware :

| CPU      | RAM     | Storage   | Upload Speed | NAT                |
|----------|---------|-----------|--------------|--------------------|
| 2c VPU   | 2G RAM  | 50G SSD + | 10Mbps +     | TCP1, 2, 3 UDP1, 2, 3 |

VPU : Intel VT-x - SVM Mode AMD


#### Führen Sie den folgenden Befehl aus, um Systempakete zu aktualisieren und zu aktualisieren:

```bash
sudo apt update -y && sudo apt upgrade -y
```
## 2. Installieren Sie die erforderlichen Pakete:

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen unzip lz4 -y
```

## 3. Installationspaket herunterladen und entpacken

##### Installationspaket herunterladen : 

```bash
wget https://pcdn.titannet.io/test4/bin/agent-arm.zip
```

##### Installationsverzeichnis erstellen

```bash
mkdir -p /opt/titanagent
```
##### Installationspaket entpacken

```bash
unzip agent-linux.zip -d /opt/titanagent
```

## 4. Open Screen : 

```bash
screen -S titan

```
## 5. Enter File : 

```bash
cd /opt/titanagent
```

## 6 . Holen wir uns unseren Titan Key : 

- Link : https://test4.titannet.io/ - Wir loggen uns mit Keplr ein. Wir erhalten unseren Schlüssel von der Node Management Section.

![resim](https://github.com/user-attachments/assets/1e2864ef-ba38-43a1-800d-37093b3b5f73)

## 7. Starten wir : 

- Fügen Sie Ihren Schlüssel in your-key ein, fügen Sie die endgültige Version ein und führen Sie sie aus. Entfernen Sie das <>.

```bash
./agent --working-dir=/opt/titanagent --server-url=https://test4-api.titannet.io --key=<your-key>
```

- Sie können den Bildschirm mit CTRL A + D verlassen.

## Main Guide / Source : https://titannet.gitbook.io/titan-network-en/galileo-testnet/node-participation-guide
