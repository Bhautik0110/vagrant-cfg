Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
  config.vm.box_version = "1.0.282"

  [["alice", "192.168.56.10"], ["bob", "192.168.56.11"], ["charlie", "192.168.56.12"], ["das", "192.168.56.13"]].each do |machineName, ipAddr|
    config.vm.define "#{machineName}" do |i|
      i.vm.network "private_network", ip: "#{ipAddr}"
      i.vm.hostname = "#{machineName}"
    end
  end

  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 1
  end
end
