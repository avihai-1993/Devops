How to Use the Playbook
Set up your environment: Ensure Ansible is installed on your control machine and you can connect to all the target nodes via SSH. The user defined in group_vars/all.yml must have passwordless sudo access.

Create the files: Create the directory structure as shown in the immersive document.

.
├── hosts.ini
├── site.yml
├── group_vars
│   └── all.yml
└── roles
    ├── admin
    │   └── tasks
    │       └── main.yml
    ├── cni
    │   └── tasks
    │       └── main.yml
    ├── common
    │   └── tasks
    │       └── main.yml
    ├── manager
    │   └── tasks
    │       └── main.yml
    └── worker
        └── tasks
            └── main.yml
Update the variables: Edit hosts.ini with your server IPs and update the ansible_user in group_vars/all.yml to match your SSH username.

Run the playbook: From your control machine, execute the following command:

Bash

ansible-playbook -i hosts.ini site.yml
This playbook will first prepare all nodes, then initialize the manager node, join the workers, deploy the CNI, and finally, configure the admin node to manage the cluster. After the playbook completes, you should be able to run kubectl get nodes on your admin node and see all the nodes in a Ready state.
