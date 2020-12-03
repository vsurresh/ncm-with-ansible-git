# ncm-with-ansible-git

Network Configuration Management with Ansible and Git

The example playbook consists of ASA, NXOS and IOS based devices. You can have login credentials encrypted using vault and have a group_vars file with connection information for each group. 

group_vars should look something like this for the ASA. 

ansible_connection: network_cli
ansible_network_os: asa
ansible_become: yes
ansible_become_method: enable

Few things to consider

'command: date' - Ansible prints out the current date and time and pass it as the Git commit message. So, we can easily find out when a config change was made.
'delegate_to: localhost' - We are telling Ansible to run the commands on the localhost
'chdir:' - Change the directory

You can remove unwanted lines from the configuration file by using Ansible 'lineinfile' module.

For more info: https://packetswitch.co.uk/ncm-ansible-git/
