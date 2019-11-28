# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "4096"
    vb.cpus = "2"
  end

  config.vm.define "minikube" do |minikube|
    minikube.vm.box = "ubuntu/xenial64"
    minikube.vm.hostname = "minikube"
    minikube.vm.network "private_network", ip: "192.168.33.33"
    minikube.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd; sudo apt install -y python-minimal", run: "always"
   end

end
