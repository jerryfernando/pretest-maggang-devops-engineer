![3](https://github.com/user-attachments/assets/db9f0e93-1e3e-4d68-857d-85d51189a490)# Virtualization
ubah hostname 
```
hostnamectl set-hostname tabeldata.com
```
![1](https://github.com/user-attachments/assets/88f59582-49c7-4124-aff0-2be523f76e49)

os centos7
![2](https://github.com/user-attachments/assets/c6561f94-5bc8-4824-b4b9-c626fa7d315f)

## Instalasi Node.js dan Nginx

Update Sistem
```
sudo yum update -y

```

```
sudo yum install -y epel-release

```


instalasi nginx

```
sudo yum install -y nginx

```

```
sudo systemctl start nginx
sudo systemctl enable nginx

```

mengubah index.html yg berada di /usr/share/nginx/html/

masuk ke
```
/usr/share/nginx/html/
```
```
sudo nano index.html
```
```
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profile Teman-Teman</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>JERI FERNANDO</h1>
        <div class="profile">
            <h2>devops</h2>
            <p>I'm a committed DevOps Engineer dedicated to creating efficient, automated, and secure development and production environments. With experience studying and applying devops knowledge.
Fundamentally, I'm a bridge builder between development and operations teams, aiming to remove barriers and expedite software delivery. I'm an expert in CI/CD automation, infrastructure as code, and cloud infrastructure management.</p>
        </div>
        <!-- Tambahkan lebih banyak profile sesuai kebutuhan -->
    </div>
</body>
</html>

```
![8](https://github.com/user-attachments/assets/3d3bede4-66f8-4028-8779-1bcdaf67a4d8)

opsional untuk menambahkan sedikit styles.css
```
sudo nano styles.css
```
```
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    margin: 0;
    padding: 20px;
}

.container {
    max-width: 800px;
    margin: 0 auto;
    background: white;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

h1 {
    text-align: center;
    color: #333;
}

.profile {
    margin: 20px 0;
    padding: 15px;
    border: 1px solid #ddd;
    border-radius: 5px;
    transition: background-color 0.3s;
}

.profile:hover {
    background-color: #f9f9f9;
}

h2 {
    color: #007BFF;
}

p {
    color: #555;
}

```
![9](https://github.com/user-attachments/assets/e11fad4d-3bfc-481b-9a55-3f87885f0322)

hasil 

![taks1](https://github.com/user-attachments/assets/cb3fdf2d-cb56-4b1d-85e6-6743e8b8d003)
