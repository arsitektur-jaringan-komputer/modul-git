# Konsep Git sebagai VCS

Version Control System sangat penting dalam praktik DevOps dan DevSecOps modern. VCS memungkinkan *developer* bekerja secara terpisah tanpa mengganggu pekerjaan yang lain, mendukung Continuous Integration dan Delivery untuk otomatisasi, serta memfasilitasi kolaborasi antar tim. VCS juga membantu tim DevOps dan DevSecOps melacak perubahan kode dan konfigurasi sehingga penyebab masalah dapat diidentifikasi dengan cepat. Selain itu, VCS memudahkan untuk kembali ke versi sebelumnya jika diperlukan.

![DevOps dan Git](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-0.png)

Tapi, sebelum menuju ke pembahasan yang lebih dalam, apakah kalian sudah benar-benar memahami tentang VCS?

> Apakah kalian pernah menggunakan Google Docs? Jika pernah, maka harusnya kalian tidak asing dengan simbol *version history*. Nah, salah satu kegunaan dari VCS sama seperti itu.

Kita coba analogikan dengan pengerjaan tugas makalah berkelompok seperti saat di sekolah atau kuliah.

![Makalah](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-1.png)

Tentu kalian pernah menjumpai hal seperti itu, kan? Kalian harus mencatat dokumen untuk revisi pertama hingga seterusnya. Tidak lupa juga kalian harus mengunduh dan juga menggabungkan dengan pekerjaan teman-teman anggota kelompok kalian. Belum lagi, kalian tidak tahu, perubahan apa, bagaimana, dan di sebelah mana dilakukan perubahannya. Tentu sangat merepotkan, bukan? 

Nah, VCS hadir untuk mengatasi hal-hal seperti itu dalam pengembangan perangkat lunak dan sebagainya. Setiap perubahan kode dapat di-*track* baik itu dari perubahan kode, waktu, maupun siapa pengubahnya. Ingat, tidak ada *project* yang sempurna secara langsung. 

> Akan tetap selalu ada revisi di balik *project* yang sempurna.

## Daftar Isi

Modul 1 ini berisi beberapa bahasan sebagai berikut.

