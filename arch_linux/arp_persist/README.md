# Persist ARP Entries

## Usage

1. Change MAC address and IP address in arp_persist.py

2. sudo ./setup.sh

## Test

After booting system wait for 2 Minutes, Because of added delay so that all interface will be up. Then you can test using

​	```systemctl status arp_request```

or

​	```arp -a```

And in arp entry you will see "PERM"

## Working

### arp_persist.py

This is a simple script which sets arp entry.

Why Try-Catch and Loop?

If you are not connected to interface this will throw error that's why used try-catch and you might connect interface any random time that's why it tries to add entry every 150 Sec. Don't worry about resource consumption it only consumes 4 MB Ram.

### arp_persist.service

This only creates a service which calls above script on boot. This is for arch linux, for other distributions follow guidelines for running python scripts at startup.

## setup.sh

This shell script copies files at desired locations and then enables service. Don't use for other distribution, You have to manually enable running python script "arp_persist.py" at boot.

## Troubleshoot

You can use same concept and can also use for other distributions. If you encounter any problem and  need my help,you can reach me at "git.hrca@gmail.com"

## Liked my work?
<a href="https://www.buymeacoffee.com/parveshmonu" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>

## Websites
https://github.com/Parveshdhull
<br />https://twitter.com/ParveshMonu
<br />https://youtube.com/right2trick