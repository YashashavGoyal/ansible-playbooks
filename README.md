# 🎓 Ansible Practice Labs & Skill Building

This repository is a curated collection of individual **Ansible Practice Labs**. Each directory contains self-contained playbooks and configurations created to master specific Ansible modules, plugins, and automation patterns.

---

## 🛠️ Prerequisites & Requirements

Before running the playbooks, ensure your environment is prepared. Several labs rely on external Ansible collections.

### 📦 Required Collections
To install the necessary external collections, run the following commands:

```bash
# Install POSIX modules (for mount, firewalld, etc.)
ansible-galaxy collection install ansible.posix

# Install community modules (for advanced system management)
ansible-galaxy collection install community.general
```

### 🗝️ Workspace setup
- **`ansible.cfg`**: Configured to look for collections in `./collection/path`.
- **`inventory.yml`**: Defines `dev`, `prod`, and standalone server hosts.

---

## 🚀 Learning Labs

Each folder below represents a distinct practice scenario. Navigate into a directory to explore its specific implementation.

| Learning Lab | Focus Area | What You'll Practice |
| :--- | :--- | :--- |
| [**`partition/`**](./partition) | Storage & LVM | Creating PVs, VGs, LVs, and handling disk partitioning. |
| [**`vault/`**](./vault) | Security | Encrypting/decrypting variables and files with Ansible Vault. |
| [**`template/`**](./template) | Dynamic Config | Using Jinja2 templates for SSH configs and custom scripts. |
| [**`fact/`**](./fact) | Data Discovery | Implementing custom facts (facts.d) and host discovery. |
| [**`handlers/`**](./handlers) | Event Flows | Orchestrating service restarts only upon config changes. |
| [**`loop_conditional/`**](./loop_conditional) | Control Logic | Mastering `when`, `with_items`, `until`, and `register`. |
| [**`var_try/`**](./var_try) | Variables | Understanding variable precedence and `group_vars`/`host_vars`. |

---

## 📖 How to Practice

1. **Navigate** to the desired lab folder.
2. **Review** the `play.yml` (or specifically named playbooks like `lvm.yml`) to understand the logic.
3. **Execute** the playbook from the root or lab directory.

> [!IMPORTANT]
> Since these are practice labs, many playbooks are designed for specific node names (e.g., `node1`, `node2`). Check your [`inventory.yml`](./inventory.yml) to ensure it matches your test environment.

### Commands for Execution
```bash
# Typical practice execution
ansible-playbook <lab_folder>/play.yml

# Using Vault for the security lab
ansible-playbook vault/play.yml --ask-vault-pass
```

---

> [!TIP]
> Use `ansible-playbook --syntax-check` frequently while practicing to catch errors early. Happy Automating!
