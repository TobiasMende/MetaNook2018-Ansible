Vagrant.require_version ">= 2.0"

cluster = {
  "lb01.vagrant.test" => { :primary => true },
  "app01.vagrant.test" => { :primary => false },
  "app02.vagrant.test" => { :primary => false },
  "db01.vagrant.test" => { :primary => false }
}

Vagrant.configure(2) do |config|

  cluster.each_with_index do |(hostname, info), index|
    config.landrush.enabled = true

    config.vm.define hostname, primary: info[:primary] do |c|
      c.vm.box = "ubuntu/trusty64"
      c.vm.hostname = hostname

      c.ssh.forward_agent = true
      c.ssh.insert_key = false

      c.vm.provider "virtualbox" do |vb|
        vb.memory = "512"
      end

#      c.vm.provision "ansible" do |ansible|
#        ansible.playbook = "vagrant.yml"
#      end
    end # end config

  end # end cluster
  
end