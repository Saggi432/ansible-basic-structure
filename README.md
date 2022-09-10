Basic Structure of Ansible repository



```
--------ansible-repo
          |
          |
          ----prod(Prod inventory)
          ----dev(Dev Inventory)
          ----vars
               |-vars.yml( Global variables)
               |-oneusers.yml(user specific variables)
          ----oneuser-frontend.yml
          ----oneuser-backend.yml
          ----roles
               |-----------frontend
                              |------tasks----sample.yml
                              |-------Handlers----handlers.yml
                              |-------defaults----defaults.yml
                              |-------files------python.py
                              |-------templates----sample.j2
                              |-------vars-------yaml.yml
                              
                              
 ```
 
 
 oneuser-frontend.yml
 
  ```
  
  - hosts: oneuser-frontend(This is defined in the inventory)
  vars_files:
    - vars/vars.yml
    - vars/oneusers.yml
  roles:
    - frontend
    - backend
  vars:
    - SAMPLE: false(additional overriding variables)

```

