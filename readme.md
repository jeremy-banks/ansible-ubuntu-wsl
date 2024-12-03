# Ansible Ubuntu WSL
Playbook to reconfigure Ubuntu WSL on Windows quickly

1. Create `repos` folder on Windows Desktop
1. Install Ubuntu WSL
   1. Ubuntu WSL username *must* be identical to the Windows username
1. Create new ssh key
   - `ssh-keygen -t ed25519 -C "workjeremyb@gmail.com"`
1. Upload key to GitHub.com
1. Install Ansible
   https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html#installing-ansible-on-ubuntu
   ```
   sudo -i
   apt update
   sudo apt install software-properties-common
   sudo add-apt-repository --yes --update ppa:ansible/ansible
   sudo apt install -y ansible
   exit
   ```
1. Clone this repo and execute playbook
   ```
   git@github.com:jeremy-banks/ansible-ubuntu-wsl.git
   cd ansible-ubuntu-wsl
   ansible-playbook site.yml -K
   ```
1. Restart Ubuntu WSL to begin working
