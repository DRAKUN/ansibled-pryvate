
Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  config.vm.define "private-pip"

  config.vm.provision "ansible" do |ansible|
    ansible.groups = {
        "python-repos" => ["private-pip"],
        "all_groups:children" => ["python-repos"]
    }
    ansible.limit = "all,localhost"
    ansible.playbook = "configure-private-repo.yml"
  end
end
