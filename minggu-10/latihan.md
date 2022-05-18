# Praktikum Teknologi Cloud Computing - Minggu 10 (Docker Networking)

## Login akun Docker

---

![](image/latihan/1.png)

Untuk dapat mengakses terminal linux pada web ini yakni dengan login terlebih dahulu menggunakan akun Docker kita.

---

## Section #1 - Networking Basics

---

**Step 1: The Docker Network Command**

![](image/latihan/2.png)

```
//Merupakan perintah utama untuk konfigurasi dan mengelola container networks
$ docker network
```

**Step 2: List networks**

![](image/latihan/3.png)

```
//Menampilkan daftar container networks
$ docker network ls
```

**Step 3: Inspect a network**

![](image/latihan/4.png)

```
//Melihat detail konfigurasi jaringan
$ docker network inspect bridge
```

**Step 4: List network driver plugins**

![](image/latihan/5.png)

```
//Melihat informasi mengenai installasi Docker
$ docker info
```

---

## Section #2 - Bridge Networking

---

**Step 1: The Basics**

![](image/latihan/6.png)
![](image/latihan/7.png)
![](image/latihan/8.png)
![](image/latihan/9.png)
![](image/latihan/10.png)

```
//Menampilkan daftar container networks
$ docker network ls

//Mengupdate dan install packages bridge-utils
$ apk update

//Menambahkan packages bridge-utils
$ apk add bridge

//Menampilkan daftar bridges pada Docker host
$ brctl show

//Melihat detail bridge
$ ip a
```

**Step 2: Connect a container**

![](image/latihan/11.png)
![](image/latihan/12.png)
![](image/latihan/13.png)
![](image/latihan/14.png)

```
//Membuat container baru
$ docker run -dt ubuntu sleep infinity

//Melihat spek container network
$ docker ps

//Menampilkan daftar bridges pada Docker host
$ brctl show

//Menampilkan lampiran pada container bridge
$ docker network inspect bridge
```

**Step 3: Test network connectivity**

![](image/latihan/15.png)
![](image/latihan/16.png)
![](image/latihan/17.png)
![](image/latihan/18.png)
![](image/latihan/19.png)

```
//Mengetes jaringan (ping)
$ ping -c5 172.17.0.2

//Melihat spek container network
$ docker ps

//Masuk terminal ubuntu
$ docker exec -it yourcontainerid /bin/bash

//Menginstall program ping
$ apt-get update && apt-get install -y iputils-ping

//Mengetes jaringan (ping)
$ ping -c5 www.github.com

//Keluar dari terminal ubuntu
$ exit

//Menghentikan container yang sedang berjalan
$ docker stop yourcontainerid
```

**Step 4: Configure NAT for external connectivity**

![](image/latihan/20.png)
![](image/latihan/21.png)
![](image/latihan/22.png)

```
//Menjalankan container baru dari official NGINX image
$ docker run --name web1 -d -p 8080:80 nginx

//Melihat spek container network
$ docker ps

//Menghubungkan ke docker host
$ curl 127.0.0.1:8080
```

---

## Section #3 - Overlay Networking

---

**Step 1: The Basics**

![](image/latihan/23.png)
![](image/latihan/24.png)
![](image/latihan/25.png)

```
//Menginisialisasi docker swarm baru
$ docker swarm init --advertise-addr $(hostname -i)

//Menggabungkan node
$ docker swarm join \
>     --token SWMTKN-1-69b2x1u2wtjdmot0oqxjw1r2d27f0lbmhfxhvj83chln1l6es5-37ykdpul0vylenefe2439cqpf \
>     10.0.0.5:2377

//Melihat daftar node
$ docker node ls
```

**Step 2: Create an overlay network**

![](image/latihan/26.png)
![](image/latihan/27.png)
![](image/latihan/28.png)
![](image/latihan/29.png)

```
//Membuat sebuah overlay network
$ docker network create -d overlay overnet

//Mengecek/menampilkan network
$ docker network ls

//Melihat lebih detail informasi mengenai overnet network
$ docker network inspect overnet
```

**Step 3: Create a service**

![](image/latihan/30.png)
![](image/latihan/31.png)
![](image/latihan/32.png)
![](image/latihan/33.png)

```
//Membuat layanan baru
$ docker service create --name myservice \
--network overnet \
--replicas 2 \

//Mengecek/menampilkan daftar layanan
$ docker service ls

//Melihat daftar layanan yang sedang berjalan
$ docker service ps myservice

//Mengecek/menampilkan network
$ docker network ls

//Melihat lebih detail informasi mengenai overnet network
$ docker network inspect overnet
```

**Step 4: Test the network**

![](image/latihan/34.png)
![](image/latihan/35.png)

```
//Melihat lebih detail informasi mengenai overnet network
$ docker network inspect overnet

//Melihat spek container network
$ docker ps
```

---

## Cleaning Up

![](image/latihan/36.png)
![](image/latihan/37.png)
![](image/latihan/38.png)

```
//Menghspus layanan
$ docker service rm myservice

//Melihat spek container network
$ docker ps

//Menghapus node
$ docker swarm leave --force
```

---
