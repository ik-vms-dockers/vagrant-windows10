## Windows 10 w/ Edge

```bash
$ vagrant up
```

## First `vagrant up`

A VirtualBox GUI will open automatically.

From the VirtualBox GUI:

- Enable Remote Desktop
- Change network type to: **Private**
- Run `winrm.bat` as an Administrator.

From your host machine:

- Run `vagrant halt` to temporarily stop the box.
- Edit the `Vagrantfile`. Please set `vb.gui = false`.
- Install an RDP client for future connections:
  - `brew cask install microsoft-remote-desktop-beta`

## Subsequent Startups

```bash
vagrant up && vagrant rdp
```
