Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = 512
    vb.cpus = 1
  end



config.vm.define "wordpress" do |wordpress|
  wordpress.vm.box = "ubuntu/trusty64"
  wordpress.vm.network "public_network", ip: "192.168.1.24"
  wordpress.vm.provision "shell",
      inline: "cat /vagrant/configs/id_bionic.pub >> .ssh/authorized_keys"
  wordpress.vm.provision "shell", inline: "apt-get update"
  wordpress.vm.provider "virtualbox" do |m|
    m.memory = 1024
    m.name =  "wordpress_com_ansible"
  end
end

config.vm.define "mysql" do |mysql|
  mysql.vm.box = "ubuntu/trusty64"
  mysql.vm.network "public_network", ip: "192.168.1.28"
  mysql.vm.provision "shell",
      inline: "cat /vagrant/configs/id_bionic.pub >> .ssh/authorized_keys"
  mysql.vm.provision "shell", inline: "apt-get update"
  mysql.vm.provider "virtualbox" do |m|
    m.memory = 1024
    m.name =  "mysql"
  end
end


  config.vm.define "ansible" do |ansible|
    ansible.vm.network "public_network", ip: "192.168.1.26"

    ansible.vm.provision "shell",
      inline: "cp /vagrant/id_bionic /home/vagrant && \
      chmod 600 /home/vagrant/id_bionic && \
      chown vagrant:vagrant /home/vagrant/id_bionic" 

    ansible.vm.provision "shell",
            inline: "apt-get update && \
                     apt-get install -y software-properties-common && \
                     apt-add-repository --yes --update ppa:ansible/ansible && \
                     apt-get install -y ansible"
  end





end





