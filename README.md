# 📡 Website_Publish-role

This Ansible role installs and configures an Apache web server on Red Hat-based systems. It sets a custom port and serves a basic web page with user-defined content.

## 📁 Role Structure

```
Website_Publish-role/
├── defaults/
│   └── main.yml
├── tasks/
│   └── main.yml
├── templates/
│   └── index.html.j2
```

## ⚙️ Variables

| Variable       | Description                          | Default                 |
|----------------|--------------------------------------|-------------------------|
| `custom_port`  | Port on which Apache should listen   | `88`                    |

Set these in your playbook or inventory:

```yaml
custom_port: 8080
```

## ▶️ How to Use

1. Extract the role:
   ```bash
   tar -xzvf Website_Publish-role.tar.gz
   ```

2. Use it in your playbook:

```yaml
- name: Deploy custom website
  hosts: webservers
  become: yes

  vars:
    custom_port: 8080

  roles:
    - Website_Publish-role
```

3. Run the playbook:
   ```bash
   ansible-playbook -i hosts site.yml
   ```

## 🛠️ Prerequisites

- Red Hat-based system (e.g., RHEL, CentOS)
- Apache not running on the default/custom port
- Ansible installed and configured

## 🧑‍💻 Author

Ahmed Orabi
