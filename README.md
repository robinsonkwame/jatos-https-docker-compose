# JATOS over HTTPS

## Introduction
This is a simple modification that enables you to run a JATOS HTTPS server using `docker-compose`. The use of HTTPS assumes that you have a:
* domain name SSL certificate
* access to the domain name private key (.key)
* the domain name certificate (.crt)

## Configuration
```{bash}
git clone https://github.com/robinsonkwame/jatos-https-docker-compose.git
# Open `docker-compose.yml` in the text editor of your choice, insert <host_path_to_your_certificate>.crt and save
# Open `docker-compose.yml` in the text editor of your choice, insert <host_path_to_your_private_key>.key and save
# Open `ngix.conf` in the text editor of your choice, search and replace <insert your domain name here> with your domain name and save
```

## How to start
```{bash}
docker-compose up
# access https://<your domain name>
# note: even https://localhost will work
#   the hostname won't match the certificate but the data will be
#   encrypted and calls like `getUserMedia` will still function
```

HTH
