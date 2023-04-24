
VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # Use the same key for each machine
  config.ssh.insert_key = false
  # config.vm.network "public_network"
  config.vm.provision "file", source: "C:\\data\\af\\", destination: "/home/vagrant/"
  # config.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/me.pub"
  config.vm.provider "virtualbox" do |v|
    v.memory = 6000
  
end

config.vm.define "v" do |v|
  v.vm.box = "centos/7"
  v.vm.hostname = "agent"
  v.vbguest.installer_options = { allow_kernel_upgrade: true }
  v.vm.synced_folder "C:/data/vagrant/playbooks", "/vagrant", type: "virtualbox"
  v.vm.network "private_network", ip: "192.168.121.22"
  # # v.vm.network "public_network", ip: "192.168.121.110"
  v.vm.network "forwarded_port", guest: 8793, host: 8880
  v.vm.network "forwarded_port", guest: 8080, host: 8080
  # Postgres
  v.vm.network "forwarded_port", guest: 5432, host: 5430
  # Redis
  v.vm.network "forwarded_port", guest: 6379, host: 6370
  ## Health check port
  v.vm.network "forwarded_port", guest: 8974, host: 8972
  
   ## Logging port
   v.vm.network "forwarded_port", guest: 8793, host: 8792
  # celery flower port
  v.vm.network "forwarded_port", guest: 5555, host: 5552

  ## statsd port
  v.vm.network "forwarded_port", guest: 8125, host: 8122

  ## Elastic Search
  v.vm.network "forwarded_port", guest: 9200, host: 9200
  v.vm.network "forwarded_port", guest: 9300, host: 9300

  ## Kibana
  v.vm.network "forwarded_port", guest: 5601, host: 5601

end
config.vm.define "v8" do |v|
    v.vm.box = "centos/7"
    v.vm.hostname = "backup"
    v.vbguest.installer_options = { allow_kernel_upgrade: true }
    v.vm.synced_folder "C:/data/vagrant/playbooks", "/vagrant", type: "virtualbox"
    v.vm.network "private_network", ip: "192.168.121.110"
    ##v.vm.network "public_network", ip: "192.168.121.8"
    v.vm.network "forwarded_port", guest: 8793, host: 8889
    v.vm.network "forwarded_port", guest: 8080, host: 8089
    ##Postgres
    v.vm.network "forwarded_port", guest: 5432, host: 5438
    ##Redis
    v.vm.network "forwarded_port", guest: 6379, host: 6378
    ## Health check port
    v.vm.network "forwarded_port", guest: 8974, host: 8978
    
     ## Logging port
     v.vm.network "forwarded_port", guest: 8793, host: 8798
    ## celery flower port
    v.vm.network "forwarded_port", guest: 5555, host: 5550

     ## statsd port
     v.vm.network "forwarded_port", guest: 8125, host: 8128

     ## Elastic Search
    v.vm.network "forwarded_port", guest: 9200, host: 9201
    v.vm.network "forwarded_port", guest: 9300, host: 9301

    ## Kibana
    v.vm.network "forwarded_port", guest: 5601, host: 5602
    v.vm.network "forwarded_port", guest: 5000, host: 5008
  end
  
  
  
  config.vm.define "v1" do |v|
    v.vm.box = "centos/7"
    v.vm.hostname = "master"
    v.vbguest.installer_options = { allow_kernel_upgrade: true }
    v.vm.synced_folder "C:/data/vagrant/playbooks", "/vagrant", type: "virtualbox"
    # v.vm.network "private_network", ip: "192.168.10.11"
    v.vm.network "private_network", ip: "192.168.121.11"
    v.vm.network "forwarded_port", guest: 8793, host: 8891
    v.vm.network "forwarded_port", guest: 8080, host: 8091
    # Postgres
    v.vm.network "forwarded_port", guest: 5432, host: 5431
    # Redis
    v.vm.network "forwarded_port", guest: 6379, host: 6379
    ## Health check port
    v.vm.network "forwarded_port", guest: 8974, host: 8971
  
     ## Logging port
     v.vm.network "forwarded_port", guest: 8793, host: 8791
    #celery flower port
    v.vm.network "forwarded_port", guest: 5555, host: 5551

    ## statsd port
    v.vm.network "forwarded_port", guest: 8125, host: 8121
    ## prometheus
    v.vm.network "forwarded_port", guest: 9090, host: 9091

     ## Elastic Search
     v.vm.network "forwarded_port", guest: 9200, host: 9203
     v.vm.network "forwarded_port", guest: 9300, host: 9303
 
     ## Kibana
     v.vm.network "forwarded_port", guest: 5601, host: 5603

     ## Kibana
     v.vm.network "forwarded_port", guest: 3000, host: 3000

     ## Kibana
     v.vm.network "forwarded_port", guest: 1024, host: 1024
  end
  
  

end