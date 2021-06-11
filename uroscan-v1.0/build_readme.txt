#!/bin/bash
myContainer="ctg-uroscan-v1.1"

#ssh octopoda.local
#cd singularity/rnaSeqTools

scp -P 2222 -i /Users/david/vm-singularity/.vagrant/machines/default/virtualbox/private_key  ~/scripts/ctg-singularity/ctg-uroscan-v1.1/environment.yml vagrant@127.0.0.1:/home/vagrant/
scp -P 2222 -i /Users/david/vm-singularity/.vagrant/machines/default/virtualbox/private_key  ~/scripts/ctg-singularity/ctg-uroscan-v1.1/ctg-uroscan-v1.1.def vagrant@127.0.0.1:/home/vagrant/

## BUILD
vagrant global-status
echo "Start the vagrant virual envronment with:  vagrant ssh 9d5f316"
echo "Build the singularity container with:  sudo -E singularity build ctg-uroscan-v1.1.sif ctg-uroscan-v1.1.def"
# exit


## after completion
scp -P 2222 -i /Users/david/vm-singularity/.vagrant/machines/default/virtualbox/private_key vagrant@127.0.0.1:/home/vagrant/ctg-uroscan-v1.1.sif .

rsync -av rsync -av david@octopoda.local:/Users/david/scripts/ctg-singularity/ctg-uroscan-v1.1/ctg-uroscan-v1.1.sif ~/scripts/ctg-singularity/ctg-uroscan-v1.1
