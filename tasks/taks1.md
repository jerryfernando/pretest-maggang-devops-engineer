# Virtualization
ubah hostname 
```
hostnamectl set-hostname tabeldata.com
```
![1](https://github.com/user-attachments/assets/88f59582-49c7-4124-aff0-2be523f76e49)

os centos7
![2](https://github.com/user-attachments/assets/c6561f94-5bc8-4824-b4b9-c626fa7d315f)

## Instalasi Node.js dan Nginx

Update Sistem dan Instalasi Node.js
```
sudo yum update -y

```

```
sudo yum install -y epel-release

```

```
sudo yum install -y nodejs npm

```

instalasi nginx

```
sudo yum install -y nginx

```

```
sudo systemctl start nginx
sudo systemctl enable nginx

```
## Setup Proyek Node.js

```
mkdir myapp
cd myapp

```

```
npm init -y


```

```
npm install express

```
buat file app.js
```
nano app.js

```

```
// Simple Express web server
// @see http://howtonode.org/getting-started-with-express

// Load the express module
var express = require('express');
var app = express();

// Respond to requests for / with profile information
app.get('/', function(req, res) {
  res.send(`
    <html>
      <head>
        <title>Profile</title>
      </head>
      <body>
        <h1>JERI FERNANDO</h1>
        <h2>DEVOPS</h2>
        <h5>I'm a committed DevOps Engineer dedicated to creating efficient, automated, and secure development and production environments. With experience studying and applying devops knowledge.
Fundamentally, I'm a bridge builder between development and operations teams, aiming to remove barriers and expedite software delivery. I'm an expert in CI/CD automation, infrastructure as code, and cloud infrastructure management</h5>
      </body>
    </html>
  `);
});

// Listen on port 80
app.listen(80, () => console.log('Express server started successfully.'));


```

Jalankan server Express

```
sudo node app.js

```

buat file konfigurasi nginx

```
sudo nano /etc/nginx/conf.d/myapp.conf

```

```
server {
    listen 80;

    server_name <your-domain> <public-ip>;

    location / {
        proxy_pass http://localhost:80;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}

```
```
sudo ln -s /etc/nginx/sites-available/myapp /etc/nginx/sites-enabled/
````

```
sudo systemctl restart nginx

```
