Vagrant.configure(2) do |config|
  config.vm.box = 'Microsoft/EdgeOnWindows10'

  config.vm.communicator = 'winrm' # See: <http://jas.xyz/1QHAabF>
  config.winrm.username = "IEUser" # Default Modern.ie Windows username.
  config.winrm.password = "Passw0rd!" # Default Modern.ie password.

  config.vm.network :forwarded_port, guest: 5985, host: 5985, id: 'winrm', auto_correct: true
  config.vm.network :forwarded_port, guest: 3389, host: 3389, id: 'rdp', auto_correct: true

  config.vm.provider "virtualbox" do |vb|
    vb.gui = true # Comment this line if using RDP.
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--vram", "256"]
    vb.customize ["modifyvm", :id, "--cpus", "2"]
  end
end
