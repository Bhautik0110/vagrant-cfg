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

# Stop / Shutdown machine
$> vagrant halt
```


### k3s instruction
```
# Boostrap the cluster
# Below command run in master
# This is NOT HA implementation!!
$> curl -sfL https://get.k3s.io | K3S_KUBECONFIG_MODE="644" INSTALL_K3S_EXEC="server --disable=traefik --node-external-ip=<IP>" sh - 
copy master node token 
$> sudo cat /var/lib/rancher/k3s/server/token

# Below command run in worker.
$> curl -sfL https://get.k3s.io | K3S_URL=https://<MASTER_SERVER_IP>:6443 K3S_TOKEN="<REPLACE_TOKEN>" INSTALL_K3S_EXEC="--node-external-ip=<IP>" sh -

# Give worker label to worker nodes
$> kubectl label node <node_name> node-role.kubernetes.io/worker=worker
```
