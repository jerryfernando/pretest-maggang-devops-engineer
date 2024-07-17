# container docker

install docker  
```
#!/bin/bash

# Perbarui paket yang ada di sistem
sudo yum update -y

# Instal beberapa paket yang diperlukan sebelum menginstal Docker
sudo yum install -y yum-utils device-mapper-persistent-data lvm2

# Tambahkan repository Docker ke sistem
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

# Instal Docker menggunakan perintah berikut
sudo yum install -y docker-ce docker-ce-cli containerd.io

# Mulai layanan Docker dan aktifkan agar otomatis berjalan saat sistem dinyalakan

sudo systemctl start docker
sudo systemctl enable docker
```

![2](https://github.com/jerryfernando/DataSintesa-DevOps-Engineer-Take-home-Test/assets/23428256/80960607-6bb1-400c-9b04-1cad8d2b9deb)


```
version: '3.8'

services:
  backend:
    image: dimmaryanto93/udemy-springboot-app:latest
    ports:
      - "8080:8080"
    environment:
      DATABASE_HOST: 103.127.97.172
      DATABASE_PORT: 5432
      DATABASE_NAME: postgres
      DATABASE_PASSWORD: Jeri123
      APPLICATION_PORT: 8080
    depends_on:
      - db

  frontend:
    image: dimmaryanto93/udemy-angular-app:latest
    ports:
      - "8081:80"
    environment:
      APPLICATION_PORT: 80
      NGINX_ROOT_DOCUMENT: /var/www/html
      BACKEND_HOST: backend
      BACKEND_PORT: 8080
      BACKEND_CONTEXT_PATH: /

  db:
    image: postgres:14.2
    environment:
      POSTGRES_DB: postgres
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: Jeri123
    ports:
      - "5432:5432"

networks:
  default:
    driver: bridge
```

![6](https://github.com/user-attachments/assets/5ee4f111-2a22-4812-b595-d0baf5f4cda0)

hasil 
![5](https://github.com/user-attachments/assets/8ef44797-d7a9-404d-a012-c3fee14e3381)


