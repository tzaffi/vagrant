# vagrant

Thank you [@santosh79](https://github.com/santosh79/) for your vagrant knowledge share and for most of the code
included in this project!!!

## I'm putting my public vagrant files here. These are:

* `tzaffi/ubuntujava71` - this is a box we use in our local development environment. It is **NOT MEANT FOR PRODUCTION**.
    * which is based on `marruda/trusty64-java-all` and consists of:
        * Ubuntu 14.04.2 (trusty)
        * Java 1.7.79
        * Maven 3.0.5
        * Git 1.9.1
    * and consists of the additional packages
        *  g++ 
        *  make 
        *  python-setuptools 

        *  python-software-properties
        *  curl 
        *  build-essential
        *  emacs
        *  tomcat7
        *  tomcat7-admin
        *  node.js
        *  mysql (with standard root credentials)


## NOTE: You will still need to configure your own forwarded ports with a command such as
```sh
  config.vm.network "forwarded_port", guest: 80, host: 8081
```
or by calling the provided `setup_forwarded_ports` command

## I (and similarly you) push these vagrant boxes to atlas by using as follows:
1. Make sure that the vagrant image is named with a command such as 
```
  config.vm.provider "virtualbox" do |v|
    v.name = "ubuntujava71"
  end
```

2. Bring the box up with `vagrant up --provision`

3. Package the box with something like `vagrant package --base ubuntujava71 --output ubuntujava71.box --vagrantfile Vagrantfile`

4. Follow the [instructions for creating boxes via the Web UI](https://atlas.hashicorp.com/help/vagrant/boxes/create#creating-boxes-via-the-atlas-web-interface)

