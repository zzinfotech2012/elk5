# For ELK 5.x installation on one server
Vagrant.configure("2") do |config|

  # set timezone
  if Vagrant.has_plugin?("vagrant-timezone")
    config.timezone.value = "EST"
  end

  (1..1).each do |i|
    config.vm.define "elk0#{i}" do |node|
       node.vm.hostname = "elk0#{i}"
       node.vm.box = "centos/7"
       node.vm.network "private_network", ip: "10.10.0.10#{i}"
       node.vm.provider "virtualbox" do |v|
         v.memory = 6144
       end
       node.ssh.private_key_path = "/home/vmuser/.ssh/github-zzinfotech2012"
    end
  end

  config.vm.provision "file", source: "/home/vmuser/.ssh/github-zzinfotech2012.pub", destination: "~/.ssh/authorized_keys"

end

