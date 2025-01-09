# Configuration du Nœud Titan Galileo

![resim](https://github.com/user-attachments/assets/4c227290-b685-40f1-ae70-fe8524f85e3a)

## Configuration matérielle minimale :

| CPU      | RAM     | Stockage         | Vitesse de téléversement | NAT                |
|----------|---------|------------------|--------------------------|--------------------|
| 2c VPU   | 2G RAM  | 50G SSD +        | 10Mbps +                 | TCP1, 2, 3 UDP1, 2, 3 |

VPU : Intel VT-x - Mode SVM AMD

### Mettre à jour et améliorer les paquets système :

```bash
sudo apt update -y && sudo apt upgrade -y
```

### Installer les paquets requis :

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen unzip lz4 -y
```

### Télécharger Snapd :

```bash
sudo apt install snapd
```

### Activer Snap :

```bash
sudo systemctl enable --now snapd.socket
```

### Télécharger MultiPass :

```bash
sudo snap install multipass
```

### Vérifier MultiPass :

```bash
multipass --version
```

- Cela affichera le numéro de version.

### Télécharger les fichiers :

```bash
wget https://pcdn.titannet.io/test4/bin/agent-linux.zip
mkdir -p /opt/titanagent
unzip agent-linux.zip -d /opt/titanagent
```

### Ouvrir Screen :

```bash
screen -S titan
```

### Accéder au répertoire :

```bash
cd /opt/titanagent
```

### Obtenir la clé Titan :

- [Testnet Titan Galileo](https://test4.titannet.io/) – Connectez-vous avec Keplr et obtenez la clé dans la section "Node Management".

![resim](https://github.com/user-attachments/assets/1e2864ef-ba38-43a1-800d-37093b3b5f73)

### Lancer le nœud :

- Insérez votre clé dans `<your-key>`, supprimez `< >`, et exécutez la commande :

```bash
./agent --working-dir=/opt/titanagent --server-url=https://test4-api.titannet.io --key=<your-key>
```

- Quittez Screen avec `CTRL A + D`.

### Guide principal / Source :

[Guide de Participation au Nœud Titan Galileo](https://titannet.gitbook.io/titan-network-en/galileo-testnet/node-participation-guide)

