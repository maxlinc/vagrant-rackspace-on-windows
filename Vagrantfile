Vagrant.configure("2") do |c|
  #c.vm.provision "chef_solo" do |chef|
  #  chef.add_recipe "apache"
  #end

  c.vm.box = "dummy"
  c.vm.box_url = "https://github.com/mitchellh/vagrant-rackspace/raw/master/dummy.box"
  # This was set by kitchen-vagrant, but not sure it makes sense here...
  c.vm.synced_folder ".", "/vagrant", disabled: true

  c.vm.define :windows do |windows|
    windows.vm.provision "shell", inline: 'Write-Output "Hello World"'
    windows.vm.communicator = :winrm
    windows.winrm.username = 'Administrator'
    windows.winrm.password = ENV['WINRM_PASSWORD']
    windows.vm.provider :rackspace do |p|
      p.image = 'Windows Server 2012'
      p.personality = [
        {
          :path => 'C:\\cloud-automation\\bootstrap.cmd',
          :contents => Base64.encode64(File.read('bootstrap.cmd'))
        }
      ]
    end
  end

  c.vm.define :ubuntu do |ubuntu|
    ubuntu.vm.provider :rackspace do |p|
      p.image = 'Ubuntu 13.10 (Saucy Salamander) (PVHVM)'
    end
  end

  c.vm.provider :rackspace do |p|
    p.flavor = "performance1-2"
    p.username = ENV['RAX_USERNAME']
    p.api_key = ENV['RAX_API_KEY']
  end
end
