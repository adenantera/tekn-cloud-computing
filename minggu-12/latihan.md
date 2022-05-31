# Praktikum Teknologi Cloud Computing - Minggu 12 (Docker Orchestration Hands-on Lab)

## Login akun Docker

---

![](image/latihan/1.png)

Untuk dapat mengakses terminal linux pada web ini yakni dengan login terlebih dahulu menggunakan akun Docker kita.

---

1. Membuat container baru pada terminal node1.

![](image/latihan/2.png)

`Disini menggunakan container terbaru dari ubuntu.`

2. Melihat daftar container untuk memastikan bahwa container telah berhasil dibuat.

![](image/latihan/3.png)

3. Menginisialisasi docker swarm.

![](image/latihan/4.png)

`Disini kita mendapatkan token untuk menggabungkan dengan node lain nantinya.`

4. Melihat informasi docker swarm pada node1.

![](image/latihan/5.png)
![](image/latihan/6.png)
![](image/latihan/7.png)

`Node1 merupakan node untuk memanajemen node lainnya.`

5. Menggabungkan node2 dan node3 kedalam swarm node1 dengan menggunakan token yang telah didapatkan sebelumnya.

![](image/latihan/8.png)
![](image/latihan/9.png)

`Disini node2 dan node3 telah bergabung dengan swarm node1 sebagai Worker nodes.`

6. Melihat daftar node yang ada beserta keterangannya.

![](image/latihan/10.png)

7. Mendeploy container.

![](image/latihan/11.png))

8. Memastikan bahwa container telah berhasil di deploy.

![](image/latihan/12.png)

9. Menjalankan layanan yang sama dengan skala 7.

![](image/latihan/13.png)

10. Melihat layanan yang sedang berjalan.

![](image/latihan/14.png)

11. Menjalankan kembali layanan yang sama namun dengan skala 4.

![](image/latihan/15.png)

12. Melihat kembali layanan yang sedang berjalan.

![](image/latihan/16.png)

13. Melihat daftar node yang ada.

![](image/latihan/17.png)

14. Melihat daftar container.

![](image/latihan/18.png)

15. Melihat kembali daftar node yang ada.

![](image/latihan/19.png)

16. Mengubah availability node 2 menjadi drain.

![](image/latihan/20.png)

17. Mengecek hasilnya.

![](image/latihan/21.png)

18. Melihat container yang sedang berjalan pada node2.

![](image/latihan/22.png)

`Disini kosong karena node2 availability sebelumnya telah diubah menjadi drain.`

19. Melihat layanan yang sedang berjalan.

![](image/latihan/23.png)

`Disini terlihat bahwasanya layanan yang menggunakan node2 terhenti karena sama seperti sebelumnya tadi.`

20. Menghapus layanan.

![](image/latihan/24.png)

21. Melihat daftar container yang ada.

![](image/latihan/25.png)

22. Menghapus container.

![](image/latihan/26.png)

23. Menhapus swarm pada node1, 2 dan 3.

    ![](image/latihan/27.png)
    ![](image/latihan/28.png)
    ![](image/latihan/29.png)
