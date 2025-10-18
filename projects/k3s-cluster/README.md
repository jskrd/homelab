# Raspberry Pi K3s Cluster

```mermaid
graph BT
    subgraph "Raspberry Pi K3s Cluster"
        CP[k3s-1.home.arpa<br/>Control Plane<br/>:6443]

        subgraph "Worker Nodes"
            W1[k3s-2.home.arpa<br/>Worker]
            W2[k3s-3.home.arpa<br/>Worker]
            W3[k3s-4.home.arpa<br/>Worker]
        end

        W1 -->|Join| CP
        W2 -->|Join| CP
        W3 -->|Join| CP
    end

    User[User/kubectl] -->|API Requests| CP
```

## Prerequisites

Install Ansible (macOS):

```bash
brew install ansible
```

## Usage

Deploy K3s cluster:

```bash
ansible-playbook -i hosts site.yml --ask-vault-pass
```

Update all cluster nodes:

```bash
ansible-playbook -i hosts system-update.yml --ask-vault-pass
```

Edit the encrypted vault file:

```bash
ansible-vault edit group_vars/vault.yml
```
