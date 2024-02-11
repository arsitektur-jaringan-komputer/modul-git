# Bermain di Local Repository

Setelah memahami konsep dasar dari Git, kita akan memulai dengan bermain-main di *local repository*. Kita akan memulai dengan membuat *repository*, melakukan *change*, dan melihat *history change*. 

> Local vs Remote Repository?
> Intinya, *local repository* merupakan *repository* yang berada pada *host machine* kalian. Dalam hal ini, *host machine* tersebut adalah komputer kalian. Sebaliknya, *remote repository* adalah *repository* yang terdapat pada *git server remote provider*, seperti GitHub. Keduanya bisa dihubungkan.

![img](https://cdn.discordapp.com/attachments/1206040429368451093/1206055278366294078/local-and-remote-git-repositories.png?ex=65da9d81&is=65c82881&hm=e5b395d92c7c834b4a2fe1de462443aeeeab86897d3c8cd243e09f4d3ae8a408&)

</br>

## Daftar Isi

Modul 2 ini berisi beberapa bahasan sebagai berikut.

- [Bermain di Local Repository](#bermain-di-local-repository)
  - [Daftar Isi](#daftar-isi)
  - [Setup Local Repository](#setup-local-repository)
    - [1. Create new repository](#1-create-new-repository)
    - [2. Clone repository](#2-clone-repository)
  - [Melakukan Changes](#melakukan-changes)
  - [Undo Changes](#undo-changes)
    - [1. Reset](#1-reset)
    - [2. Revert](#2-revert)
    - [3. Checkout](#3-checkout)
  - [Commit Changes](#commit-changes)
    - [1. Git add](#1-git-add)
    - [2. Git commit](#2-git-commit)
    - [3. Git push](#3-git-push)
  - [Conventional Commit Messages](#conventional-commit-messages)
    - [1. Type](#1-type)
    - [2. Scope](#2-scope)
    - [3. Description](#3-description)
  - [Branchs Management](#branchs-management)

</br>

## Setup Local Repository

Terdapat dua cara untuk menyiapkan *local repository*. 

### 1. Create new repository

Untuk membuat *repository* baru, hal pertama yang perlu kalian lakukan adalah menginisiasi git di dalam direktori yang akan kalian jadikan *repository*. Direktori ini akan menjadi *local repository*.

```
git init
```

Kemudian, untuk membuat *remote repository* dari *local repository* yang telah kalian buat, gunakan perintah ini.

```
git remote add origin <remote_repository_URL>
```

### 2. Clone repository

Selain membuat *repository* baru, kita juga bisa menduplikasi *repository* yang sudah ada di git ke *local repository* kita dengan perintah berikut.

```
git clone <repository_url>
```

</br>

## Melakukan Changes

Terdapat tiga jenis *change* atau perubahan:

1. Create: membuat file atau line baru, ditandai dengan warna hijau
2. Edit: mengubah file atau sebuah line, ditandai dengan warna biru.
3. Delete: menghapus file atau sebuah line, ditandai dengan warna merah.

![img](https://cdn.discordapp.com/attachments/1206040429368451093/1206040464726425630/image.png?ex=65da8fb5&is=65c81ab5&hm=16ebfe18e961f3411e7987ebaf1da9e11fe3d855939cc2bb2b3423fc4f1a13e7&)

*Changes* dapat dilihat menggunakan perintah berikut.

``` 
git diff
```

[img]()

</br>

## Undo Changes

Setelah mengubah, mungkin kalian ingin menunda perubahan yang kalian lakukan pada *repository*. Untuk itu, git menyediakan perintah untuk menunda perubahan yang kalian buat.

### 1. Reset

Reset berguna untuk mengatur ulang HEAD (pointer ke *commit* terakhir) atau mengembalikan *working directory* ke kondisi *commit* sebelumnya. Biasa digunakan untuk menunda *local private changes*.

```
git reset HEAD <file_name>    # Hapus perubahan di sebuah file
```

### 2. Revert

Revert berguna untuk membuat commit baru yang membatalkan perubahan oleh commit tertentu tanpa mengubah sejarah commit yang sudah ada. Sangat baik untuk menunda *shared public changes*.

```
git revert <commit_id>
```

### 3. Checkout

Checkout sebenarnya berfungsi untuk berpindah branch, namun bisa juga digunakan untuk mengembalikan file di working directory ke versi pada commit tertentu.

```
git checkout <branch_name>  # Pindah ke branch lain
git checkout <commit_id> -- <file>  # Mengembalikan keadaan sebuah file ke versi pada commit tertentu
```

Terdapat juga kondisi di mana kalian mungkin sudah membuat perubahan pada branch kalian, namun ingin berpindah ke branch lain. Kalian bisa menggunakan perintah berikut untuk menyembunyikan perubahan di branch kalian dan beralih ke branch lain tanpa perlu melakukan commit.

```
git stash
```

Untuk mengembalikan perubahan yang disimpan sebelumnya dari stash ke working directory, kalian bisa menggunakan perintah berikut.

```
git stash pop
```

</br>

## Commit Changes

![img](https://cdn.discordapp.com/attachments/1206040429368451093/1206120703158521876/1yHKzz1RaeLxtnDnnLcJVnA.png?ex=65dada70&is=65c86570&hm=6d6fa0e431f2b781282cf4b68969146943df0909f175341ba0a7fa774025a0a8&)

Bila perubahan yang kalian lakukan sudah *fix*, kalian dapat melakukan perintah-perintah berikut untuk memasukkan ke *remote repository*.

### 1. Git add

Git add dilakukan untuk memilih dan menambahkan perubahan yang telah dibuat ke staging area. Berikut adalah beberapa cara melakukan git add.

```
git add . # Menambahkan semua perubahan ke staging area
git add <file_name> # Menambahkan perubahan di satu file ke staging area
```

### 2. Git commit

Git commit adalah perintah yang digunakan untuk menyimpan perubahan yang telah ditambahkan ke staging area ke dalam *local repository* sebagai sebuah commit. Commit merupakan langkah penting karena merupakan cara untuk merekam riwayat perubahan dalam repositori. Setelah melakukan commit, perubahan yang dilakukan akan tercatat di riwayat *repository* kalian. Berikut adalah perintah untuk git commit.

```
git commit -m "commit message"
```

Kalian juga bisa mengubah commit terakhir atau menyatukan perubahan dalam commit terakhir tanpa membuat commit baru menggunakan perintah berikut.

```
git commit --amend
```

### 3. Git push

Git push dilakukan untuk mengirim perubahan yang telah di-commit di local repository ke remote repository. Berikut adalah perintah untuk melakukan git push.

```
git push
```

Terdapat juga perintah untuk memaksa push ke remote repository dengan mengganti sejarah commit di remote repository dengan sejarah commit dari local repository, yaitu `git push --force`. Namun, hal ini dapat berbahaya karena menghilangkan pekerjaan orang lain yang bekerja berdasarkan sejarah commit dari remote repository. Untuk itu, kalian bisa menggunakan perintah berikut untuk melakukan push paksa secara aman, yaitu dengan mendapat peringatan bila orang lain telah melakukan push berdasarkan remote repository.

```
git push --force-with-lease
```

> Penting: pastikan kalian telah berada di branch yang benar sebelum melakukan push, ya!

</br>

## Conventional Commit Messages

Selain mempermudah pekerjaan kolaborasi, git juga dapat dimanfaatkan untuk dokumentasi. Hal ini perlu dilakukan untuk mempermudah teman kerja kita memahami perubahan yang kita lakukan di *repository*. Salah satu cara mendokumentasikan pekerjaan kita adalah menggunakan [*conventional commit messages*](https://gist.github.com/qoomon/5dfcdf8eec66a051ecd85625518cfd13). 

Format commit dalam *conventional commit messages* adalah sebagai berikut.

```
<type>(<optional scope>): <description>
```

### 1. Type

- feat → Perubahan berupa penambahan atau penghapusan sebuah fitur.
- fix → *Bug fixing*, diikuti deskripsi mengenai *bug*. 
- docs → Memperbarui dokumentasi (README.md)
- style → Mengubah *style* kode tanpa mengubah logika dalam kode.
- chore → Menginstall atau memperbarui dependensi.
- refactor → Mengubah pendekatan kode, namun dengan hasil yang sama.
- test → Menambahkan atau mengoreksi tes.
- [Tipe lainnya](https://gist.github.com/qoomon/5dfcdf8eec66a051ecd85625518cfd13)

### 2. Scope

Bersifat opsional, hanya berguna untuk menambah informasi kontekstual. Contoh: `docs(readme): update installation instructions`.

### 3. Description

Deskripsi bersifat mandatori, dan berisikan deskripsi singkat mengenai perubahan yang dilakukan. Biasanya menggunakan *imperative*, *present tense*. Misalnya, *Update*, bukan *Updated* atau *Updates*.

</br>

## Branchs Management

Branching adalah membuat cabang pekerjaan dari cabang utama development dan melanjutkan pekerjaan kalian tanpa mengutak-atik cabang utama.

![img](https://cdn.discordapp.com/attachments/1206040429368451093/1206120063959048212/C0Sh78rxOPN47IG7iLD40znvkTU8q1AAAAAElFTkSuQmCC.png?ex=65dad9d7&is=65c864d7&hm=c4206c7e91e2a3fbc944af56e3d2fc422d14130c5e2d9f4e8ce53b0cd04a9df0&)

Pada umumnya, terdapat dua branch, yaitu Master dan Development. Branch Development biasa digunakan untuk melakukan push dari para developer. Kemudian, saat projek di branch development telah siap dan stabil, barulah branch development di-merge dengan branch master. Branch master biasanya dilindungi dari penulisan langsung oleh pengembang untuk mencehan perubahan yang tidak diinginkan.

Untuk membuat branch, digunakan perintah berikut.

```
git branch <nama_branch>
```

Untuk pindah ke branch lain, digunakan perintah berikut.

```
git checkout <nama_branch>
```

Kini kalian telah menguasai local repository yang ibaratnya adalah ruang kerja pribadi kalian. Berikutnya, kalian akan belajar mengenai kolaborasi tim dalam git.