# Praktikum Teknologi Cloud Computing - Minggu 8 (TUGAS)

## Diagram Keterkaitan antara Docker image, container, client, compose dan swarm.

<dd>

![](image/tugas/docker.png)

</dd>

Dari diagram yang saya rancang diatas, docker compose dapat menerima request dari file yml sehingga feedback yang diberikan dengan membaca file yml dan mengirim ke manage docker client, dimana cli dapat melakukan deklarasi build dan kemudian melakukan running dan kemudian dapat melakukan pull terhadap image container nanti. Apabila proses manage pada docker client melakukan request maka terlebih dahulu melalaui docker swarm untuk melakukan pengelompokan terhadap request yang diberikan dan kemudkan akan dilanjutkan ke dockerd/docker daemond, dimana pada docker dameond image dan container saling mengirim dan menerima feedback untuk selanjutnya memberikan feedback kepada docker cli untuk melakukan manage ulang terhadap kesalahan dll.
