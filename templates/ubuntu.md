# [Ubuntu ${UBUNTU_VERSION} ${UBUNTU_TYPE^}](http://www.ubuntu.com/${UBUNTU_TYPE})

## Clean + Minimal + Latest Ubuntu ${UBUNTU_TYPE^} ${UBUNTU_ARCH} base box for [libvirt](https://github.com/vagrant-libvirt/vagrant-libvirt) provider.

---

#### Github repository for bug reports or feature requests:

[https://github.com/ruzickap/packer-templates/](https://github.com/ruzickap/packer-templates/)


## Requirements
* [QEMU-KVM](https://en.wikibooks.org/wiki/QEMU/Installing_QEMU)
* [Vagrant](https://www.vagrantup.com/downloads.html)
* [Vagrant Libvirt Plugin](https://github.com/pradels/vagrant-libvirt#installation)

Here are the steps for latest Fedora/Ubuntu to install Vagrant and vagrant-libvirt + KVM:
\`\`\`
# Fedora
dnf install -y vagrant-libvirt

# Ubuntu
apt install -y libvirt-bin vagrant-libvirt
\`\`\`


## Getting started

Install and connect to the box:

\`\`\`
mkdir ${NAME}
cd ${NAME}
vagrant init ${VAGRANT_CLOUD_USER}/${NAME}
VAGRANT_DEFAULT_PROVIDER=libvirt vagrant up
vagrant ssh
\`\`\`


## Login Credentials

(root password is not set)

* Username: vagrant
* Password: vagrant


## VM Specifications

* Libvirt Provider
* VirtIO dynamic Hard Disk (up to 50 GiB)
* VirtIO Network Interface
* QXL Video Card (SPICE display)


## Configuration

#### Minimal installation - see the [preseed file](https://github.com/ruzickap/packer-templates/blob/master/http/ubuntu-${UBUNTU_TYPE}/preseed.cfg)
(it's very close to official Ubuntu [preseed file](https://help.ubuntu.com/lts/installation-guide/example-preseed.txt))

* en_US.UTF-8
* keymap for standard US keyboard
* UTC timezone
* NTP enabled (default configuration)
* full-upgrade
* unattended-upgrades
* /dev/vda1 mounted on / using ext4 filesystem (all files in one partition)
* no swap
