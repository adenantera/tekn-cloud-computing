# Praktikum Teknologi Cloud Computing - Minggu 9 (Docker for Beginners - Linux)

## Login akun Docker

---

![](image/latihan/1.png)

Untuk dapat mengakses terminal linux pada web ini yakni dengan login terlebih dahulu menggunakan akun Docker kita.

---

## Task 0: Prerequisites

---

Meng-clone repo dari github dengan nama linux_tweet_app pada akun dockersamples.

![](image/latihan/2.png)

---

## Task 1: Run some simple Docker containers

**Run a single task in an Alpine Linux container**

1. Memulai container baru dengan image alpine

![](image/latihan/3.png))

2. Melihat daftar semua container yang ada

![](image/latihan/4.png)

**Run an interactive Ubuntu container**

1. Menjalankan Docker container dan mengakses terminal ubuntu

![](image/latihan/5.png)

2. Menjalankan perintah berikut.

![](image/latihan/6.png)

```
//untuk menampilkan daftar folder atau file yang ada
jalankan perintah $ ls /

//untuk menampilkan proses container yang sedang berjalan
jalankan perintah $ ps aux

//untuk menampilkan distro linux yang container yang digunakan
$ cat /etc/issue
```

3. Keluar dari terminal ubuntu

![](image/latihan/7.png)

4. Cek versi host VM

![](image/latihan/8.png)

**Run a background MySQL container**

1. Menjalankan MySQL container

![](image/latihan/9.png)

2. Melihat daftar container

![](image/latihan/10.png)

3. Cek log dan proses yang berjalan didalam container

![](image/latihan/11.png)
![](image/latihan/12.png)

4. Melihat versi MySQL yang digunakan

![](image/latihan/13.png)

5. Menghubungkan terminal ke sh

![](image/latihan/14.png)

---

## Task 2: Package and run a custom app using Docker

---

**Build a simple website image**

1. Berpindah ke direktori repo yang telah di-clone sebelumnya

![](image/latihan/15.png)

```
//untuk melihat isi dari Dockerfile
$ cat Dockerfile
```

2. Mengexport variabel dockerid dengan isian id docker kita

![](image/latihan/16.png)

```
//untuk menampilkan isi dari variabel dockerid
$ echo $DOCKERID
```

3. Membuat docker image

![](image/latihan/17.png)

4. Menjalankan container untuk menghosting image yang telah dibuat

![](image/latihan/18.png)

5. Mengecek hasilnya dengan menekan link yang telah disediakan

![](image/latihan/19.png)
![](image/latihan/20.png)

6. Menghentikan dan menghapus container lalu mengeceknya

![](image/latihan/21.png)

---

## Task 3: Modify a running website

**Start our web app with a bind mount**

1. Menjalankan container untuk menghosting image yang telah dibuat

![](image/latihan/22.png)

2. Mengecek bahwasanya image berhasil di hosting dengan menekan link yang telah disediakan

![](image/latihan/23.png)
![](image/latihan/24.png)

**Modify the running website**

1. Meng-kopi index.html container dan merefresh web sblmnya untuk melihat hasilnya

![](image/latihan/25.png)
![](image/latihan/26.png)

2. Menghentikan dan menghapus container dan mengeceknya

![](image/latihan/27.png)
![](image/latihan/28.png)

**Update the image**

1. Membuat image baru

![](image/latihan/29.png)

2. Melihat daftar image yang ada

![](image/latihan/30.png)

**Test the new version**

1. Menjalankan container dan melihat hasilnya

![](image/latihan/31.png)
![](image/latihan/32.png)

2. Menjalankan container lainnya dan melihat hasilnya

![](image/latihan/33.png)
![](image/latihan/34.png)

**Push your images to Docker Hub**

1. Melihat daftar image yang telah di hosting

![](image/latihan/35.png)

2. Sebelumnya login menggunakan akun docker kita agar tepat dan lancar di push atau upload pada akun docker kita

![](image/latihan/36.png)

3. Push image versi 1.0 dan 2.0

![](image/latihan/37.png)

4. Melihat hasil image yang telah di push pada akun docker hub kita masing-masing

![](image/latihan/38.png)
![](image/latihan/39.png)

---
