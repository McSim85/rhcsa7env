# RHCSA 7 Study/Test Environment powered by Ansible and Vagrant. 


## Install the following software before setting up:
- [Latest Version of Vagrant](https://www.vagrantup.com/downloads.html) - (`brew cask install vagrant`)
    - Vagrant Plugin - `vagrant plugin install vagrant-guest_ansible`
- [Latest Version of Virtualbox](https://www.virtualbox.org/wiki/Downloads) (`brew cask install VirtualBox`)
- Virtual Box Extension Pack (`brew cask install virtualbox-extension-pack`)

If you're using a Mac, Gatekeeper will block virtualbox from installing. All you have to do is go to System Preferences and click Allow under the General tab and rerun installation.

### (Linux/Mac only) Install at once with the command below:
(`brew install ansible ; brew install python ; brew cask install vagrant ; brew cask install VirtualBox ; brew cask install virtualbox-extension-pack`)

Now you should be ready to follow the next steps and get the deployment up and running!

## Once the above software is installed. Do the following if you're running the environment on Mac/Linux:
1. Create a separate `~/bin` directory and `cd` to it.  (The directory doesn't have to be ~/bin, it can be anything you want.)
2. Clone the environment repo to it with `git clone https://github.com/rdbreak/rhcsa7env.git`
3. Change to the `rhcsa7env` directory that is now in your `~/bin` directory.
3. Run `vagrant up --provider virtualbox` to deploy the environment 

## Once the above software is installed. Do the following if you're running the environment on Windows:
1. Create a separate `~/bin` directory and `cd` to it.  (The directory doesn't have to be ~/bin, it can be anything you want.)
2. Download the environment repo zip from https://github.com/rdbreak/rhcsa7env.git`
3. Unzip the repo and move the directory into the `~/bin` directory (or whatever directory you created above).
3. Open CMD prompt and cd to the repo directory then run `vagrant up --provider virtualbox` to deploy the environment 

*Also, don't be spooked by any scary red font during the setup process. There are known issues that won't have a negative affect on the environment.* 

_NOTE - You can also use the VirtualBox console to interact with the VMs or through a terminal. If you need to reset the root password, you would need to use the console._

## Other Useful Information:
The first time you run the vagrant up command, it will download the OS images for later use. In other words, it will take longest the first time around but will be faster when it is deployed again. You can run `vagrant destroy -f` to destroy your environment at anytime. **This will erase everything**. This environment is meant to be reuseable, If you run the `vagrant up --provider virtualbox` command after destroying the environment, the OS image will already be downloaded and environment will deploy faster. Once the setup is complete, the ipa server and client for realm EXAMPLE.COM will already be setup and paired. Deployment should take around 10 minutes depending on your computer. Hope this helps in your studies!

### This environment includes two systems:
- ipa.example.com
- system1.example.com

### System Details:
###### ipa
192.168.55.5
###### system1
192.168.55.6

There is a repo available to use from `http://ipa.example.com/rpms`

### Accessing the systems
Remember to add the IP addresses to your local host file if you want to connect to the guest systems with the hostname.
Username - vagrant
Password - vagrant
- For root - use `sudo` or `sudo su`
Access example - `ssh vagrant@192.168.55.5` or `vagrant ssh system`

### LDAP users
- Username = dave, lisa
- Password = password

## Help
If you're having problems with the environment, please submit an issue by going to the `ISSUES` tab at the top. If you have more questions, looking for practice exams to use against this environment, or just looking for a fantastic Red Hat community to join, please navigate to #practiceexam in the [Red Hat Certs Slack Workspace](https://join.slack.com/t/redhat-certs/shared_invite/enQtNjAxNDc3MzYyMTAxLWZlM2ZhMGRlNGI2YjQyMzQ4NWEyNDIyYTJiNzcxM2E1ZDVkZmQ4MzU2MTc0ZDRlNzg2MTU5NWIwZjFjZDdjMGE).
