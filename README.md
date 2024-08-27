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

1. DevOps adalah metodologi dalam pengembangan software yang menggabungkan proses development dan operation guna mengoptimasikan dan mempersingkat siklus pengembangan software dengan tetap memberikan fitur, perbaikan, dan pembaruan perangkat lunak dengan frekuensi dan kualitas yang tinggi.
2. Infrastructure dalam konteks IT mengacu pada komponen-komponen yang membangung dan mendukung pengoperasian dan pengelolaan suatu sistem. Contoh komponen yang dimaksud adalah hardware, software dan layanan/fasilitas yang digunakan.
3. Server adalah perangkat yang menyediakan layanan kepada komputer lain dalam suatu jaringan. Layanan tersebut meliputi menyimpan dan mengelola database, hosting aplikasi web, tempat penyimpanan file.
Implementasi dan contoh server:
- Meng-host aplikasi web. Contoh : Apache HTTP Server, Nginx.
- Menyimpan dan mengelola data dalam database. Contoh: MySQL, PostgreSQL, Oracle Database.
- Menyediakan tempat penyimpanan file. COntoh Samba, NFS (Network File System), Windows File Sharing.
4. Server dibutuhkan dalam development dikarenakan kebutuhan terhadap layanan yang diberikan oleh server tersebut. Misalnya server dapat menyediakan environment yang konsisten untuk pengembangan dan pengujian dengan memastikan aplikasi berjalan sama di semua tahap pengembangan. Selain itu server juga dapat menjadi tempat penyimpanan data yang akan diakses oleh banyak pengguna.
5. Virtualization adalah teknologi yang memungkinakan untuk membagi sumber daya suatu perangkat keras sehingga dapat menjalankan beberapa sistem operasi pada satu perangkat keras.
Container atau containerization adalah metode virtualisasi dimana seluruh komponen aplikasi di kumpulkan dalam satu container sehingga dapat di jalankan pada lingkungan yang terisolasi.
6. Beberapa alasan mengapa container sangat populer:
- Container lebih ringan dan efisien dibandingkan dengan VM.
- Container memungkinkan aplikasi dijalankan secara konsisten di berbagai lingkungan.|
- Memberikan lingukangan yang terisolasi sehingga dapat mengurangi konflik dan meningkatkan kemanan.
- Memiliki integrasi yang baik dengan proses DevOps dan CI/CD.
7. Orchestration Container System adalah alat yang dapat mengotomasi proses penempatan, manajemen, penskalaan, dan penghapusan container. 
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

