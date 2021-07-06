# gophish-ssl
randomshiii    (if reboot goto /opt/gophish and ./gophish
===

***Step 1: 
***
1. make sure server centos 7
2. yum install wget -y
3. yum install git -y
4. yum install unzip -y

***Step 2: Download GoPhish install go phish***


[https://github.com/gophish/gophish/releases
](https://)
1. The prereq to this is you have the ability to port forward traffic to your own Linux VM at home or are using a VM on a VPS provider.

1. Unzip the file and modify the file gophish to be an executable
1. mkdir /opt/gophish
1. unzip whatudownload.zip -d /opt/gophish
1. chmod +x gophish
1. ./gophish (dont run yet)

***Step 2: Download certbot install get ssl***

1. yum -y install epel-release
2. yum -y install certbot
3. certbot certonly -d domain.com --manual --preferred-challenges dns


    
***Step 4: Copy the key and cert files to the gophish directory***

sudo cp /etc/letsencrypt/live/yourdomain.com/privkey.pem /opt/gophish/domain.key  and  gophish_admin.key

sudo cp /etc/letsencrypt/live/yourdomain.com/fullchain.pem /opt/gophish/domain.crt   and gophish_admin.crt

sudo nano /opt/gophish/config.json


    fix domain.key and domain.crt in and set all ip to 0.0.0.0
    
    
1. Step 5: Amend the configuration of config.json with your new certificate information.
1. Change the url port from 80 to 443, change use_tls from false to true, change cert_path from example.cert to domain.crt and key_path from exmaple.key to domain.key

Stop ./gophish and start it back up to enable the new certificates
This will make the website look a little bit more legit. 


