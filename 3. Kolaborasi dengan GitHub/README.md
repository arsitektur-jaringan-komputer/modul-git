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

*Forking* adalah membuat salinan *repositor*y dari *repository* utama ke *repository* pribadi di akun kalian sendiri. *Forking* umumnya digunakan untuk berkontribusi pada *repository open-source* yang dikelola oleh orang lain. Dengan melakukan *fork*, kalian dapat bekerja pada salinan *repository* tersebut tanpa mengubah *repository* utama.

Setelah melakukan *fork*, kalian dapat melakukan perubahan pada *local repository* kalian, seperti membuat *branch* baru, melakukan perubahan, dan melakukan *commit*. Setelah itu, kalian dapat mengajukan *pull request* kepada pemilik *repository* utama untuk memasukkan perubahan kalian ke *repository* utama.

![img](https://cdn.discordapp.com/attachments/1206040429368451093/1207001205167886356/featured.png?ex=65de0e78&is=65cb9978&hm=7d0e3ae3017c157dc646fcd5e49f798503767048848c4bf5812178e269bddfe6&)

Berikut adalah cara *forking*:

1. Kalian dapat melakukan *forking* dengan membuka *repository* utama dari browser kalian, lalu membuka *dropdown* *fork* dan memilih *create a new fork*.

![img](https://cdn.discordapp.com/attachments/1206040429368451093/1206137744632451093/image.png?ex=65daea4f&is=65c8754f&hm=812e66e3c845b77411c166895304f223ffdf1927b25a98a2c73bbd1894b994e0&)

2. Kalian bisa mengatur nama dan deskripsi *repository* serta *branch* yang akan kalian *fork* sesuai kebutuhan.

![img](https://cdn.discordapp.com/attachments/1206040429368451093/1206138904491851877/image.png?ex=65daeb63&is=65c87663&hm=896eebf3be8b31ee4163d1286c07b7ad35a8a49600c87058682a7e695b05accb&)

3. Kemudian, kalian *clone repository* hasil *fork* dengan cara yang dijelaskan di bab sebelumnya.

Git Sync adalah memperbarui fork kalian dengan perubahan terbaru yang telah terjadi di *repository* utama. Ini memungkinkan *fork* kalian untuk tetap sinkron dengan perubahan terbaru yang telah terjadi di *repository* utama. Berikut adalah langkah-langkah untuk melakukan *syncing*:

1. Kalian perlu menambahkan *repository* utama sebagai *remote repository* kedua (atau disebut sebagai *upstream*) di *repository* *fork* kalian, dengan perintah sebagai berikut.

```
git remote add upstream <repository_name>
```

2. Kalian bisa memastikan *syncing* berhasil dengan perintah `git remote -v`.

![img](https://cdn.discordapp.com/attachments/1206040429368451093/1206152017433853972/image.png?ex=65daf79a&is=65c8829a&hm=0163767eae6fb7f9046b3aa87840c5211ab111cb780ed1d35b421ba93c0a6642&)

3. Ambil perubahan dari *upstream* dengan perintah berikut. 

```
git fetch upstream
git pull upstream <nama_branch>
```

![img](https://cdn.discordapp.com/attachments/1206040429368451093/1206142586402897960/image.png?ex=65daeed1&is=65c879d1&hm=cd48bb2844d897eb08f182a0f7d480d9ba49aa0e0c0696df5b050f9069f9be11&)

![img](https://cdn.discordapp.com/attachments/1206040429368451093/1206142767583989770/image.png?ex=65daeefc&is=65c879fc&hm=9aca09244106808a6d29573022cb9a87338c4068f031b3274b7e4c46435428c8&)

4. Kemudian, kalian bisa melakukan *pull* perubahan dari *repository* utama ke *fork* kalian, dan menerapkan perubahan tersebut di *local repository* kalian.


</br>

## GitHub Project, Backlog, dan Issue

Github Project adalah salah satu alat manajemen proyek, serupa dengan Trello dan Jira. Namun, Github Project dapat langsung dihubungkan dengan pengerjaan sebuah *repository* di Github. Berikut adalah contoh tampilan Github Project, yaitu berupa kartu-kartu yang merepresentasikan tugas, serta terhubung dengan *issues* dan *pull request*.

![img](https://cdn.discordapp.com/attachments/1083700228907085946/1206143219033833502/image.png?ex=65daef68&is=65c87a68&hm=bce10d27a3a9e2c77a348ef2f381bb393fb72746e56e3887befebf4d8c60e947&)

Backlog adalah tempat di mana semua ide, permintaan fitur, atau kebutuhan perbaikan dikumpulkan sebelum ditindaklanjuti atau dijadwalkan untuk implementasi. Dalam konteks GitHub, Backlog dapat direpresentasikan dengan menggunakan fitur Issue. 

Issue adalah alat yang digunakan untuk melacak tugas, *bug*, atau permintaan fitur dalam proyek. Setiap Issue memiliki judul, deskripsi, label, dan dapat ditetapkan kepada orang tertentu dalam tim. Melalui Github Project, Issue dapat ditugaskan kepada anggota tim tertentu untuk ditindaklanjuti, dan kemudian dapat dipindahkan melalui berbagai tahapan alur kerja, seperti *Ready*, *In Progress*, *In Review*, dan *Done*.

</br>

## Pull Request, Merge, dan Rebase

*Pull request* adalah permintaan yang kita ajukan kepada pemilik *repository* untuk menggabungkan (*merge*) perubahan yang telah dilakukan di *branch* kita ke dalam *branch* utama (biasanya *master* atau *development*). Di GitHub, *pull request* memungkinkan kita untuk membahas dan meninjau perubahan sebelum digabungkan ke dalam *repository* utama. Untuk melakukan *pull request*, biasanya pilihan untuk melakukan *pull request* akan muncul di halaman *remote repository* begitu kalian melakukan *push* ke *branch* kalian. 

![img](https://cdn.discordapp.com/attachments/1206040429368451093/1206185789718011915/image.png?ex=65db170e&is=65c8a20e&hm=a71e56ebad15f32ae54407bccc374b90daf8687d42d1c469e7ba24e8c6f4e641&)

Jika tidak ada, kalian juga bisa membuat *pull request* secara manual.

![img](https://github.com/arsitektur-jaringan-komputer/modul-git/blob/26428b10c1a42734e5f0ba22d3ebbd4906b5abb5/3.%20Kolaborasi%20dengan%20GitHub/img/3-20.png)

Deskripsi dari *pull request* yaitu daftar perubahan yang kalian kerjakan di *branch* kalian serta dokumentasinya, bisa berupa *screenshot* yang memperlihatkan bahwa pekerjaan kalian telah sesuai.

![img](https://cdn.discordapp.com/attachments/1206040429368451093/1206186086833983509/image.png?ex=65db1754&is=65c8a254&hm=9e56da04064b84359c7fabff0f0aea348051d87b68038223e3e24e77187f9841&)

*Merge* adalah proses menggabungkan perubahan dari satu *branch* ke *branch* lainnya di dalam *repository* Git. Ini biasanya dilakukan setelah *pull request* telah di-*review* dan disetujui. Ketika *pull request* yang kita ajukan di-*merge*, perubahan yang ada di *branch* kita akan digabungkan ke dalam *branch* target.

*Rebase* adalah proses mengubah sejarah *commit* di *branch* kita dengan menerapkan perubahan yang telah terjadi di *branch* target. Ini biasanya digunakan untuk menjaga sejarah *commit* tetap bersih dan rapi dengan memperbarui *branch development* dengan perubahan terbaru di *repository* utama. Kita dapat melakukan *rebase* dari *branch* target ke *branch development* mereka sebelum *pull request* di-*merge* untuk memastikan bahwa perubahan terbaru di *repository* utama telah disertakan.

</br>

## Menjadi Reviewer 101

Sebagai *reviewer*, tugas kita adalah mengecek apakah perubahan yang dibuat dalam sebuah *pull request* sudah benar atau belum. Pertama, kalian bisa mengecek perubahan yang dibuat dalam *pull request* tersebut.

![img](https://github.com/arsitektur-jaringan-komputer/modul-git/blob/26428b10c1a42734e5f0ba22d3ebbd4906b5abb5/3.%20Kolaborasi%20dengan%20GitHub/img/3-22.png)

Bila dirasa masih kurang sesuai, kalian bisa meninggalkan komentar.

![img](https://github.com/arsitektur-jaringan-komputer/modul-git/blob/26428b10c1a42734e5f0ba22d3ebbd4906b5abb5/3.%20Kolaborasi%20dengan%20GitHub/img/3-23.png)

Sudah sesuai? Langsung merge saja!

![img](https://github.com/arsitektur-jaringan-komputer/modul-git/blob/26428b10c1a42734e5f0ba22d3ebbd4906b5abb5/3.%20Kolaborasi%20dengan%20GitHub/img/3-17.png)

![img](https://github.com/arsitektur-jaringan-komputer/modul-git/blob/26428b10c1a42734e5f0ba22d3ebbd4906b5abb5/3.%20Kolaborasi%20dengan%20GitHub/img/3-16.png)


</br>

## Git Graph (Git Log)

Nah, salah satu keunggulan dari git adalah adanya Git Log. Git akan mencatat dan membuat alur history dari seluruh commit yang telah dibuat sebelumnya yang umum kita kenal dengan istilah logging. 
