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

### Few things to note:

* When ansible finishes provisioning, do: `vagrant ssh controller` and go to `/user/share/openstack-dashboard` and run `python manage.py runserver 0.0.0.0:8000`

* Open a browser and type in `http://controller:8000`, enter username and password. It will go to `http://controller:8000/horizon`, this page does not exist, removing "horizon" in the address will solve this issue.

* If you don't see "nova" in "availability zone", do `ansible ssh controller` and `sudo service nova-conductor start` to manually bring it up.

* There's still an issue with bringing up instances. It consistently complains that "no valid host was found". They maybe ralated to neutron.

### References:
* https://github.com/openstack-ansible/openstack-ansible

* https://github.com/yunlzheng/ansible-openstack

* http://docs.openstack.org/openstack-ops/content/upgrade-icehouse-juno.html

> Note: For inventory and vm config changes, edit Vagrantfile
