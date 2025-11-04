# Homelab

Infrastructure-as-code and automation for my homelab.

Current focus:

- `projects/k3s-cluster` – Builds and maintains the Raspberry Pi K3s control plane and worker nodes with Ansible.
- `projects/k3s-apps` – Installs cluster add-ons (Argo CD, MinIO) via Ansible + Helm.

Run playbooks from the respective project directories:

```bash
cd projects/k3s-cluster
ansible-playbook -i hosts site.yaml --ask-vault-pass
```

```bash
cd projects/k3s-apps
ansible-playbook -i hosts site.yaml --ask-vault-pass
```

More homelab-y things to be added over time following the same pattern.
