#https://stackoverflow.com/questions/64905347/how-does-ansible-find-the-location-of-inventory-group-vars-all-yaml-user-vars

commands:
ansible-playbook -v -i inventories/stage --extra-vars server_env_group="stageservers" main_playbook.yml
ansible-playbook -v -i inventories/test --extra-vars server_env_group="testservers" main_playbook.yml

Structure:

.
├── inventories
│   ├── stage
│   │   ├── group_vars
│   │   │   └── stageservers.yml
│   │   └── host
│   └── test
│       ├── group_vars
│       │   └── testservers.yml
│       └── hosts
├── main_playbook.yml
└── roles
    └── common
        └── tasks
            └── main.yml


