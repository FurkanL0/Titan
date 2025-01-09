# Titan Galileo Node Einrichtung - Linux Arm

![bild](https://github.com/user-attachments/assets/4c227290-b685-40f1-ae70-fe8524f85e3a)

### Minimale Hardwareanforderungen:

| CPU      | RAM     | Speicher   | Upload-Geschwindigkeit | NAT                |
|----------|---------|-----------|--------------|--------------------|
| 2c VPU   | 2G RAM  | 50G SSD + | 10Mbps +     | TCP1, 2, 3 UDP1, 2, 3 |

VPU : Intel VT-x - SVM Modus AMD


#### Führen Sie den folgenden Befehl aus, um die Systempakete zu aktualisieren:

```bash
sudo apt update -y && sudo apt upgrade -y
```
## 2. Installieren Sie die erforderlichen Pakete:

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen unzip lz4 -y
```

## 3. Installationspaket herunterladen und extrahieren

##### Installationspaket herunterladen

```bash
wget https://pcdn.titannet.io/test4/bin/agent-arm.zip
```

##### Installationsverzeichnis erstellen

```bash
mkdir -p /opt/titanagent
```
##### Installationspaket extrahieren

```bash
unzip agent-arm.zip -d /opt/titanagent
```

## 4. Screen öffnen: 

```bash
screen -S titan
```

## 5. In das Verzeichnis wechseln: 

```bash
cd /opt/titanagent
```

## 6. Titan-Schlüssel abrufen: 

- Link: https://test4.titannet.io/ - Melden Sie sich mit Keplr an. Den Schlüssel erhalten Sie im Bereich Node Management.

![bild](https://github.com/user-attachments/assets/1e2864ef-ba38-43a1-800d-37093b3b5f73)

## 7. Starten: 

- Ersetzen Sie your-key durch Ihren Schlüssel, fügen Sie die endgültige Version ein und führen Sie sie aus. Entfernen Sie die <>.

```bash
./agent --working-dir=/opt/titanagent --server-url=https://test4-api.titannet.io --key=<ihr-schlüssel>
```

- Sie können den Screen mit CTRL A + D verlassen.

## Hauptleitfaden / Quelle: https://titannet.gitbook.io/titan-network-en/galileo-testnet/node-participation-guide
