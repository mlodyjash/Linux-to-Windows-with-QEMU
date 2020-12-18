## GCP sdk commands 

`gcloud compute instances create temp-image-base --image-family=projects/ubuntu-os-cloud/global/images/family/ubuntu-1604-lts --zone=us-central1-b`

`gcloud compute instances stop temp-image-base --zone=us-central1-b`

`gcloud compute images create nested-vm-image --source-disk=temp-image-base --source-disk-zone=us-central1-b --licenses="https://www.googleapis.com/compute/v1/projects/vm-options/global/licenses/enable-vmx"`

`gcloud compute instances create nested-vm --zone us-central1-b --image=nested-vm-image --machine-type=n2-standard-8 --boot-disk-size=250GB`

`gcloud compute instances create nested-vm --zone europe-west3-a --image=nested-vm-image --machine-type=n2-standard-4 --boot-disk-size=250GB`

`gcloud compute ssh nested-vm --zone=us-central1-b`

`gcloud compute ssh nested-vm --zone=europe-west3-a`

`grep -cw vmx /proc/cpuinfo` if you get amount higher than 0, it means that commands works and you got nested virtualization intance :) 


## How to Run the Script to install windows

Just run below five commands one after another :

`su -`

`mkdir /media/script && mount -t tmpfs -o size=1m tmpfs /media/script`

`wget -P /media/script https://raw.githubusercontent.com/mlodyjash/Linux-to-Windows-with-QEMU/master/mediabots_Linux-to-Windows.sh`

`chmod +x /media/script/*`

`/media/script/mediabots_Linux-to-Windows.sh`

Bye!
