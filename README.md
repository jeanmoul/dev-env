> playbook based on chaosmail/dev-env


# Before Starting

Download Ubuntu  18.04 LTS 64bit from [ubuntu.com](http://www.ubuntu.com/download/desktop) and install it on your machine.

Git and openssh are the only requirement needed, so go ahead and install it via `sudo apt-get install -y git openssh-server`.

[//]: # ## Getting started

[//]: # First, clone the *dev-env* repository to your machine to the *~/.dev-env* directory. Then you can run the [//]: # setup script, which will install Python, Pip and Ansible. It will also link the `run.sh` file to the [//]: # `dev-env` command.
 
[//]: # ```sh
[//]: #[//]: # git clone git@github.com:chaosmail/dev-env.git ~/.dev-env
[//]: # sh ~/.dev-env/scripts/setup.sh
```

## Installing, updating and configuring your Environment

After running the above setup script, you can automatically install and configure all your development applications with Ansible by running the `dev-env` command from the terminal.

## What's included?

At the moment, following packages will be automatically installed and configured:

* common: curl, gcc, nmap, wget, make, git, openssl
* chromium: installation
* docker: installation
* tools : filezilla, keepassx, inkscape, sketch, pandoc, git, maven, gradle, zsh,screen, tmux, terminator, jq, atom  
* java: installation (Open JDK/JRE 11)
* nodejs: installation and install npm packages (define in group_vars/all.yml)
* python: python3, pip3 and python packages (define in group_vars/all.yml)
* vscode: installation
* dev ide: eclipse, vscode, intellij


* It also configure 
** the CSSF proxy for
*** the system
*** firefox
** the good time server






## Development

To debug the configuration you can simply add the `tags: debug` statement to a tasks and then call the following command to execute these tasks.

```sh
cd ~/.dev-env
ansible-playbook $DIR/playbooks/main.yml -i hosts --ask-sudo-pass --tags debug
```
