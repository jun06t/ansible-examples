# ansible-examples
Ansible examples

# Usage

## On Vagrant
Edit ``Vagrantfile``.

```
  config.vm.define :web1 do |web|
    web.vm.network :private_network, ip: "192.168.33.10"
    web.vm.provider "virtualbox" do |vb|
      vb.memory = "1048"
    end
  end

  config.vm.define :web2 do |web|
    web.vm.network :private_network, ip: "192.168.33.11"
    web.vm.provider "virtualbox" do |vb|
      vb.memory = "1048"
    end
  end

  config.vm.define :web3 do |web|
    web.vm.network :private_network, ip: "192.168.33.12"
    web.vm.provider "virtualbox" do |vb|
      vb.memory = "1048"
    end
  end
```

Create inventory file like this.

```
[elasticsearch]
web1
web2
web3
```

Then run ansible-playbook.

```
$ ansible-playbook -i inventory/local elasticsearch.yml 
```
