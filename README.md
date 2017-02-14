# Daniel Lay Drawing Wordpress Website

## Getting Started

#### Requirements
Make sure all dependencies have been installed before moving on:

* [Ansible](http://docs.ansible.com/ansible/intro_installation.html#latest-releases-via-pip) >= 2.0.2 (except 2.1.0)
    * `brew tap homebrew/versions`
    * `brew install homebrew/versions/ansible20`
* [Virtualbox](https://www.virtualbox.org/wiki/Downloads) >= 4.3.10
* [Vagrant](https://www.vagrantup.com/downloads.html) >= 1.8.5
* [vagrant-bindfs](https://github.com/gael-ian/vagrant-bindfs#installation) >= 0.3.1 (Windows users may skip this)
    * `vagrant plugin install vagrant-bindfs`
* [vagrant-hostmanager](https://github.com/smdahlen/vagrant-hostmanager#installation)
    * `vagrant plugin install vagrant-hostmanager`


#### Local Installation
Run this command inside the `trellis` directory
```bash
# Install Ansible
ansible-galaxy install -r requirements.yml

# Start the virtual machine
vagrant up
```

## Deploy to Production or Staging
Run these commands inside the `trellis` directory if you want to launch changes to the `production` or `staging` server.

#### Build Server
`ansible-playbook server.yml -e env=production`

#### Deploy
`ansible-playbook deploy.yml -e "site=dlay.net env=production" -vvvv`
