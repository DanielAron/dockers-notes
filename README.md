-- THIS IS MY NOTES ON A RAMP UP EFFORT TESTING THE DOCKER TECHONOGY AND BLUEMIX ---

# Install vagrant
...
# Install vagrant guest addition
> vagrant plugin install vagrant-vbguest


>vagrant init ubuntu/trusty64
>vagrant up
>vagrant ssh
# Install Docker:
>wget -qO- https://get.docker.com/ | sh
>sudo usermod -aG docker vagrant

# Expose vagrant guest ip to host:
update VagrantFile and uncomment the next line:
       config.vm.network "private_network", ip: "192.168.33.10"

# Walk throu the docker tutorial:
     Check docker-log.md

# Bluemix Containers:
## Instalation: https://www.ng.bluemix.net/docs/containers/container_cli_ov.html

### Install cf cli
Download .deb from: https://github.com/cloudfoundry/cli/releases
> sudo dpkg -i cf-cli-installer_6.14.1_x86-64.deb 

### Install plugin:
>cf install-plugin https://static-ice.ng.bluemix.net/ibm-containers-linux_x64

### Login:
cf login -a api.ng.bluemix.net

### Bluemix tutorial
>cf ic init

GOOO AND PLAY WITH DOKERS ON BLUEMIX!!!

>cf ic ps
>cf ic images
>cf ic ip list
>cf ic namespace get

>docker tag _image_tag_ registry.ng.bluemix.net/_your_namespace_/_image_tag_ 
>docker push registry.ng.bluemix.net/_your_namespace_/_image_tag_
>docker push registry.ng.bluemix.net/daniel/ubuntu:14.04

>cf ic run -d -P registry.ng.bluemix.net/daniel/nginx:new
>cf ic ps
>cf ic ip list
>cf ic ip bind [134.168.14.19] [2aae5002-017]
>cf ic exec -it 2aae5002-017 bash
