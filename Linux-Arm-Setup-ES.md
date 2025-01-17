# Configuración del Nodo Titan Galileo - Linux Arm

![imagen](https://github.com/user-attachments/assets/4c227290-b685-40f1-ae70-fe8524f85e3a)

### Requisitos Mínimos de Hardware:

| CPU      | RAM     | Almacenamiento | Velocidad de Subida | NAT                |
|----------|---------|--------------|-----------------|--------------------|
| 2c VPU   | 2G RAM  | 50G SSD +    | 10Mbps +        | TCP1, 2, 3 UDP1, 2, 3 |

VPU : Intel VT-x - Modo SVM AMD


#### Ejecute el siguiente comando para actualizar los paquetes del sistema:

```bash
sudo apt update -y && sudo apt upgrade -y
```
## 2. Instale los paquetes requeridos:

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen unzip lz4 -y
```

## 3. Descarga y Extracción del Paquete de Instalación

##### Descargue el paquete de instalación

```bash
wget https://pcdn.titannet.io/test4/bin/agent-arm.zip
```

##### Cree el directorio de instalación

```bash
mkdir -p /opt/titanagent
```
##### Extraiga el paquete de instalación

```bash
unzip agent-arm.zip -d /opt/titanagent
```

## 4. Abra Screen: 

```bash
screen -S titan
```

## 5. Entre al Directorio: 

```bash
cd /opt/titanagent
```

## 6. Obtengamos nuestra Clave Titan: 

- Enlace: https://test4.titannet.io/ - Iniciamos sesión con Keplr. Obtenemos nuestra clave desde la Sección de Gestión de Nodos.

![imagen](https://github.com/user-attachments/assets/1e2864ef-ba38-43a1-800d-37093b3b5f73)

## 7. Iniciemos: 

- Coloque su clave en your-key, pegue la versión final y ejecútela. Elimine los <>.

```bash
./agent --working-dir=/opt/titanagent --server-url=https://test4-api.titannet.io --key=<su-clave>
```

- Puede salir de la pantalla con CTRL A + D.

## Guía Principal / Fuente: https://titannet.gitbook.io/titan-network-en/galileo-testnet/node-participation-guide

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=FurkanL0&style=flat-square&color=brightgreen&label=Profile+Views+/+Repo+Views+" alt="Repo / Profile Views" />
</p>
