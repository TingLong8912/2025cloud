# 2025cloud

This project contains two Docker containers:

## 1. Python App

Located in `python-app/`.  
A simple Python script that prints a message.

## 2. Nginx Site

Located in `nginx-site/`.  
A basic static HTML site served by Nginx.

## How to Build and Run

### Python App

```bash
cd python-app
docker build -t yourname/2025cloud:python-app .
docker run yourname/2025cloud:python-app


### Nginx Site
cd nginx-site
docker build -t nolonger89/2025cloud:nginx-site .
docker run -p 8080:80 nolonger89/2025cloud:nginx-site