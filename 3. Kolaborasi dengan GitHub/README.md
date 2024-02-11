# Kolaborasi dengan GitHub



</br>

## Daftar Isi

Modul 3 ini berisi beberapa bahasan sebagai berikut.

- [Kolaborasi dengan GitHub](#kolaborasi-dengan-github)
  - [Daftar Isi](#daftar-isi)
  - [Fork dan Sync Git](#fork-dan-sync-git)
  - [GitHub Project, Backlog, dan Issue](#github-project-backlog-dan-issue)
  - [Pull Request, Merge, dan Rebase](#pull-request-merge-dan-rebase)
  - [Menjadi Reviewer 101](#menjadi-reviewer-101)
  - [Git Graph (Git Log)](#git-graph-git-log)

</br>

## Fork dan Sync Git

Forking adalah membuat salinan repository dari repository utama ke repository pribadi di akun kalian sendiri. Forking umumnya digunakan untuk berkontribusi pada repository open-source yang dikelola oleh orang lain. Dengan melakukan fork, kalian dapat bekerja pada salinan proyek tersebut tanpa mengubah repository utama.

Setelah melakukan fork, kalian dapat melakukan perubahan pada salinan proyek di repositori kalian, seperti membuat branch baru, melakukan perubahan, dan melakukan commit seperti dalam repositori lokal kalian sendiri. Setelah itu, kalian dapat mengajukan pull request kepada pemilik proyek utama untuk memasukkan perubahan kalian ke proyek utama.

Kalian dapat melakukan forking dengan membuka repository utama dari browser kalian, lalu membuka dropdown fork dan memilih create a new fork.

![img](https://cdn.discordapp.com/attachments/1206040429368451093/1206137744632451093/image.png?ex=65daea4f&is=65c8754f&hm=812e66e3c845b77411c166895304f223ffdf1927b25a98a2c73bbd1894b994e0&)

Kalian bisa mengatur nama dan deskripsi repository serta branch yang akan kalian fork sesuai kebutuhan.

![img](https://cdn.discordapp.com/attachments/1206040429368451093/1206138904491851877/image.png?ex=65daeb63&is=65c87663&hm=896eebf3be8b31ee4163d1286c07b7ad35a8a49600c87058682a7e695b05accb&)

Kemudian, kalian clone repository hasil fork dengan cara yang dijelaskan di bab sebelumnya.

Git sync adalah memperbarui fork kalian dengan perubahan terbaru yang telah terjadi di repositori utama. Untuk melakukan syncing, kalian perlu menambahkan repositori utama sebagai remote kedua di repositori fork kalian, dengan perintah sebagai berikut.

```
git remote add upstream <repository_name>
```

Kalian bisa memastikan syncing berhasil dengan perintah `git remote -v`.

![img](https://cdn.discordapp.com/attachments/1206040429368451093/1206152017433853972/image.png?ex=65daf79a&is=65c8829a&hm=0163767eae6fb7f9046b3aa87840c5211ab111cb780ed1d35b421ba93c0a6642&)

Ambil perubahan dari upstream dengan perintah berikut. 

```
git fetch upstream
git pull upstream <nama_branch>
```

![img](https://cdn.discordapp.com/attachments/1206040429368451093/1206142586402897960/image.png?ex=65daeed1&is=65c879d1&hm=cd48bb2844d897eb08f182a0f7d480d9ba49aa0e0c0696df5b050f9069f9be11&)

![img](https://cdn.discordapp.com/attachments/1206040429368451093/1206142767583989770/image.png?ex=65daeefc&is=65c879fc&hm=9aca09244106808a6d29573022cb9a87338c4068f031b3274b7e4c46435428c8&)

Anda kemudian bisa menarik (pull) perubahan dari repositori utama ke fork Anda, dan menerapkan perubahan tersebut di repositori lokal atau fork Anda.
Ini memungkinkan Anda untuk tetap up-to-date dengan proyek utama dan menjaga fork Anda tetap sinkron dengan perubahan terbaru yang telah terjadi di repositori utama.

</br>

## GitHub Project, Backlog, dan Issue

cakno

</br>

## Pull Request, Merge, dan Rebase

kanza pr
nur sing review
    kalo udah ok, merge
    kalo belum, kasih comment
kanza revisi, nur acc
merge vs rebase

</br>

## Menjadi Reviewer 101

how to read changes
how to give comment
how to approve
how to reject

</br>

## Git Graph (Git Log)

Nah, salah satu keunggulan dari git adalah adanya Git Log. Git akan mencatat dan membuat alur history dari seluruh commit yang telah dibuat sebelumnya yang umum kita kenal dengan istilah logging. Git akan melakukan  