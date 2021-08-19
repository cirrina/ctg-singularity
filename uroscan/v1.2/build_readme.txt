#!/bin/bash
myContainer="uroscan-v1.2"
version="v1.2"
#ssh octopoda.local




echo "scp -P 2222 -i /Users/david/vm-singularity/.vagrant/machines/default/virtualbox/private_key  ~/scripts/ctg-singularity/uroscan/${version}/bin/Linux_x86_64_static/STAR vagrant@127.0.0.1:/home/vagrant/"

echo "scp -P 2222 -i /Users/david/vm-singularity/.vagrant/machines/default/virtualbox/private_key  ~/scripts/ctg-singularity/uroscan/${version}/environment.yml vagrant@127.0.0.1:/home/vagrant/"
echo "scp -P 2222 -i /Users/david/vm-singularity/.vagrant/machines/default/virtualbox/private_key  ~/scripts/ctg-singularity/uroscan/${version}/uroscan.def vagrant@127.0.0.1:/home/vagrant/"

## BUILD
echo  "vagrant global-status"

## vagrant up 9d5f316

echo "Start the vagrant virual envronment with:  vagrant ssh 9d5f316"
echo "Build the singularity container with:  sudo -E singularity build uroscan.sif uroscan.def"
# exit


## after completion
echo "scp -P 2222 -i /Users/david/vm-singularity/.vagrant/machines/default/virtualbox/private_key vagrant@127.0.0.1:/home/vagrant/uroscan-v1.1.sif ."

ehco "rsync -av rsync -av david@octopoda.local:/Users/david/scripts/ctg-singularity/uroscan/v1.1/uroscan-v1.1.sif ~/scripts/ctg-singularity/uroscan/v1.1'
