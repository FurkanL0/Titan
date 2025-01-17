# Configuración del Nodo Titan Galileo

![resim](https://github.com/user-attachments/assets/4c227290-b685-40f1-ae70-fe8524f85e3a)

## Requisitos mínimos de hardware:

| CPU      | RAM     | Almacenamiento  | Velocidad de subida | NAT                |
|----------|---------|-----------------|---------------------|--------------------|
| 2c VPU   | 2G RAM  | 50G SSD +       | 10Mbps +            | TCP1, 2, 3 UDP1, 2, 3 |

VPU: Intel VT-x - Modo SVM AMD

### Actualizar y mejorar los paquetes del sistema:

```bash
sudo apt update -y && sudo apt upgrade -y
```

### Instalar los paquetes necesarios:

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen unzip lz4 -y
```

### Descargar Snapd:

```bash
sudo apt install snapd
```

### Activar Snap:

```bash
sudo systemctl enable --now snapd.socket
```

### Descargar MultiPass:

```bash
sudo snap install multipass
```

### Verificar MultiPass:

```bash
multipass --version
```

- Mostrará el número de versión.

### Descargar archivos:

```bash
wget https://pcdn.titannet.io/test4/bin/agent-linux.zip
mkdir -p /opt/titanagent
unzip agent-linux.zip -d /opt/titanagent
```

### Abrir Screen:

```bash
screen -S titan
```

### Cambiar al directorio:

```bash
cd /opt/titanagent
```

### Obtener la clave de Titan:

- [Titan Galileo Testnet](https://test4.titannet.io/) – Inicie sesión con Keplr y obtenga la clave en la sección "Node Management".

![resim](https://github.com/user-attachments/assets/1e2864ef-ba38-43a1-800d-37093b3b5f73)

### Iniciar el nodo:

- Inserte su clave en `<your-key>`, elimine `< >`, y ejecute el comando:

```bash
./agent --working-dir=/opt/titanagent --server-url=https://test4-api.titannet.io --key=<your-key>
```

- Salga de Screen con `CTRL A + D`.

### Guía principal / Fuente:

[Guía de Participación del Nodo Titan Galileo](https://titannet.gitbook.io/titan-network-en/galileo-testnet/node-participation-guide)


<p align="center">
  <img src="https://komarev.com/ghpvc/?username=FurkanL0&style=flat-square&color=brightgreen&label=Profile+Views+/+Repo+Views+" alt="Repo / Profile Views" />
</p>
