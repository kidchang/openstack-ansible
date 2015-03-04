# openstack-ansible
Ansible playbooks for Openstack juno release

## Provision

### Prerequisites:

* Vagrant
* Oracle VM Virtualbox
* Ansible >= 1.6.0
* Import this trusty vagrant box: [ubuntu/trusty64](https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box)

`pip install ansible`

`vagrant box add ubuntu/trusty64 https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box `

`git clone https://github.com/kidchang/openstack-ansible`

and run

`vagrant up --provision`

For debugging, when VMs are running, do vagrant ssh { node_name} (e.g: vagrant ssh controller)

To rerun, when VMs are running, do vagrant provision { node_name} (e.g: vagrant provision controller)

### Usage:

* Once deployment is up and running, you can visit the dashboard by visit http://{{ controller ip }}/horizon in the browser.

* You can also "vagrant ssh controller" and "source /opt/admin-openrc.sh"; then you are able to run openstack command lines.

### References:
* https://github.com/openstack-ansible/openstack-ansible

* https://github.com/yunlzheng/ansible-openstack

* http://docs.openstack.org/openstack-ops/content/upgrade-icehouse-juno.html

> Note: For inventory and vm config changes, edit Vagrantfile
