Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"

  [["alice", "192.168.56.10"], ["bob", "192.168.56.11"], ["charlie", "192.168.56.12"]].each do |machineName, ipAddr|
    config.vm.define "#{machineName}" do |i|
      i.vm.network "private_network", ip: "#{ipAddr}"
    end
  end

  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 1
  end
end
