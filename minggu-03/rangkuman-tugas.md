# Penjelasan Praktikum TCC Minggu-03
<br/>

# Tugas
<br/>

1. Untuk proses berikutnya akan melakukan login pada heroku, disini saya menggunakan command git-bash untuk melakukan penagaksesan heroku. berikut merupakan perintahnya :<br/>
<dd>

![](image/tugas/1.png)

Dari perintah diatas apabila sudah mengisi perintah "heroku login", maka secara otomatis akan lansung terhubung ke web heroku yaitu halaman login. Seperti pada gambar dibawah ini :<br/>

![](image/tugas/2.png)

2. Selanjutnya mengecek versi dari php, composer dan git dari komputer local yang sebelumnya sudah diinstal, untuk perintah dan hasil eksekusinya seperti pada gambar dibawah ini :<br/>
<dd>

![](image/tugas/3.png)

3. Pada bagian ke-3 ini dilakukan proses clonning dari git heroku untuk mengambil repo "php-getting-started" ke bash lokal komputer dan masuk ke repo lokal yang baru di clonning, dan kemudian selanjutnya membuat app bauru kita pada heroku. untuk perintahnya seperti pada gambar yang tertera dibawah ini :<br/>
<dd>

![](image/tugas/4.png)


4. Kemudian selanjutnya melakukan push ke branch master heroku dengan menggunakan perintah "git push heroku master". Untuk perintah dan hasilnya seperti pada gambar dibawah ini :<br/>
<dd>

![](image/tugas/5.png)
![](image/tugas/6.png)

5. Kemudian selanjutnya melakukan konfiguasi pada web scale dengan nilai konfigurasinya 1, apabila 1 maka app yang di create pada heroku dapat diakses, dan kemudian untuk membukanya dengan menggunakan perintah "heroku open". seperti pada gambar dibawah ini :<br/>
<dd>

![](image/tugas/7.png)

<dd>Sehingga hasil yang di tampilkan pada web browser seperti dibawah ini :<br/>

![](image/tugas/8.png)

6. Kemudian selanjutnya melakukan update composer, dari bash commmand git, untuk perintah dan hasilnya seperti yang terlihat pada gambar dibawah ini :<br/>
<dd>

![](image/tugas/9.png)
![](image/tugas/10.png)
![](image/tugas/11.png)

Sehingga hasil yang di tampilkan pada repo lokal yang di conning sebelumnya, dimana pada direktori vendor akan terdapat file autoload.php dari hasil update composer tersebut :<br/>

![](image/tugas/12.png)

7. Selanjutnya dari hasil update composer tersebut masih memerlukan direktori arlik11es dan didalamnya akan di install atau ditambahkan direktori cowsayphp, dan kemudian baru dilakukan update composernya lagi. Untuk perintah dan hasilnya seperti pada gambar dibawah ini :<br/>
<dd>

![](image/tugas/13.png)

Sehingga hasil yang di tampilkan pada repo lokal yang di conning sebelumnya, dimana pada direktori vendor akan terdapat direktori arlik11es/cowsayphp dari hasil update composer tersebut :<br/>

![](image/tugas/14.png)

8. Kemudian selanjutnya melakukan perubahan pada file index.php yang terdapat pada direktori web pada repo lokal hasil clonning sebelumnya. untuk prosesnya seperti pada gambar dibawah ini : <br/>
<dd>

![](image/tugas/15.png)

9. Dan selanjutnya dilakukan push pada app heroku kita, dengan langkah perintah seperti yang tertera pada gambar dibawah ini :<br/>
<dd>

![](image/tugas/16.png)

Dan kemudian untuk melihat hasil dari push tersebut, dengan menggunakan perintah "git open cowsay", seperti pada gambar dibawah ini :<br/>

![](image/tugas/17.png)

Sehingga hasil yang ditapilkan pada halaman url app heroku kita, seperti pada gambar dibawah ini :<br/>

![](image/tugas/18.png)

10. Selanjutnya akan dilakukan pengecekan dengan menjalankan pada bash lokal heroku, apabila berhasil maka proses running app kita akan dilihat disitu, seperti pada gambar dibawah ini :<br/>
<dd>

![](image/tugas/19.png)