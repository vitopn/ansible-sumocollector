# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|
  config.vm.define "ansible-sumocollector-ubuntu" do |vagrant1|
        vagrant1.vm.box = "ubuntu/trusty64"
        vagrant1.vm.hostname = "ansible-sumocollector-ubuntu"
        vagrant1.vm.provision "ansible" do |ansible|
            ansible.playbook = "test.yml"
            ansible.verbose = 'v'
            #ansible.extra_vars = 'test_vars.yml'
            #ansible.inventory_path = 'vagrant-inventory'
            #ansible.host_key_checking = false
        end
    end
    config.vm.define "ansible-sumocollector-centos" do |vagrant2|
        vagrant2.vm.box = "centos/7"
        vagrant2.vm.hostname = "ansible-sumocollector-centos"
        vagrant2.vm.provision "ansible" do |ansible|
            ansible.playbook = "test.yml"
            ansible.verbose = 'v'
            #ansible.extra_vars = 'test_vars.yml'
            #ansible.inventory_path = 'vagrant-inventory'
            #ansible.host_key_checking = false
        end
    end
end
