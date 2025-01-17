# Titan Galileo Node Einrichtung

![resim](https://github.com/user-attachments/assets/4c227290-b685-40f1-ae70-fe8524f85e3a)

## Mindestanforderungen an die Hardware:

| CPU      | RAM     | Speicher  | Upload-Geschwindigkeit | NAT                |
|----------|---------|-----------|------------------------|--------------------|
| 2c VPU   | 2G RAM  | 50G SSD + | 10Mbps +               | TCP1, 2, 3 UDP1, 2, 3 |

VPU: Intel VT-x - SVM-Modus AMD

### Systempakete aktualisieren und upgraden:

```bash
sudo apt update -y && sudo apt upgrade -y
```

### Erforderliche Pakete installieren:

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen unzip lz4 -y
```

### Snapd herunterladen:

```bash
sudo apt install snapd
```

### Snap aktivieren:

```bash
sudo systemctl enable --now snapd.socket
```

### MultiPass herunterladen:

```bash
sudo snap install multipass
```

### MultiPass überprüfen:

```bash
multipass --version
```

- Die Versionsnummer wird angezeigt.

### Dateien herunterladen:

```bash
wget https://pcdn.titannet.io/test4/bin/agent-linux.zip
mkdir -p /opt/titanagent
unzip agent-linux.zip -d /opt/titanagent
```

### Screen öffnen:

```bash
screen -S titan
```

### In das Verzeichnis wechseln:

```bash
cd /opt/titanagent
```

### Titan-Schlüssel abrufen:

- [Titan Galileo Testnet](https://test4.titannet.io/) – Anmeldung mit Keplr und den Schlüssel im Abschnitt "Node Management" abrufen.

![resim](https://github.com/user-attachments/assets/1e2864ef-ba38-43a1-800d-37093b3b5f73)

### Node starten:

- Fügen Sie Ihren Schlüssel in `<your-key>` ein, entfernen Sie `< >`, und führen Sie den Befehl aus:

```bash
./agent --working-dir=/opt/titanagent --server-url=https://test4-api.titannet.io --key=<your-key>
```

- Den Screen mit `CTRL A + D` verlassen.

### Hauptanleitung / Quelle:

[Titan Galileo Node Participation Guide](https://titannet.gitbook.io/titan-network-en/galileo-testnet/node-participation-guide)


<p align="center">
  <img src="https://komarev.com/ghpvc/?username=FurkanL0&style=flat-square&color=brightgreen&label=Profile+Views+/+Repo+Views+" alt="Repo / Profile Views" />
</p>
