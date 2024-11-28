# Installation

## Nginx

Replace `jenkins.example.com` by your domain in `default.conf`

## Install SSL

1. Install Certbot `sudo apt-get install certbot python3-certbot-nginx -y`
2. Generate certificates `sudo certbot certonly --nginx -d yourdomain.com --config-dir .`
3. Edit `docker-compose.yml`, replace `<domain>` by your domain name in nginx volumes section
4. Certbot might install and start nginx service on current machine, you need to stop this nginx service for the nginx docker to work `sudo systemctl disable nginx` and `sudo systemctl stop nginx`
5. You might have to stop nginx with this command aswell `sudo nginx -s stop`

## Jenkins

1. Run `docker compose up -d`
2. Go to `https://<domain>` to access Jenkins web interface
<br>
On the first install you need to recover the inital admin password
Just run `docker logs jenkins` and copy the password from the terminal to the web interface

