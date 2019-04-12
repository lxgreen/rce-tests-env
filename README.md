# rce-tests-env

## Vagrant-based environment

[Vagrant](https://www.vagrantup.com/)-based dev environment for [RCE](https://github.com/wix-incubator/rich-content) testing

### Dependencies

- [Vagrant](https://www.vagrantup.com/downloads)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

### Setup

After dependencies are installed, run in termianal:

```bash
git clone https://github.com/lxgreen/rce-tests-vagrant.git

cd rce-tests-vagrant

cp ~/.ssh/id_rsa

vagrant up
```

**Note**: the 'rich-content-plugin-gallery' build requires the Wix VPN connection on the host machine, and the SSH key as well.

At this step, the Vagrant will download and run the Ubuntu VM. Please wait for the initial setup to finish. Once it is done, you can login to the VM with _vagrant/vagrant_ credentials.

Before you go, it is good to take a snapshot:

```bash
vagrant snapshot save initial
```

Later, you can `restore` it.

Now you have a VM with fully configured node environment. Run [get-rce](https://github.com/lxgreen/get-rce/blob/master/README.md) with required parameters to fetch, build and run RCE examples. The running `editor` and `viewer` examples are available on `localhost:30000` and `localhost:30001`, respectively.