- [Konsep Git sebagai VCS](#konsep-git-sebagai-vcs)
  - [Daftar Isi](#daftar-isi)
  - [Git sebagai Version Control System](#git-sebagai-version-control-system)
  - [Area dalam Git dan Operasinya](#area-dalam-git-dan-operasinya)
  - [Berkenalan dengan GitHub dan Fiturnya](#berkenalan-dengan-github-dan-fiturnya)
  - [Set Up Remote Repository](#set-up-remote-repository)

</br>

## Git sebagai Version Control System

Git, adalah salah satu layanan VCS yang paling populer dan ramai digunakan saat ini. Git diciptakan oleh Linus Torvalds dimana pada awalnya digunakan untuk pengembangan kernel Linux. 

![Macam VCS](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-2.jpeg)

Git sendiri sebenarnya tidak hanya berperan sebagai VCS yang begitu-begitu saja. Setidaknya terdapat tiga peran dari git sebagai berikut.

1. VCS, yang terbagi menjadi tiga jenis:
    - Single User
    - Centralized
    - Distributed
2. Source Code Manager (SCM), dan
3. Revision Control System (RCS).

Selain itu, terdapat juga alasan mengapa git begitu populer, yaitu:
- Git memiliki fitur-fitur yang sekarang umum digunakan, seperti *branching*, *merging*, dan lainnya.
- Git memiliki fitur seperti *pull request*, *cherrypick*, dan lainnya.
- Git memiliki beberapa *tools* yang memudahkan pengguna dalam menggunakan git.
- Git gratis dan *open source*.
- Git memiliki komunitas yang begitu besar.
- Git juga didukung oleh berbagai *remote git server provider* seperti GitHub, Bitbucket, GitLab, dan lainnya yang menjadi media sosial bagi para developer.

![Syncing](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-3.png)

Dalam sebuah git repository (folder project), terdapat dua file, yaitu file project dan history file (biasanya hidden). Dengan git ini, dapat dilakukan undo ke suatu poin commit yang telah ter-track di history file sebelumnya.

</br>

## Area dalam Git dan Operasinya

Terdapat 3 (tiga) area di dalam git (*local*), yaitu **Working Directory**, **Staging Area**, dan **Repository**. *Working directory* adalah di mana pengerjaan kode dilakukan. Staging area adalah di mana perubahan-perubahan yang dilakukan pada *working directory* telah di-*track* oleh git. Sedangkan *repository* adalah di mana perubahan-perubahan yang telah di-*track* oleh git telah di-*commit*.

![Area](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-4.png)

> Simpelnya, dapat dituliskan seperti ini
> **Working Directory** —> *git add* —> **Staging Area** —> *git commit* —> **Repository** —> *git push* —> **Remote Repository**

Jika dilanjutkan, maka diagram sebelumnya dapat digambarkan sebagai berikut. Terdapat koneksi antara *local* dan *remote* repository. 

![Cont'd Area](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-5.png)

Jika diperhatikan, terdapat *command-command* yang mewakili transisi antar area yang ada pada git. Contohnya, antara *Working Directory* dan *Staging Area* menggunakan `git add`, antara *Staging Area* dan *Repository* menggunakan `git commit`, dan antara *Repository* dan *Remote Repository* menggunakan `git push`. Selain itu juga ada `git checkout` dan `git merge` yang ditunjukkan. Apakah kalian tahu apa fungsinya?

Selain keenam *command* tersebut, terdapat juga beberapa *command* yang umum digunakan pada git sebagai berikut.

| Perintah                  | Deskripsi                                                                                                                                                         |
|---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `git status`              | Menampilkan status *repository* saat ini.                                                                                                                          |
| `git add`                 | Menambahkan file dalam *Working* *Directory* ke *Staging* *Area*. Dapat semua *file* (`git add .`) atau spesifik *file*.                                                      |
| `git commit`              | Menambahkan semua *file* perubahan pada satu *Repository* dengan pesan *commit*. Disarankan menggunakan aturan *conventional* *commit*.                                      |
| `git push`                | Mengunggah *Repository* ke *Remote* *Repository*.                                                                                                                      |
| `git diff`                | Melihat perubahan yang terjadi dalam *project* dibandingkan dengan versi sebelumnya.                                                                                |
| `git stash`               | Menyimpan perubahan sementara (*Stash* Area) untuk mengatasi *conflict*. Gunakan `git stash apply` untuk mengembalikannya.                                             |
| `git log --oneline`       | Melihat riwayat *commit* disertai dengan ID dan *commit* *message* dalam satu baris.                                                                                   |
| `git reset (id commit)`   | Mengembalikan ke poin tertentu. `--soft` mempertahankan perubahan di *Staging* *Area*, `--hard` menghapus perubahan tersebut. Hindari penggunaan `git reset` jika tidak diperlukan. |
| `git fetch`               | Mengambil data *update* dari *Remote* *Repository* tanpa menggabungkannya ke dalam *Local Repository*.                                                                    |
| `git pull`                | Menarik data update keseluruhan (gabungan dari `git fetch` dan `git merge`) dari *Remote* *Repository* ke dalam *Local Repository*.                                          |

![Another git](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-6.png)

*Command-command* tersebut akan dipelajari seiring waktu modul ini berjalan. 

</br>

## Berkenalan dengan GitHub dan Fiturnya

GitHub adalah *remote git server provider* yang paling populer saat ini. GitHub memiliki beberapa fitur yang memudahkan pengguna dalam menggunakan git, seperti *pull request*, *issue*, *project*, *wiki*, *action*, dan lainnya. Kalian tentu sudah memiliki akun GitHub, bukan?

Fitur-fitur GitHub yang paling sering digunakan adalah sebagai berikut.

- **Repository**
    
    Tempat menyimpan *project* yang dikerjakan. Contohnya seperti *repository* modul ini.

    ![GitHub 1](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-7.png)

- **Issues**
  
    Tempat untuk melaporkan *bug* atau *feature request*.

    ![GitHub 1](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-8.png)

- **Pull Request**

    Tempat untuk menggabungkan *branch* yang telah dikerjakan.

    ![GitHub 1](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-9.png)

- **Project**

    Tempat untuk mengatur *project* yang dikerjakan, mirip seperti Trello atau Jira Workspace. Hal yang keren adalah GitHub Project ini langsung terkoneksi dengan *repository* yang sedang dikerjakan.

    ![GitHub 1](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-10.png)

- **Action**

    Tempat untuk membuat *workflow* otomatisasi.

    ![GitHub 1](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-11.png)


Selain itu, ada juga fitur-fitur yang juga sangat berguna nantinya sebagai berikut.

- **Wiki**: Tempat untuk membuat dokumentasi *project*.
- **Security**: Tempat untuk melihat *security* *vulnerability*.
- **Insights**: Tempat untuk melihat *analytics* *project*.

Terdapat fitur lain, namun tidak dicantumkan karena tidak akan dibahas pada modul lanjutan. Kalian bisa melakukan eksplorasi sendiri terhadap fitur-fitur lain pada GitHub!

</br>

## Set Up Remote Repository

Setelah memahami tentang git dan GitHub, kalian tentu ingin membuat *remote repository* di GitHub, bukan? Caranya sangat mudah, yaitu sebagai berikut.

1. Buka [GitHub](https://github.com) dan login dengan akun GitHub kalian.
   
   ![Setup 1](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-12.png)

2. Klik tombol `+` di pojok kanan atas dan pilih `New repository`.
   
   ![Setup 1](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-13.png)

3. Isi nama *repository* dan deskripsi *repository* kalian.
   
   ![Setup 1](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-14.png)

4. Pilih *visibility* *repository* kalian, apakah *public* atau *private*.
   
   ![Setup 1](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-15.png)

5. Pilih *license repository* kalian. Umumnya, *license* yang digunakan untuk *open source* adalah *MIT License*.
   
   ![Setup 1](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-16.png)

6. Pilih *initialize* *repository* dengan *README* atau tidak.
   
   ![Setup 1](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-17.png)

7. Klik tombol `Create repository`.
   
   ![Setup 1](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-18.png)

8. *Remote repository* kalian telah berhasil dibuat dengan *default branch* `main`.
   
   ![Setup 1](https://github.com/arsitektur-jaringan-komputer/pelatihan-git/blob/development/1.%20Konsep%20Git%20sebagai%20VCS/img/1-19.png)

Setelah itu, kalian dapat mengatur *reppository* yang baru saja kalian buat. Ada bebera hal yang bisa diatur, seperti *branch protection*, *manage collaborator*, dan lainnya. Lakukan eksplorasi sebanyak mungkin, ya!

![Oniel](https://media1.tenor.com/m/CznyqgN_zv8AAAAC/onieljkt48-jkt48oniel.gif)


