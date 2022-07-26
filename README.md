# Drupal-template
Learning Drupal Templating using DDEV local and docker
## Pre-requirement
<ul>
<li>Docker Desktop</li>
<li>Homebrew Install</li>
<li>Brew install DDEV from drud/dev</li>
<li>MacOS NFS Setup</li>
</ul>


### Step 1

Install Home brew

/bin/bash -c "$(curl -fsSL [https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh](https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh))"

Install Docker

[https://docs.docker.com/desktop/mac/install/](https://docs.docker.com/desktop/mac/install/)

Allow permission for docker and start docker. You do need to sign in docker. To made sure Docker working, go to CLI to do a `docker ps`

### Step 2

Install DDEV + bash-completion
[https://sourabhbajaj.com/mac-setup/BashCompletion/](https://sourabhbajaj.com/mac-setup/BashCompletion/)
Go to terminal type: `brew tap drud/ddev`, then brew install `ddev bash-completion.` Follow instruction, add `[[ -r "/usr/local/etc/profile.d/bash_completion.sh" ]] && . "/usr/local/etc/profile.d/bash_completion.sh”` to your .bash_profile. After closing the bash profile, update the profile by typing `source .bash_profile` at the terminal.

At the terminal type `mkcert -install` to install mkcert so that you server trust your browsers.

### Step 3

Enable NFS to serve webpage faster.

[https://ddev.readthedocs.io/en/latest/users/performance/](https://ddev.readthedocs.io/en/latest/users/performance/#macos-nfs-setup)

add the terminal paste this `curl -O [https://raw.githubusercontent.com/drud/ddev/master/scripts/macos_ddev_nfs_setup.sh](https://raw.githubusercontent.com/drud/ddev/master/scripts/macos_ddev_nfs_setup.sh)` to grab the script to run it. All administration for computer.

### Step 4

Go to terminal type `ddev config global —nfs-mount-enabled` , go to the folder you want to eg. `cd workspace`, create a new folder `mkdir drupal-dev` , go to drupal-dev, type `ddev config —project-type=drupal9 —docroot=web —create-docroot` do a `composer create drupal/recommended-project` after the configuration complete.

### Problem Facing

- PHP version on mac
- [https://stackoverflow.com/questions/64684713/update-php-to-7-4-macos-catalina-with-brew](https://stackoverflow.com/questions/64684713/update-php-to-7-4-macos-catalina-with-brew)
brew update
brew upgrade php
php -v
brew services start php
brew services restart php
brew unlink php@7.3
brew link php@7.4f
