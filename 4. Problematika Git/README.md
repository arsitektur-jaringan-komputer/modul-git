# Problematika Git

Sebagai seorang *developer*, pasti semua orang pernah mengalami momen yang menantang dan memusingkan, terutama dalam mengelola VCS. Salah satu situasi yang sering kali menjadi hambatan adalah saat menghadapi konflik penggabungan (merge-conflict). Bagaimana denganmu? Apakah kalian memiliki pengalaman atau pendapat tertentu terkait situasi ini?

</br>

## Daftar Isi

Modul 4 ini berisi beberapa bahasan sebagai berikut.

- [Problematika Git](#problematika-git)
  - [Daftar Isi](#daftar-isi)
  - [Kasus-Kasus yang Sering Terjadi](#kasus-kasus-yang-sering-terjadi)
  - [Mengatasi Conflict](#mengatasi-conflict)
  - [Mengatasi Conflict](#mengatasi-conflict-1)
    - [Melakukan Undo](#melakukan-undo)
    - [Resolve Conflict](#resolve-conflict)
  - [Cherrypicking](#cherrypicking)

</br>

## Kasus-Kasus yang Sering Terjadi

Bagi yang sudah mencoba-coba apa yang dipelajari pada topik sebelumnya, mungkin kalian pernah mendapatkan beberapa kasus berikut yang akhirnya memunculkan *conflict*

- Mengembalikan perubahan yang disimpan di git stash.
- Mengambil perubahan dari remote branch dengan perintah git pull.
- Menjalankan perintah git merge untuk menyatukan perubahan ke branch master.
- Menjalankan perintah git rebase untuk mengintegrasikan perubahan pada current branch dengan branch master.
- Memilih beberapa commit untuk dipindahkan ke branch lain dengan perintah git cherry-pick.

Meskipun begitu, setiap aksi di atas tidak selalu menghasilkan conflict karena Git dapat menentukan cara mengaplikasikan perubahan antara dua source yang berbeda. 

Namun, pada situasi tertentu Git juga akan sulit untuk menentukan perubahan yang akan diterapkan, salah satunya contradictory changes (perubahan yang menimbulkan pertentangan) saat terdeteksi terdapat perubahan yang bertentangan pada suatu file atau komponen. Biasanya hal ini terjadi ketika terdapat dua commit berbeda yang melakukan perubahan pada lokasi yang sama. Selain itu, juga bisa terjadi karena adanya perbedaan file akibat dihapus atau diubah. Misalnya, diubah lokasi file-nya.

## Mengatasi Conflict

Setelah terdeteksi adanya conflict, Git akan menunjukkan pesan error. Saat itu juga proses merging akan gagal dilakukan. Berikut contoh pesan error yang muncul setelah Git berusaha untuk melakukan merge antar-branch.

![Conflict](https://www.dicoding.com/blog/wp-content/uploads/2022/08/Untitled-1.png)

Pastikan kalian mendapatkan informasi perubahan yang gagal di-merge. kalian juga dapat menggunakan perintah git status untuk mendapatkan status kondisi branch saat itu. Dalam kasus ini, Git akan mengembalikan informasi perubahan yang gagal di-merge beserta lokasinya, contoh pada kasus ini adalah file todolist_140822.text. 

![Conflict 2](https://www.dicoding.com/blog/wp-content/uploads/2022/08/Untitled-2.png)

## Mengatasi Conflict

Conflict memang tidak dapat diabaikan sehingga tidak ada kata lain selain mengatasinya. Ada dua langkah yang dapat kalian lakukan untuk mengatasi conflict.

### Melakukan Undo

Pada kasus tertentu, kalian dapat menggunakan parameter `–abort`. Misalnya, untuk kasus `merge` dan `rebase` menggunakan perintah `git merge –abort` dan `git rebase –abort`. Hal tersebut dapat mengembalikan kondisi sebelum conflict terjadi. Cara ini juga dapat dilakukan ketika kalian menemukan jalan buntu dalam proses perbaikan conflict.

### Resolve Conflict

Saat berpapasan dengan conflict maka keinginan yang terbesit adalah bagaimana agar perubahan yang kita lakukan masih dapat diterapkan berdampingan dengan perubahan dari source yang lain. Jika perubahan yang terjadi hanya pada file yang kalian buat sendiri, kalian dapat menyelesaikannya secara mandiri. Namun, lain ceritanya jika conflict terjadi karena perubahan lain berasal dari orang lain, pastinya kalian perlu persetujuan darinya sebelum menentukan perubahan yang ingin dipertahankan.

Proses resolve juga dapat dilakukan langsung pada IDE (Integrated Development Environment). Pada masa sekarang, IDE dapat terintegrasi dengan Git atau layanan Github dan sudah didukung visualisasi atau GUI (Graphical user interface) yang akan memudahkan kalian untuk mengetahui perubahan yang ditambahkan pada suatu source. Contohnya, adalah Visual Studio Code, yang juga menjadi alasan mengapa modul ini merekomendasikan untuk menggunakan VS Code tersebut.

![Resolving](https://www.dicoding.com/blog/wp-content/uploads/2022/08/Screenshot-from-2022-08-19-10-23-52-1024x592.png)

Seperti pada gambar di atas ini, terdapat dua source yang menambahkan perubahan pada file yang sama. Selanjutnya, kalian dapat menentukan bagian mana yang ingin kalian pertahankan atau resolve sebelum melanjutkan proses rebase/merge. Pada umumnya, kalian akan mendapat empat pilihan dalam proses resolve ini. Mari kita gambarkan apabila kasus ini terjadi antara source milikmu dan temanmu. Untuk memudahkan pemahamanmu terkait hal tersebut, perhatikan penjelasan di bawah ini.

- Keep yours (Hanya perubahan dari source milikmu yang akan diterapkan).
- Keep theirs (Hanya perubahan dari source milik temanmu yang akan diterapkan).
- Keep both (Perubahan dari kedua source milikmu dan temanmu akan diterapkan).
- Remove both (Perubahan dari kedua source akan dihapus).


</br>

## Cherrypicking

Ketika project terlalu berantakan dan banyak conflict, pernahkah kalian berfikir untuk kembali ke suatu versi kode yang lama? Tentu pernah, bukan? Hal itu memang naluri alamiah dari manusia. Nah, sekarang coba kalian coba untuk melakukan undo pada working directory kalian dengan CTRL + Z. Apakah muncul versi kode kalian sebelumnya? Jawabannya pasti tidak!

Di sini, kalian harus tahu tentang cherrypicking. Git Cherrypick adalah salah satu fitur yang powerful dalam Git yang memungkinkan kalian untuk mengambil satu atau beberapa commit tertentu dari satu branch dan menerapkan mereka ke branch lain. Ini akan sangat berguna ketika kalian hanya ingin memindahkan perubahan tertentu dari satu branch ke branch lain tanpa harus menggabungkan seluruh history commit.

![cherrypick](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/02ff0d17f2f1e45bc83c493239429fab5f498590/4.%20Problematika%20Git/img/1-10.png)

Langkah-langkahnya cukup sederhana. Pertama, pastikan kalian berada di branch tujuan tempat kalian ingin menerapkan perubahan. Misalnya, jika kalian ingin menerapkan commit dari branch feature-branch ke main, pastikan kalian berada di branch main.

```
git checkout <nama-branch-tujuan>
```

Lalu, lakukan cherrypick. Kalian perlu melihat commit-hash dari commit yang kalian inginkan untuk diambil dengan cherrypick.

```
git cherry-pick <commit-hash>
```

Kalian juga bisa mengambil beberapa commit sekaligus selama masih memiliki history commit yang linear.

```
git cherry-pick <commit-hash-awal>..<commit-hash-akhir>

```

Setelah menyelesaikan cherrypick dan menangani konflik (jika ada), kalian dapat menyimpan perubahan dengan commit baru atau menggunakan opsi -m untuk menyertakan pesan commit asli.