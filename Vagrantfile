# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure('2') do |config|

  config.vm.define 'node1' do |node1|
    node1.vm.box = 'centos/7'
    node1.vm.hostname = 'Node1'
    node1.vm.network "private_network", ip: "172.28.128.11"
  end

  config.vm.define 'node2' do |node2|
    node2.vm.box = 'centos/7'
    node2.vm.hostname = 'node2'
    node2.vm.network "private_network", ip: "172.28.128.12"
  end

  config.vm.define 'node3' do |node3|
    node3.vm.box = 'centos/7'
    node3.vm.hostname = 'node3'
    node3.vm.network "private_network", ip: "172.28.128.13"
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "ansible/provision.yml"
    ansible.become = true
  end
  config.vm.synced_folder "ansible", "/home/vagrant/ansible", mount_options: ["dmode=775,fmode=600"]
end
#https://www.vagrantup.com/docs/provisioning/ansible_intro.html
# config.vm.define 'k8snode2' do |k8snode2|
#   k8snode2.vm.box = 'centos/7'
#   k8snode2.vm.hostname = 'k8snode2'
#   k8snode2.vm.network "private_network", ip: "172.28.128.120"
#   k8snode2.vm.provider :virtualbox do |vb|
#          vb.customize ['modifyvm', :id,'--memory', '2048']
#   end
# end
