# ansiblemymac

Use Ansible to setup your newly installed mac

## Preset:

### Create a ssh private/public key

	$ ssh-keygen -t rsa -b 4096 -C "my@email.com"
	$ eval "$(ssh-agent -s)"

### Edit your ssh config file

	$ vim ~/.ssh/config
	
	Host *
  	  AddKeysToAgent yes
  	  UseKeychain yes
  	  IdentityFile ~/.ssh/id_rsa
	  
### Add your SSH private key to the ssh-agent and store your passphrase in the keychain

	$ ssh-add -K ~/.ssh/id_rsa
	
### Add ssh public key to your github account

	$ cat ~/.ssh/id_rsa.pub | pbcopy
	
and Follow: https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account
	
## Preset:

### Install Homebrew:

	$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"	

### Install Ansible using homebrew:

	$ brew install ansible


## Run Ansible:

### Clone this repo:

	$ mkdir Git
	$ https://github.com/silefort/ansiblemymac.git  Git/ansiblemymac
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
* Map Caps Lock to Ctrl from the command line ( no manual action )
