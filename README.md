# easy-guide-to-hardening-nginx

#remove TLSv1 and TLSv1.1 from, and add TLSv1.3
sudo nano /etc/nginx/nginx.conf
sudo nano /etc/nginx/sites-available/default
sudo nano /etc/nginx/sites-enabled/default
sudo nano /etc/letsencrypt/options-ssl-nginx.conf #only if you are using letscrypt

#reload nginx
sudo service nginx reload
#reload certbot
certbot renew --force-renewal

#use a stronger cipher suite
sudo nano /etc/letsencrypt/options-ssl-nginx.conf

ssl_ciphers ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384;
