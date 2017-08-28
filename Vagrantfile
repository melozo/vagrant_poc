Vagrant.configure("2") do |config|

  config.vm.define "nginx" do |nginx|
    nginx.vm.box_url = "debian/stretch64"
    nginx.vm.box = "debian/stretch64"
    nginx.vm.hostname = "nginx.devops.com"
    nginx.vm.network :private_network, ip: "10.127.0.10"
    nginx.vm.provider "virtualbox" do |v|
    	v.name = "nginx"
    	v.memory = 512
    	v.cpus = 2
    end
    # Ansible
    config.vm.provision "ansible" do |nginx|
    	#ansible.playbook = "ansible/ansible-nginx-role/main-nginx.yml"
    	nginx.playbook = "ansible/nginx.yml"
    	nginx.sudo = true
    end

  end
  
  config.vm.define "php" do |php|
    php.vm.box = "debian/stretch64"
    php.vm.box_url = "debian/stretch64"
    php.vm.hostname = "php.devops.com"
    php.vm.network :private_network, ip: "10.127.0.20"
    php.vm.provider "virtualbox" do |v|
    	v.name = "php"
    	v.memory = 1024
    	v.cpus = 1
    end
    # Ansible
    config.vm.provision "ansible" do |php|
    	php.playbook = "ansible/php.yml"
    	php.sudo = true
    end
  end

  config.vm.define "redis" do |redis|
    redis.vm.box_url = "debian/stretch64"
    redis.vm.box = "debian/stretch64"
    redis.vm.hostname = "redis.devops.com"
    redis.vm.network :private_network, ip: "10.127.0.30"
    redis.vm.provider "virtualbox" do |v|
    	v.name = "redis"
    	v.memory = 256
    	v.cpus = 1
    end
    # Ansible
    config.vm.provision "ansible" do |redis|
        redis.playbook = "ansible/redis.yml"
        redis.sudo = true
    end

  end
end
