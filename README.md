
## How to Run the Script

Just run below five commands one after another :

`su -`

`mkdir /media/script && mount -t tmpfs -o size=1m tmpfs /media/script`

`wget -P /media/script https://raw.githubusercontent.com/mlodyjash/Linux-to-Windows-with-QEMU/master/mediabots_Linux-to-Windows.sh`

`chmod +x /media/script/*`

`/media/script/mediabots_Linux-to-Windows.sh`
