VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu/xenial64"

  config.vm.network :forwarded_port, guest: 5000, host: 5000, auto_correct: true

  config.vm.provision :ansible do |ansible|
    ansible.become = true
    ansible.playbook = "tests/role.yml"
    ansible.raw_arguments = ["--extra-vars=ansible_python_interpreter=/usr/bin/python3"] #use python3
  end

end
