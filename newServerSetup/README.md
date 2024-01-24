This is intended for new Ubuntu installs.

Pre-Requisites:
* Install git and ansible
* Set up user who is running ansible as passwordless sudo
* Actually cloning the repo and running it

Here's a quick set of commands to accomplish this:
sudo apt-add-repostiory ppa:ansible/ansible
sudo apt update
sudo apt install git ansible
echo "$USER ALL=(ALL) NOPASSWD: ALL" | sudo tee /etc/sudoers.d/00-$USER-sudo
cd ~
git clone https://github.com/charlesharner/public-scripts.git
cd public-scripts/newServerSetup
ansible-playbook playbooks/setup.yml