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