Vagrant.configure("2") do |config|

  config.vm.define "loadbalancer" do |loadbalancer|
    loadbalancer.vm.box = "ubuntu/focal64"
    loadbalancer.vm.hostname = "lb"
    loadbalancer.vm.network  :private_network, ip: "192.168.33.10"
    loadbalancer.vm.provider "virtualbox" do |v|  
      v.memory = 1024  
      v.cpus = 1
    end
  end

  (1..2).each do |i|
    config.vm.define "worker#{i}" do |worker|
      worker.vm.box = "ubuntu/focal64"
      worker.vm.hostname = "worker#{i}"
      worker.vm.network  :private_network, ip: "192.168.33.1#{i}"
      worker.vm.provider "virtualbox" do |v|  
        v.memory = 512  
        v.cpus = 1
      end
    end
  end

end