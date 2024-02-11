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

Github project adalah salah satu alat manajemen proyek, serupa dengan Trello dan Jira. Namun, github project dapat langsung dihubungkan dengan pengerjaan sebuah repository di Github. Berikut adalah contoh tampilan github project, yaitu berupa kartu-kartu yang merepresentasikan tugas, serta terhubung dengan issues dan pull request.

![img](https://cdn.discordapp.com/attachments/1083700228907085946/1206143219033833502/image.png?ex=65daef68&is=65c87a68&hm=bce10d27a3a9e2c77a348ef2f381bb393fb72746e56e3887befebf4d8c60e947&)

Backlog adalah daftar tugas, fitur, atau perbaikan yang perlu diselesaikan dalam proyek. Ini adalah tempat di mana semua ide atau permintaan fitur dikumpulkan sebelum mereka ditindaklanjuti atau dijadwalkan untuk implementasi.
Dalam konteks GitHub, backlog dapat direpresentasikan dengan menggunakan fitur Issues. Issue adalah alat yang digunakan untuk melacak tugas, bug, atau permintaan fitur dalam proyek. Setiap issue memiliki judul, deskripsi, label, dan dapat ditetapkan kepada orang tertentu dalam tim. Melalui github project, issues dapat ditugaskan kepada anggota tim tertentu untuk ditindaklanjuti, dan kemudian dapat dipindahkan melalui berbagai tahapan alur kerja, seperti Ready, In Progress, In Review, dan Done.

</br>

## Pull Request, Merge, dan Rebase

Pull Request adalah permintaan yang kita ajukan kepada pemilik repositori untuk menggabungkan (merge) perubahan yang telah dilakukan di cabang (branch) pengembang ke dalam cabang utama (biasanya master atau development) repositori. Di GitHub, Pull Request memungkinkan kita untuk membahas dan meninjau perubahan sebelum digabungkan ke dalam repositori utama. 

Merge adalah proses menggabungkan perubahan dari satu cabang ke cabang lainnya di dalam repositori Git. Ini biasanya dilakukan setelah Pull Request telah direview dan disetujui. Ketika sebuah Pull Request di-merge, perubahan yang ada di cabang pengembang akan digabungkan ke dalam cabang target.

Rebase adalah proses mengubah sejarah commit di branch kita dengan menerapkan perubahan yang telah terjadi di branch target. Ini biasanya digunakan untuk menjaga sejarah commit tetap bersih dan rapi dengan memperbarui branch development dengan perubahan terbaru di repositori utama. Kita dapat melakukan rebase dari branch target ke branch development mereka sebelum Pull Request di-merge untuk memastikan bahwa perubahan terbaru di repositori utama telah disertakan.

</br>

## Menjadi Reviewer 101

Sebagai reviewer, tugas kita adalah mengecek apakah perubahan yang dibuat dalam sebuah pull request sudah benar atau belum. Kita bisa mengkomentari sebuah pull request dan melakukan merge apabila perubahan yang dibuat sudah benar.

</br>

## Git Graph (Git Log)

Nah, salah satu keunggulan dari git adalah adanya Git Log. Git akan mencatat dan membuat alur history dari seluruh commit yang telah dibuat sebelumnya yang umum kita kenal dengan istilah logging. 
