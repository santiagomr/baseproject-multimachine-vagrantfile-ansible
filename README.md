# Baseproject Multi-Machine Vagrantfile Ansible

Typical structure of a multi-machine vagrantfile project using the ansible provisioner, to start trying new ideas quickly.

The vagrantfile includes constants to parameterize: total number of nodes (machines), base box, IP range of the private network and number of cores and RAM assigned to each node.

The ansible provisioner is invoked only when all nodes are up and running, running an easily extensible playbook that reads variables defined for the particular environment. The sample playbook `basic_configuration.yml` performs an elementary configuration of users, passwords and authorized keys to authenticate.

## Requirements

For the execution of this project it is necessary to have the following tools installed in your host:
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads) (Tested on version >= 6.1.X)
- [Vagrant](https://www.vagrantup.com/downloads) (Tested on version >= 2.2.X)
- [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) (Tested on version >= 2.10.X)


## How to use

Once the repository is cloned, simply go to the root directory of the project.

Duplicate and rename the `vars.yml.example` file to `vars.yml`. In it you can define the variables according to what you need.

```shell
baseproject-multimachine-vagrantfile-ansible git:(master) ✗ cp vars.yml.example vars.yml && nano vars.yml
```

Edit the constants in the `Vagrantfile` if necessary (total number of nodes, base box, IP range of the private network and number of cores and RAM assigned to each node)

```shell
baseproject-multimachine-vagrantfile-ansible git:(master) ✗ nano Vagrantfile
```

Finally, provision the environment:
```shell
baseproject-multimachine-vagrantfile-ansible git:(master) ✗ vagrant up
```

That's it! You can now log into your nodes via vagrant (`vagrant ssh node1`) or directly via SSH with the correct username and IP (`ssh ubuntu@192.168.60.11`).


## License

GNU GPLv3


## Author Information

[@santiagomr](https://github.com/santiagomr)