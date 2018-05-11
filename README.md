# docker-volumes
An Ansible Docker volume role for yum,apt and pip installation

It includes volume's removal when not defined in the list

## Prerequisites

python >= 2.6

docker-py >= 1.10.0 

Check with 
```
python -c "import docker; print docker.__version__"
```
The docker server >= 1.9.0

## Usage

Include the folder in your roles directory. You can edit the configuration in, for example, your group_vars, like this:

```
 docker_volumes:
   - name: internal
     state: present
     labels: 
     force: True        #  With state "present" volume will be deleted and recreated if the volume already exist and the driver, driver options or labels differ    
   - name: external
     state: absent 
     force: True
```
## Parameters

Parameters are some of ansible's module docker_volume parameters that fit my needs(http://docs.ansible.com/ansible/latest/modules/docker_volume_module.html)
```
#global params
playbook_debug: 
enable_remove_unwanted_volumes:  
# network definition 
  - name: 
    labels: 
    state: 
    force: 
```

## Author

STROHL Matthieu <postmaster@smartdeploy.io>

## License

MIT