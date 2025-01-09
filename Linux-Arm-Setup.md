# Titan Galileo Node Setup - Linux Arm

![resim](https://github.com/user-attachments/assets/4c227290-b685-40f1-ae70-fe8524f85e3a)

### Minimum Hardware Requirements:

| CPU      | RAM     | Storage   | Upload Speed | NAT                |
|----------|---------|-----------|--------------|--------------------|
| 2c VPU   | 2G RAM  | 50G SSD + | 10Mbps +     | TCP1, 2, 3 UDP1, 2, 3 |

VPU : Intel VT-x - SVM Mode AMD


#### Run the following command to update and upgrade system packages:

```bash
sudo apt update -y && sudo apt upgrade -y
```
## 2. Install the required packages:

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen unzip lz4 -y
```

## 3. Download and Extract Installation Package

##### Download installation package

```bash
wget https://pcdn.titannet.io/test4/bin/agent-arm.zip
```

##### Create installation directory

```bash
mkdir -p /opt/titanagent
```
##### Extract installation package

```bash
unzip agent-linux.zip -d /opt/titanagent
```