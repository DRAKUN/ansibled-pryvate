
Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  config.vm.define "private-pip"

  config.vm.provision "ansible" do |ansible|
    ansible.groups = {
        "pip-host" => ["private-pip"],
        "all_groups:children" => ["pip-host"]
    }
    ansible.limit = "all,localhost"
    ansible.playbook = "feed-static-pip-repository.yml"
  end
end
