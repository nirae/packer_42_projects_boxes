.PHONY: all re build vagrant-add vagrant-remove up clean hard-clean

all : build vagrant-add up

re : clean vagrant-remove all

build:
	packer build rainfall.json

vagrant-add:
	vagrant box add 42_rainfall rainfall-amd64-virtualbox.box

vagrant-remove:
	vagrant box remove 42_rainfall --all

up:
	mkdir -p vm
	cd vm && vagrant init 42_rainfall && vagrant up

clean: vagrant-remove
	rm -rf rainfall-amd64-virtualbox.box
	cd vm && vagrant destroy -f
	rm -rf vm