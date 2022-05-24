# Praktikum Teknologi Cloud Computing - Minggu 11 (Application Containerization & Microservice Orchestration)

## Login akun Docker

---

![](image/latihan/1.png)

Untuk dapat mengakses terminal linux pada web ini yakni dengan login terlebih dahulu menggunakan akun Docker kita.

---

## Setup

![](image/latihan/2.png)

```
//Mengclone repository dari url github
$ git clone https://github.com/ibnesayeed/linkextractor.git

//Berpindah ke direktori linkextractor
$ cd linkextractor

//Berpindah ke branch demo
$ git checkout demo
```

---

## Step 0: Basic Link Extractor Script

![](image/latihan/3.png)

```
//Berpindah ke branch step0
$ git checkout step0

//Menampilkan struktur folder
$ tree
```

![](image/latihan/4.png)

```
//Menampilkan isi file linkextractor.py
$ cat linkextractor.py

//Menjalankan file linkextractor.py
$ ./linkextractor.py http://example.com/
```

![](image/latihan/5.png)

```
//Melihat hak/izin akses file linkextractor.py
$ ls -l linkextractor.py

//Menjalankan file linkextractor.py
$ python linkextractor.py
```

---

## Step 1: Containerized Link Extractor Script

![](image/latihan/6.png)

```
//Berpindah ke branch step1
$ git checkout step1

//Menampilkan struktur folder
$ tree
```

![](image/latihan/7.png)
![](image/latihan/8.png)
![](image/latihan/9.png)

```
//Menampilkan isi file Dockerfile
$ cat Dockerfile

//Membuat image
$ docker image build -t linkextractor:step1 .

//Menampilkan daftar image
$ docker image ls

//Menjalankan container
$ docker container run -it --rm linkextractor:step1 http://example.com/
```

![](image/latihan/10.png)

```
//Menjalankan container
$ docker container run -it --rm linkextractor:step1 https://training.play-with-docker.com/
```

---

## Step 2: Link Extractor Module with Full URI and Anchor Text

![](image/latihan/11.png)

```
//Berpindah ke branch step2
$ git checkout step2

//Menampilkan struktur folder
$ tree
```

![](image/latihan/12.png)

```
//Menampilkan isi file linkextractor.py
$ cat linkextractor.py
```

![](image/latihan/13.png)

```
//Membuat image
$ docker image build -t linkextractor:step2 .
```

![](image/latihan/14.png)

```
//Menampilkan daftar image
$ docker image ls
```

![](image/latihan/15.png)

```
//Menjalankan container
$ docker container run -it --rm linkextractor:step2 https://training.play-with-docker.com/
```

![](image/latihan/16.png)

```
//Menjalankan container
$ docker container run -it --rm linkextractor:step1 https://training.play-with-docker.com/
```

---

## Step 3: Link Extractor API Service

![](image/latihan/17.png)

```
//Berpindah ke branch step3
$ git checkout step3

//Menampilkan struktur folder
$ tree
```

![](image/latihan/18.png)

```
//Menampilkan isi file Dockerfile
$ cat Dockerfile
```

![](image/latihan/19.png)

```
//Menampilkan isi file main.py
$ cat main.py
```

![](image/latihan/20.png)

```
//Membuat image
$ docker image build -t linkextractor:step3 .
```

![](image/latihan/21.png)

```
//Menjalankan container
$ docker container run -d -p 5000:5000 --name=linkextractor linkextractor:step3

//Menampilkan daftar container
$ docker container ls
```

![](image/latihan/22.png)

```
//Membuat permintaan HTTP
$ curl -i http://localhost:5000/api/http://example.com/
```

![](image/latihan/23.png)

```
//Melihat catatan container
$ docker container logs linkextractor

//Menghapus container
$ docker container rm -f linkextractor
```

---

## Step 4: Link Extractor API and Web Front End Services

![](image/latihan/24.png)

```
//Berpindah ke branch step4
$ git checkout step4

//Menampilkan struktur folder
$ tree
```

![](image/latihan/25.png)

```
//Menampilkan isi file docker-compose.yml
$ cat docker-compose.yml
```

![](image/latihan/26.png)

```
//Menampilkan isi file www/index.php
$ cat www/index.php
```

![](image/latihan/27.png)

```
//Menjalankan layanan docker compose
$ docker-compose up -d --build
```

![](image/latihan/28.png)

```
//Menampilkan daftar container
$ docker container ls
```

![](image/latihan/29.png)

```
//Menghubungakan dengan layanan API
$ curl -i http://localhost:5000/api/http://example.com/
```

Mengakses web Link Extractor

![](image/latihan/30.png)
![](image/latihan/31.png)

```
//Memodifikasi index file link extractor
$ sed -i 's/Link Extractor/Super Link Extractor/g' www/index.php
```

Mengakses web Link Extractor yang telah di ubah

![](image/latihan/32.png)
![](image/latihan/33.png)

```
//Mereset atau mengembalikan perubahan
$ git reset --hard

//Menghentikan layanan
$ docker-compose down
```

---

## Step 5: Redis Service for Caching

![](image/latihan/34.png)

```
//Berpindah ke branch step5
$ git checkout step5

//Menampilkan struktur folder
$ tree
```

![](image/latihan/35.png)

```
//Menampilkan isi file www/Dockerfile
$ cat www/Dockerfile
```

![](image/latihan/36.png)

```
//Menampilkan isi file api/main.py
$ cat api/main.py
```

![](image/latihan/37.png)

```
//Menampilkan isi file docker-compose.yml
$ cat docker-compose.yml
```

![](image/latihan/38.png)

```
//Menjalankan layanan
$ docker-compose up -d --build
```

Mengakses web Link Extractor

![](image/latihan/39.png)
![](image/latihan/40.png)
![](image/latihan/41.png)

```
//Membuaka client redis
$ docker-compose exec redis redis-cli monitor

//Memodifikasi index file link extractor
$ sed -i 's/Link Extractor/Super Link Extractor/g' www/index.php

//Mereset atau mengembalikan perubahan
$ git reset --hard

//Menghentikan layanan
$ docker-compose down
```

---

## Step 6: Swap Python API Service with Ruby

![](image/latihan/42.png)

```
//Berpindah ke branch step6
$ git checkout step6

//Menampilkan struktur folder
$ tree
```

![](image/latihan/43.png)

```
//Menampilkan isi file api/linkextractor.rb
$ cat api/linkextractor.rb
```

![](image/latihan/44.png)

```
//Menampilkan isi file api/Dockerfile
$ cat api/Dockerfile
```

![](image/latihan/45.png)

```
//Menampilkan isi file docker-compose.yml
$ cat docker-compose.yml
```

![](image/latihan/46.png)

```
//Menjalankan layanana
$ docker-compose up -d --build
```

![](image/latihan/47.png)

```
//Menghubungkan layananan
$ curl -i http://localhost:4567/api/http://example.com/
```

Mengakses web link extractor
![](image/latihan/48.png)

Menguji sebuah url untuk di extract
![](image/latihan/49.png)
![](image/latihan/50.png)
![](image/latihan/51.png)

```
//Menghentikan layanan
$ docker-compose down

//Melihat catatan sebuah web yang telah di extract
$ cat logs/extraction.log
```

---
