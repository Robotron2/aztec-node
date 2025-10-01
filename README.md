<img width="680" height="340" alt="image" src="https://github.com/user-attachments/assets/0198638d-6087-4ec5-b90a-dc305188db29" />

# Aztec Network Sequencer Node

A step by step guide on How to Run `Sequencer Node` on Aztec Network Testnet & Earn `Apprentice` Role.

-   **What types of nodes can participate in the testnet?**
    -   `Sequencer`: proposes blocks, validates blocks from others, and votes on upgrades.
    -   `Prover`: generates ZK proofs that attest to roll-up integrity.

## Roles Info

Sequecner Nodes will receive a certain role for their contribution on Discord.

After running and syncing your Sequencer node, You can go through [Get Role](https://github.com/0xmoei/aztec-network/blob/main/README.md#get-apprentice-discord-role) step.

---

## Hardware Requirements

<table>
  <tr>
    <th colspan="3"> Sequencer Node HW Requirements </th>
  </tr>
  <tr>
    <td>RAM</td>
    <td>CPU</td>
    <td>Disk</td>
  </tr>
  <tr>
    <td><code>8-16 GB</code></td>
    <td><code>4-9 cores</code></td>
    <td><code>100+ GB SSD</code></td>
  </tr>
</table>

-   **Prover Node**: Requiring ~40x machines with 16 cores and 128GB RAM
-   You can skip here.

---

**Windows Users**: must run via wsl

**VPS Users(Linux environment)**: can get started via a `VPS` with 4 cores CPU, 8GB RAM! [Purchase here](https://contabo.com/en/)

---

## 1. Install Dependecies

-   Update packages:

```bash
sudo apt-get update && sudo apt-get upgrade -y
```

-   Install Packages:

```bash
sudo apt install curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev  -y
```

-   Install Docker:

```bash
sudo apt update -y && sudo apt upgrade -y
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update -y && sudo apt upgrade -y

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# Test Docker
sudo docker run hello-world

sudo systemctl enable docker
sudo systemctl restart docker
```

---
