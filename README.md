# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
2. Apa yang anda ketahui tentang Infrastructure?
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
6. Mengapa teknology container saat ini sangat populer?
7. Apa yang anda ketahui tentang Orchestration Container System?

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini
## jawaban 
### 1.DevOps
DevOps adalah sebuah pendekatan pengembangan perangkat lunak yang menggabungkan pengembangan (Development) dan operasi (Operations). Tujuan utamanya adalah meningkatkan kolaborasi antara tim pengembang dan tim operasional, mempercepat pengiriman perangkat lunak, meningkatkan kualitas produk, dan meningkatkan respon terhadap perubahan kebutuhan pasar.

Prinsip utama DevOps meliputi:

-Integrasi Berkelanjutan (Continuous Integration): Menggabungkan kode yang baru ditulis ke dalam repositori secara teratur dan melakukan pengujian otomatis.

-Pengiriman Berkelanjutan (Continuous Delivery): Otomatisasi proses pengiriman perangkat lunak hingga siap untuk diproduksi.

-Pengujian Otomatis (Automated Testing): Menggunakan alat otomatis untuk menguji kode baru guna memastikan tidak ada bug.

-Pemantauan dan Logging (Monitoring and Logging): Memantau sistem untuk mendeteksi masalah dan log aktivitas untuk analisis.

### 2.Infrastructure
Infrastructure dalam konteks teknologi informasi (TI) mengacu pada komponen fisik dan virtual yang mendukung pengoperasian, pengelolaan, dan penyediaan layanan TI. Ini mencakup:

-Hardware: Server, storage, network devices.

-Software: Sistem operasi, middleware, aplikasi.

-Network: LAN, WAN, internet connectivity.

-Data Centers: Fasilitas fisik yang menyimpan dan mengelola hardware dan software.

### 3.Server
Server adalah sebuah sistem komputer yang menyediakan layanan kepada komputer lain (client) di dalam jaringan. Server bisa berupa hardware fisik atau virtual yang di-host di cloud. Implementasi server meliputi:

-Web Server: Menyajikan halaman web kepada pengguna. Contoh: Apache, Nginx.

-Database Server: Menyimpan dan mengelola data. Contoh: MySQL, PostgreSQL.

-File Server: Menyediakan akses ke file melalui jaringan. Contoh: Samba, FTP.

-Application Server: Menjalankan aplikasi server-side. Contoh: Tomcat, JBoss.

-Mail Server: Mengelola email. Contoh: Postfix, Exchange Server.

### 4.Mengapa Server Dibutuhkan dalam Pengembangan Software
Server sangat penting dalam pengembangan software karena:

-Penyimpanan dan Pengelolaan Data: Menyimpan data dan memungkinkan akses yang efisien oleh aplikasi.

-Menjalankan Aplikasi: Menyediakan lingkungan eksekusi untuk aplikasi backend.

-Pengujian dan Integrasi: Menyediakan lingkungan untuk pengujian integrasi dan pengembangan berkelanjutan.

-Kolaborasi Tim: Memfasilitasi kolaborasi dengan hosting alat pengembangan seperti repositori kode, CI/CD tools, dll.


### 5.Virtualisasi dan Container
-Virtualisasi: Teknologi yang memungkinkan menjalankan beberapa sistem operasi virtual pada satu server fisik dengan membagi sumber daya hardware. 
Contoh: VMware, Hyper-V.

-Container: Teknologi yang memungkinkan paket aplikasi dan semua dependensinya menjadi satu unit yang dapat dijalankan secara konsisten di berbagai lingkungan. Contoh: Docker.

### 6.Mengapa Teknologi Container Sangat Populer
-Portabilitas: Container dapat berjalan konsisten di berbagai lingkungan, dari pengembangan hingga produksi.

-Efisiensi Sumber Daya: Container berbagi kernel sistem operasi, sehingga lebih ringan daripada mesin virtual.

-Penggunaan yang Mudah: Alat seperti Docker menyediakan cara yang mudah untuk mengelola dan mengirimkan container.

-Isolasi: Aplikasi di dalam container terisolasi satu sama lain dan dari host.

### 7.Orchestration Container System
Orchestration container system adalah alat yang mengotomatiskan penempatan, pengelolaan, penskalaan, dan jaringan container. 

Contoh:

-Kubernetes: Platform open-source untuk otomatisasi deployment, scaling, dan operasi container.

-Docker Swarm: Orchestration tool dari Docker untuk mengelola cluster Docker.

-Apache Mesos: Sistem manajemen cluster yang juga dapat mengelola container.

Alat-alat ini membantu dalam mengelola lingkungan container yang besar dan kompleks, memungkinkan aplikasi berjalan dengan andal, terukur, dan mudah diatur.

## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
- Buatlah web profile temen-temen kemudian deploy ke webserver nginx tersebut yang telah di deploy
  
(kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container
  - image: `dimmaryanto93/udemy-springboot-app:latest`
  - port: `8080`
  - env: 
    - `DATABASE_HOST`: `<ip-domain-db>`
    - `DATABASE_PORT`: `5432` 
    - `DATABASE_NAME`: `<db-name>`
    - `DATABASE_PASSWORD`: `<db-password>`
    - `APPLICATION_PORT`: `8080`
  need:
    - Database PostgreSQL v14.2
2. Frontend container
  - image: `dimmaryanto93/udemy-angular-app:latest`
  - port: `80`
  - env:
    - `APPLICATION_PORT`: `80`
    - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
    - `BACKEND_HOST`: `<ip-backend-apps>`
    - `BACKEND_PORT`: `<port-backend-apps>`
    - `BACKEND_CONTEXT_PATH`: `/`
  - need:
    - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`

