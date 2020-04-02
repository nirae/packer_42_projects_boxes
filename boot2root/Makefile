.PHONY: all re build vagrant-add vagrant-remove up clean hard-clean

all : build vagrant-add up

re : clean vagrant-remove all

build:
	packer build boot2root.json

vagrant-add:
	vagrant box add 42_boot2root boot2root-amd64-virtualbox.box

vagrant-remove:
	vagrant box remove 42_boot2root --all

up:
	mkdir -p vm
	cd vm && vagrant init 42_boot2root && vagrant up

clean: vagrant-remove
	rm -rf boot2root-amd64-virtualbox.box
	cd vm && vagrant destroy -f
	rm -rf vm