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

## 2. Install Aztec Tools

```bash
bash -i <(curl -s https://install.aztec.network)
```

```bash
echo 'export PATH="$HOME/.aztec/bin:$PATH"' >> ~/.bashrc

source ~/.bashrc
```

-   **Restart your Terminal** now to apply changes.
-   Check if you installed successfully:

```bash
aztec
```

---

## 3. Update Aztec

```bash
aztec-up 2.0.2
```

---

## 4. Obtain RPC URLs

-   Find a 3rd party that supports Sepolia `RPC URL` & Sepolia `BEACON URL` APIs.
-   Most of your usage is `RPC URL`. I recommend to use [Alchemy](https://dashboard.alchemy.com/) for `RPC URL` & Use [drpc](https://drpc.org/) for `Beacon URL`.

**More details on RPC solutions**:

### Get Your Own RPC by Running Geth & Prysm Nodes

-   You can run your own local RPC nodes by following this guide: [geth-prysm-node](https://github.com/0xmoei/geth-prysm-node). You may need 600-1000 GB SSD

### Free:

-   `RPC URL`: Create a Sepolia Ethereum HTTP API in [Alchemy](https://dashboard.alchemy.com/)
-   `BEACON RPC`: Create an account on [drpc](https://drpc.org/) and search for `Sepolia Ethereum Beacon Chain ` Endpoints.

![image](https://github.com/user-attachments/assets/eae865ab-461f-46cd-b3f9-b7d118dcbbdf)

### Paid:

For example: [Ankr](https://www.ankr.com/rpc/?utm_referral=LqL9Sv86Te) is supporting `RPC URL` & `Beacon URL`. You can Register, Fund it with a little USDT via your wallet, Create a project, get your normal **sepolia rpc** and **beacon sepolia rpc**.

#### Note: Sometimes 3rd party websites might fail, even when you pay. It's best to host one yourself as long as your VPS/Machine is the required spec.

![image](https://github.com/user-attachments/assets/cfde5dec-ac1a-4d58-855b-43c4374c5c87)

![image](https://github.com/user-attachments/assets/ffb97518-cd24-46ee-b131-92b2870ac407)

> You can run your own Geth & Prysm nodes to get your own `RPC URL` & `BEACON RPC` or find any other 3rd party solutions

---

## 5. Generate Ethereum Keys

Get an EVM Wallet with `Private Key` and `Public Address` saved. (Burner wallet)

---

## 6. Get Sepolia ETH

Fund your Ethereum Wallet with `ETH Sepolia`

---

## 7. Find IP

```bash
curl ipv4.icanhazip.com
```

-   Save it

---
