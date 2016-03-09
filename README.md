## Configuration:
In the Vagrantfile:
- Fill in the 'config.vm.synced_folder' value to sync a directory from your host into the vagrant machine.

In provision/playbook.yml:
- Fill out the following in the 'vars' section:
  - username: user name for the account you want to use in the vagrant machine
  - dotfile_repo_path: full path for a repo containing the dotfiles you want to add to your home directory
  - vagrant_ssh_key: ssh key you want to use to connect to your server
