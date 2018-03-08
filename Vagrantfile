Vagrant.configure(2) do |config|
  config.vm.box = 'Microsoft/EdgeOnWindows10';

  config.vm.guest = :windows;
  config.vm.communicator = 'winrm';

  config.winrm.username = 'IEUser';
  config.winrm.password = 'Passw0rd!';

  config.vm.network :private_network, ip: '192.168.10.10';
  config.vm.network :forwarded_port, guest: 3389, host: 3389, id: 'rdp', auto_correct: true;

  config.vm.synced_folder '.', '/vagrant', mount_options: ['defaults'];

  config.vm.provider 'virtualbox' do |vb|
    vb.gui = true;
    vb.customize ['modifyvm', :id, '--memory', '2048'];
    vb.customize ['modifyvm', :id, '--vram', '256'];
    vb.customize ['modifyvm', :id, '--cpus', '2'];
    vb.customize ['modifyvm', :id, '--natdnsproxy1', 'on'];
    vb.customize ['modifyvm', :id, '--natdnshostresolver1', 'on'];
    vb.customize ['guestproperty', 'set', :id, '/VirtualBox/GuestAdd/VBoxService/--timesync-set-threshold', 10000];
  end;
end;
