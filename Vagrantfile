Vagrant.configure(2) do |config|

    config.vm.define "website" do |website|
       website.vm.box = "ubuntu/xenial64"
       website.vm.hostname = "WebsiteVM"
       website.vm.network "private_network", ip: "192.168.33.15"
       website.vm.provider :virtualbox do |vb|
         vb.memory = "512"
         vb.cpus = "1"
       end
       website.vm.provision "shell", inline: <<-SHELL
            apt update
            apt install -y nginx
       SHELL
     end
     config.vm.define "database" do |database|
       database.vm.box = "ubuntu/xenial64"
       database.vm.hostname = "DatabaseVM"
       database.vm.network "private_network",ip:"192.168.33.50"
       database.vm.provider :virtualbox do |vb|
         vb.memory = "1024"
         vb.cpus = "1"
       end
       database.vm.provision "shell", inline: <<-SHELL
            apt update
            apt install -y mysql-server
       SHELL
     end


   end

  