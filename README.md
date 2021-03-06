# Packer Example - CentOS 7 minimal Vagrant Box using Ansible provisioner

**Current CentOS Version Used**: 7.0

This example build configuration installs and configures CentOS 7 x86_64 minimal using Ansible, and then generates a Vagrant box file for use with VirtualBox.

The example can be modified to use more Ansible roles, plays, and included playbooks to fully configure (or partially) configure a box file suitable for deployment for development environments.

## Requirements

The following software must be installed/present on your local machine before you can use Packer to build the Vagrant box file:

  - [Packer](http://www.packer.io/)
  - [Vagrant](http://vagrantup.com/)
  - [VirtualBox](https://www.virtualbox.org/)
  - [Ansible](http://docs.ansible.com/intro_installation.html)

You will also need the [`geerlingguy.packer-rhel`](https://galaxy.ansible.com/list#/roles/671) and [`geerlingguy.nfs`](https://galaxy.ansible.com/list#/roles/463) Ansible roles installed, which can be installed using the command `ansible-galaxy install geerlingguy.packer-rhel` and `ansible-galaxy install geerlingguy.nfs`, respectively.

If you have the roles installed somewhere besides the default roles path on your machine (`/etc/ansible/roles`), you will need to edit the `role_paths` inside `centos65.json` to match that location. If you don't have Ansible installed (perhaps you're using a Windows PC?), you can simply [clone the repository from GitHub](https://github.com/geerlingguy/ansible-role-packer-rhel), and update the `role_paths` variable to match the location of the cloned role.

## Usage

Make sure all the required software (listed above) is installed, then cd to the directory containing this README.md file, and run:

    $ packer build centos7.json

After a few minutes, Packer should tell you the box was generated successfully.

## License

MIT license.

## Author Information

Created in 2014 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).
