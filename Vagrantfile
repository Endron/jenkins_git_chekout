# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.define "git" do |git|
    git.vm.box = "ubuntu/trusty64"
  end
  config.vm.define "jenkins" do |jenkins|
    jenkins.vm.box = "ubuntu/trusty64"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.groups = {
      "git-servers" => ["git"],
      "build-servers" => ["jenkins"]
    }

    ansible.playbook = "playbook.yml"
  end
end
