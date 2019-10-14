gwc_vm_images
=========
Repository for GWC base VM images

Requirements
------------
The following applications must be installed on the host where the VM image is being built
* Ansible - Image configuration
* Packer - Automation tool
* QEMU - Image builder

Directories
--------------
* ansible - contains ansible playbooks for building the base image
* http - contains first boot instructions passed to the VM
* docs - Instruction documents to build, test, deploy VM images

Dependencies
------------
* NectarCloud Openstack credentials - To upload VM images
* TBA

Example Executions
----------------
* [Image development - Ansible, Vagrant](./docs/IMAGE_DEVELOPMENT.md)
* [Image building - Packer](./docs/IMAGE_BUILD.md)
* [Image Submission - Openstack](./docs/IMAGE_SUBMISSION)

License
-------
* [GPU License](./LICENCE.md)
