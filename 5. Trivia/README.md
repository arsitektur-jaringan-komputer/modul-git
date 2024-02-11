# Trivia



</br>

## Daftar Isi

Modul 5 ini berisi beberapa bahasan sebagai berikut.

- [Trivia](#trivia)
  - [Daftar Isi](#daftar-isi)
  - [GitHub Action](#github-action)
  - [Git Bisect](#git-bisect)
  - [Git Hooks](#git-hooks)
  - [Git Submodule](#git-submodule)
  - [Git LFS](#git-lfs)
  - [Git Flow](#git-flow)
  - [Git Server](#git-server)

</br>

## GitHub Action

GitHub Action adalah *workflow* yang digunakan untuk mengelola *branch* di dalam *repository*. Dengan menggunakan GitHub Action, kita bisa mengelola *branch* seperti *feature*, *release*, *hotfix*, dan *master*. Nah, salah satu contohnya, yaitu ketika kita ingin melakukan auto rebase dari branch development ke branch master. Kita bisa menggunakan GitHub Action untuk melakukan automasi hal tersebut. 

Untuk lebih lengkapnya, silahkan baca [dokumentasi resmi](https://docs.github.com/en/actions).

</br>

## Git Bisect

Git Bisect adalah perintah yang digunakan untuk mencari commit yang menyebabkan bug. Git Bisect akan melakukan *binary search* pada *commit history* untuk menemukan commit yang menyebabkan bug. Skenario yang sering terjadi adalah ketika kita menemukan bug pada *commit* terbaru, namun kita tidak tahu *commit* mana yang menyebabkan bug tersebut. Dengan menggunakan Git Bisect, kita bisa menemukan *commit* yang menyebabkan bug tersebut.  

```sh
git bisect start
git bisect bad
git bisect good <commit>
```

Untuk lebih lengkapnya, silahkan baca [dokumentasi resmi](https://git-scm.com/docs/git-bisect).

</br>

## Git Hooks

Git Hooks adalah *script* yang dijalankan secara otomatis ketika terjadi *event* tertentu pada Git. *Event* tersebut bisa berupa *commit*, *push*, *merge*, dan lain-lain. Dengan menggunakan Git Hooks, kita bisa melakukan *custom action* ketika *event* tersebut terjadi. 

Contoh penggunaan Git Hooks adalah ketika kita ingin menjalankan *unit test* setiap kali ada *commit* baru. Kita bisa menggunakan Git Hooks untuk menjalankan *unit test* setiap kali ada *commit* baru. 

```sh
#!/bin/sh
echo "Running unit test"
npm test
```

Untuk lebih lengkapnya, silahkan baca [dokumentasi resmi](https://git-scm.com/docs/githooks).


</br>

## Git Submodule

Git Submodule adalah cara untuk mengelola *repository* lain di dalam *repository* utama. Dengan menggunakan Git Submodule, kita bisa menambahkan *repository* lain ke dalam *repository* utama. 

```sh
git submodule add <url>
```

Untuk lebih lengkapnya, silahkan baca [dokumentasi resmi](https://git-scm.com/docs/git-submodule).

</br>

## Git LFS

Git LFS adalah cara untuk mengelola *file* besar di dalam *repository*. Dengan menggunakan Git LFS, kita bisa mengelola *file* besar seperti *image*, *video*, dan *file* lainnya. 

```sh
git lfs install
git lfs track "*.jpg"
```

Untuk lebih lengkapnya, silahkan baca [dokumentasi resmi](https://git-scm.com/docs/git-lfs).

</br>

## Git Flow

Git Flow adalah *workflow* yang digunakan untuk mengelola *branch* di dalam *repository*. Dengan menggunakan Git Flow, kita bisa mengelola *branch* seperti *feature*, *release*, *hotfix*, dan *master*.

Untuk lebih lengkapnya, silahkan baca [dokumentasi resmi](https://nvie.com/posts/a-successful-git-branching-model/).

</br>

## Git Server

Git Server adalah *workflow* yang digunakan untuk mengelola *branch* di dalam *repository*. Dengan menggunakan Git Server, kita bisa mengelola *branch* seperti *feature*, *release*, *hotfix*, dan *master*.

Untuk lebih lengkapnya, silahkan baca [dokumentasi resmi](https://git-scm.com/book/en/v2/Git-on-the-Server-Setting-Up-the-Server).
