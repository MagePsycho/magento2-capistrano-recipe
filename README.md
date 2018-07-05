# Automated Magento2 Deployment via Capistrano

## Prerequisite
Assumptions
- Operating System: Ubuntu 16.04
- PHP Version - 7.0

### SSH
### Ruby
### Git
### Deployer
Deploying with the root user is a potential risk.  
So it's better to create a new user, say `deployer` associated with web-group `www-data`
```
# Login to a remote server
sudo adduser deployer
sudo passwd deployer
sudo usermod -a -G www-data deployer
# make www-data as primary group
# sudo usermod -g www-data deployer
su deployer
whoami
```

Some of the operation may require root access like changing ownership, restarting web-server, php etc.
In order to have promptless deployment, create a new sudoers file
```
visudo -f /etc/sudoers.d/deployer
```
with following text
```
deployer ALL=(ALL) ALL
deployer ALL=NOPASSWD:/bin/chown
deployer ALL=NOPASSWD:/bin/chmod
deployer ALL=NOPASSWD:/usr/sbin/service php7.0-fpm reload
deployer ALL=NOPASSWD:/usr/sbin/service php7.0-fpm restart
```

## Installation

## Configuration

## Deployment
