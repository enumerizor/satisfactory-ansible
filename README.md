# satisfactory-ansible
Ansible playbook(s) for configuring Satisfactory dedicated servers

Enclosed is an ansible playbook which is an adaption of the currently available installation instructions for [steamcmd](https://developer.valvesoftware.com/wiki/SteamCMD) and [satisfactory dedicated servers](https://satisfactory.fandom.com/wiki/Dedicated_servers).

It has been tested on a fresh installation of Ubuntu server 20.04 and uses ansible modules specifically for that distribution.  Modifications will likely be necessary for use with other linux distributions.

When run this playbook will..

* Install and configure steamcmd
* Create a systemd service which both runs a Satisfactory dedicated server and uses steamcmd to keep it up to date
* Create a cron job to restart the service daily at 4 am local server time
* Install [netdata](https://www.netdata.cloud/) for server monitoring (dashboard available on server port 19999)

### Usage
To use, install ansible on your local machine and run `ansible-playbook <path_to_file>` with either `-k` or `--private-key` arguments supplied for password or private key ssh authentication respectively.  The playbook will prompt for the input of the user account to connect with, and the target server to configure.

**Note**: the user you are connecting with must have sudo rights on the server.