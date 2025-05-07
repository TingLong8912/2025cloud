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
```

### Nginx Site
```bash
cd nginx-site
docker build -t nolonger89/2025cloud:nginx-site .
docker run -p 8080:80 nolonger89/2025cloud:nginx-site
```

## CI/CD: Automated Docker Build & Tagging

這個專案透過 GitHub Actions 自動化產生並推送 Docker Images，以下是流程設計與標記邏輯（Tagging Logic）的說明：

### 📦 自動化流程圖

```text
程式碼 Push 到 main         
        │               
        ▼               
GitHub Action 啟動 (`build-and-push.yml`)               
        │                   
        ├─ 建立 Python App 的 Docker Image              
        ├─ 建立 Nginx Site 的 Docker Image          
        │               
        └─ 推送至 Docker Hub (nolonger89/2025cloud)             
```

### 🏷️ Tag 設計邏輯

目前我們固定為每個子專案設計不同的 tag 名稱：

- `python-app`：用於 Python App 對應的 Image
- `nginx-site`：用於 Nginx 靜態網頁服務對應的 Image

每次 `main` 分支更新時就會重新建立並推送最新版本的 image，tag 不會變動（即會覆蓋舊版）。

