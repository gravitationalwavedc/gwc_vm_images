Vagrant.configure("2") do |config|
  
    # Ubuntu 18.04 (bionic) with Kubernetes
    config.vm.define "ubuntu1804-kubernetes" do |c|
      c.vm.box = "generic/ubuntu1804"
      config.vm.provider "virtualbox" do |v, override|
        override.vm.box = "generic/ubuntu1804"
      end
      c.vm.provision "ansible" do |ansible|
        ansible.compatibility_mode = "2.0"
        ansible.extra_vars = { nectar_test_build: true,
                               murano_image_type: "Kubernetes",
                               nectar_image_name: "Ubuntu 18.04 LTS (Bionic) amd64 (with Kubernetes)",
                               ansible_python_interpreter: "/usr/bin/python3" }
        ansible.config_file = "ansible/ansible.cfg"
        ansible.playbook = "ansible/playbook-kubernetes.yml"
        ansible.tags = "debugme"
        ansible.become = true
      end
      c.vm.provision "shell" do |shell|
        shell.inline = "/usr/nectar/run_tests.sh"
        shell.privileged = false
        shell.env = { "NECTAR_TEST_BUILD": 1 }
      end
    end
  
    config.vm.synced_folder ".", "/vagrant", disabled: true
  
    config.vm.provider :libvirt do |v|
      v.memory = 2048
      v.cpus = 2
      v.machine_virtual_size = 4  # 4GB disk
    end
  
    config.vm.provider :virtualbox do |v|
      v.memory = 2048
      v.cpus = 2
    end
  
  end
  
  # vi: set ft=ruby :
  