# Ansible Ubuntu WSL
Playbook to reconfigure Ubuntu WSL on Windows quickly

# Features
- Installs tools required for devops: aws-cli, terraform, etc
- Configures git automatically to use my name and email
- Symlinks Desktop/repos in Windows for easy use across both Windows and Ubuntu WSL
- Adds aliases I prefer to use

# Instructions
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
   apt install software-properties-common
   add-apt-repository --yes --update ppa:ansible/ansible
   apt install -y ansible
   exit
   ```
1. Clone this repo and execute playbook
   ```
   git@github.com:jeremy-banks/ansible-ubuntu-wsl.git
   cd ansible-ubuntu-wsl
   ansible-playbook site.yml -K
   ```
1. Restart Ubuntu WSL to begin working
