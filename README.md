# 📦 Ansible LAMP Stack Deployment

This project uses **Ansible** to automate the setup of a **LAMP stack** (Linux, Apache, MySQL, PHP) on multiple servers.

---

## ✅ Features

- Installs **Apache**, **MySQL**, and **PHP**
- Deploys a sample `index.php` file
- Sets **MySQL root password** and configures login
- Uses:
  - Ansible **roles**
  - **Handlers** to restart services
  - **Blocks**, `rescue`, and `always` for error handling
  - Separate inventory files for `dev` and `prod`


---

## ▶️ How to Run

1. **Clone the repository** and navigate to the playbook directory:

   ```bash
   git clone https://github.com/your-username/ansible-lamp-deployment.git
   cd ansible-lamp-deployment/playbooks


2. **Run the Playbook**

   Execute the main playbook using your development inventory:

   ```bash
   ansible-playbook -i ../inventories/dev/hosts.ini site.yml


### 🛠️ Troubleshooting: Role Not Found Error

If you encounter an error like:  
`ERROR! the role 'mysql' was not found in ...`

Set the Ansible roles path manually:

```bash
   export ANSIBLE_ROLES_PATH=../roles
```

Then re-run the playbook

⚠️ Notes

✅ MySQL login fix: Resolved root login issues by using the mysql_native_password plugin and specifying the Unix socket.

🔁 Handlers: Apache will automatically restart when its configuration or deployed PHP files are changed.



