# ansiblemymac

Use Ansible to setup your newly installed mac

## Preset:

### Install Homebrew:

	$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"	

### Install Ansible using homebrew:

	$ brew install ansible


## Run Ansible:

### Clone this repo:

	$ https://github.com/silefort/ansiblemymac.git 
	$ cd ansiblemac

### Install Ansible requirements:

	$ ansible-galaxy install geerlingguy.homebrew

### Run your playbook:

	$ ansible-playbook main.yml -i inventory.ini -K 

## Remaining Manual Setup:

* Remap Caps Lock to Ctrl


Ideas stolen from:
* https://blog.vandenbrand.org/2016/01/04/how-to-automate-your-mac-os-x-setup-with-ansible/
* https://github.com/mtneug/cfg_mgmt-macos
* https://github.com/geerlingguy/macos-virtualbox-vm
* https://github.com/MWGriffin/ansible-playbooks
* https://github.com/geerlingguy/mac-dev-playbook

TODO:
* Automatic dotfiles (bash, vimrc, tmux...)
* different roles depending on pro or personnal computer
* CI
