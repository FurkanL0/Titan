# Configuration du Nœud Titan Galileo - Linux Arm

![image](https://github.com/user-attachments/assets/4c227290-b685-40f1-ae70-fe8524f85e3a)

### Configuration Matérielle Minimale :

| CPU      | RAM     | Stockage  | Vitesse Upload | NAT                |
|----------|---------|-----------|--------------|--------------------|
| 2c VPU   | 2G RAM  | 50G SSD + | 10Mbps +     | TCP1, 2, 3 UDP1, 2, 3 |

VPU : Intel VT-x - Mode SVM AMD


#### Exécutez la commande suivante pour mettre à jour les paquets système :

```bash
sudo apt update -y && sudo apt upgrade -y
```
## 2. Installez les paquets requis :

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen unzip lz4 -y
```

## 3. Téléchargement et Extraction du Package d'Installation

##### Téléchargez le package d'installation

```bash
wget https://pcdn.titannet.io/test4/bin/agent-arm.zip
```

##### Créez le répertoire d'installation

```bash
mkdir -p /opt/titanagent
```
##### Extrayez le package d'installation

```bash
unzip agent-arm.zip -d /opt/titanagent
```

## 4. Ouvrez Screen : 

```bash
screen -S titan
```

## 5. Entrez dans le Répertoire : 

```bash
cd /opt/titanagent
```

## 6. Obtention de votre Clé Titan : 

- Lien : https://test4.titannet.io/ - Connectez-vous avec Keplr. Récupérez votre clé depuis la section Gestion des Nœuds.

![image](https://github.com/user-attachments/assets/1e2864ef-ba38-43a1-800d-37093b3b5f73)

## 7. Lancement : 

- Remplacez your-key par votre clé et collez la version finale pour l'exécuter. Retirez les <>.

```bash
./agent --working-dir=/opt/titanagent --server-url=https://test4-api.titannet.io --key=<votre-clé>
```

- Vous pouvez quitter l'écran avec CTRL A + D.

## Guide Principal / Source : https://titannet.gitbook.io/titan-network-en/galileo-testnet/node-participation-guide

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=FurkanL0&style=flat-square&color=brightgreen&label=Profile+Views+/+Repo+Views+" alt="Repo / Profile Views" />
</p>
