# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

config.vm.provision "shell", path: "bootstrap.sh"
#config.vm.provision "file", source: "docker-ce.repo", destination: "/etc/yum.repos.d/docker-ce.repo"
#config.vm.provision "file", source: "kubernetes.repo", destination: "/etc/yum.repos.d/kubernetes.repo"
#Provision Master
 config.vm.define "master" do |master|
  master.vm.box = "scottharwell/fedora-35-aarch64" 
  master.vm.hostname = "master.example.com"
  master.vm.provision "shell", path: "bootstrap_master.sh" 
end

   config.vm.provider "parallels" do |vb|
     vb.memory = "1024"
   end
=begin
=end
#Provision Worker
#NodeCount = 3
# Kubernetes Worker Nodes

#Provision Worker
NodeCount = 2
# Kubernetes Worker Nodes
  (1..NodeCount).each do |i|
    config.vm.define "worker#{i}" do |workernode|
      workernode.vm.box = "scottharwell/fedora-35-aarch64"
      workernode.vm.hostname = "worker#{i}.example.com"
      workernode.vm.provision "shell", path: "bootstrap_worker.sh"
	end
  end
config.vm.provider "paralles" do |vb|
	vb.memory = "1024" 
end  
end
