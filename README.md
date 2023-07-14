# Simple Notes App
This is a simple notes app built with React and Django.

## Requirements
1. Python 3.9
2. Node.js
3. React

## Create AWS EC2 Instance(t2.micro)(ubuntu)
## Install Nginx
```
sudo apt-get update
sudo apt install nginx
systemctl status nginx
```
## Install Docker
```
sudo apt install docker.io
docker ps
sudo usermod -aG docker $USER
sudo reboot
```
## Installation
1. Clone the repository
```
https://github.com/AbhishekTijare/django-deployment-nginx.git
```

2. Build the app
```
docker build -t notes-app .
```

3. Run the app
```
docker run -d -p 8000:8000 notes-app:latest
```

## Set the proxy_pass for the app in /etc/nginx/sites-enabled/default
```
sudo vim default
```
for frontend :
inside location /{ proxy_pass http://127.0.0.1:8000;}
for backend :
inside location/api { proxy_pass http://127.0.0.1:8000/api;}
