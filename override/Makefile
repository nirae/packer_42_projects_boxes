.PHONY: all re build vagrant-add vagrant-remove up clean hard-clean

all : build vagrant-add up

re : clean vagrant-remove all

build:
	packer build override.json

vagrant-add:
	vagrant box add 42_override override-amd64-virtualbox.box

vagrant-remove:
	vagrant box remove 42_override --all

up:
	mkdir -p vm
	cd vm && vagrant init 42_override && vagrant up

clean: vagrant-remove
	rm -rf override-amd64-virtualbox.box
	cd vm && vagrant destroy -f
	rm -rf vm