### Vagrant

Vagrant is a tool for building and maintaining portable software development environments. Under the hood, the vagrant creates the VM using the provider (virtualizers). I'm using VirtualBox as a virtualizer. You can use docker, VMWare Hyper-V as well.


### Useful commands
```shell
# Initialize vagrant file
$> vagrant init

# Spin up machine
$> vagrant up
# If you are using mentioned Vagrantfile it will create 3 VMs.

# Apply changed configuration
$> vagrant reload

# SSH to VM
$> vagrant ssh bob 
# password is vagrant

# Destroy all VMs
$> vagrant destroy 
```
