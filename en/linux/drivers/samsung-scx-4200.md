# Installing driver for Samsung SCX-4200

## Debian

Here is the repository for the driver supporting both printer and scanner:

http://www.bchemnet.com/suldr/index.html

    echo "deb http://www.bchemnet.com/suldr/ debian extra" > /etc/apt/sources.list.d/bchemnet.list
    wget -O - http://www.bchemnet.com/suldr/suldr.gpg | sudo apt-key add -
    apt-get update
    apt-get install samsungmfp-scanner
