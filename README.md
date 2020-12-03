# ncm-with-ansible-git

Network Configuration Management with Ansible and Git

## What does it do?

The playbook copies the running-config from each device and save it into a local directory (Git repository). The playbook also commits and push the changes to GitLab everyday. 

The example playbook consists of ASA, NXOS and IOS based devices. You can have login credentials encrypted using vault and have a group_vars file with connection information for each group. 

## Cronjob

You can configure cronjob to run the playbook everydat at specific time. 

`0 1 * * * /usr/bin/ansible-playbook /home/ubuntu/config_backup/playbooks/config_backup.yml` 


For more info: https://packetswitch.co.uk/ncm-ansible-git/
