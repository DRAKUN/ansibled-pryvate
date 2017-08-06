
Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  config.vm.define "pryvate-host"

  config.vm.provision "ansible" do |ansible|
    ansible.groups = {
        "pryvate-repos" => ["pryvate-host"],
        "pryvate-clients" => ["pryvate-host"],
        "all_groups:children" => ["pryvate-repos", "pryvate-clients"]
    }
    ansible.limit = "all,localhost"
    ansible.playbook = "configure-pryvate-repos.yml"
#    ansible.playbook = "configure-pryvate-clients.yml"
  end
end
