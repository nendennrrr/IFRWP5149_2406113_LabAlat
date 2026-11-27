# LAPORAN PRAKTIKUM PERTEMUAN 6

## Activity Diagram: Proses Input Nilai Mata Kuliah sampai Lihat KHS

## 1. Tujuan

Tujuan dari praktikum ini adalah:

1.  Memahami cara menyusun *activity diagram* berdasarkan tabel skenario
    use case pada Pertemuan 5.
2.  Menggambarkan alur proses input nilai mata kuliah sampai mahasiswa
    dapat melihat Kartu Hasil Studi (KHS).
3.  Menerapkan empat *swimlane*, yaitu Dosen, Sistem, Admin Akademik,
    dan Mahasiswa, sesuai dengan tanggung jawab masing-masing.
4.  Menggunakan *decision* dan *merge* untuk menggambarkan pemeriksaan
    kelengkapan nilai serta alur perbaikan apabila nilai belum lengkap.
5.  Menggunakan *fork* dan *join* untuk menggambarkan dua proses yang
    berjalan secara paralel setelah nilai disahkan.
6.  Memastikan setiap *action* pada diagram dapat ditelusuri kembali ke
    langkah skenario SIA-UC08 dan SIA-UC09 pada Pertemuan 5.

## 2. Dasar Teori

### 2.1 Activity Diagram

*Activity diagram* merupakan salah satu diagram UML yang digunakan untuk
menggambarkan alur kegiatan dalam suatu proses. Diagram ini menunjukkan
urutan aktivitas, percabangan berdasarkan kondisi, proses yang berjalan
secara paralel, serta pembagian tanggung jawab setiap pelaku.

Dalam praktikum ini, *activity diagram* disusun berdasarkan tabel
skenario use case Pertemuan 5. Dengan demikian, setiap aktivitas yang
digambarkan harus memiliki sumber langkah yang jelas pada skenario
tersebut.

### 2.2 Unsur-Unsur Activity Diagram

Beberapa unsur yang digunakan dalam penyusunan diagram adalah:

  -----------------------------------------------------------------------
  Unsur                               Fungsi
  ----------------------------------- -----------------------------------
  Initial node                        Menunjukkan titik awal proses.

  Action                              Menunjukkan satu kegiatan atau
                                      langkah yang dilakukan oleh aktor
                                      maupun sistem.

  Control flow                        Menunjukkan urutan perpindahan dari
                                      satu aktivitas ke aktivitas
                                      berikutnya.

  Decision                            Menentukan percabangan alur
                                      berdasarkan kondisi tertentu.
                                      Setiap cabang diberi *guard*.

  Merge                               Menggabungkan kembali beberapa
                                      cabang keputusan menjadi satu alur.

  Fork                                Membagi satu alur menjadi beberapa
                                      proses yang berjalan secara
                                      paralel.

  Join                                Menyatukan kembali proses paralel
                                      sebelum alur dilanjutkan.

  Activity final node                 Menunjukkan bahwa seluruh proses
                                      telah selesai.

  Swimlane                            Mengelompokkan aktivitas
                                      berdasarkan aktor atau pihak yang
                                      bertanggung jawab.
  -----------------------------------------------------------------------

### 2.3 Decision dan Merge

*Decision* digunakan ketika proses memiliki lebih dari satu kemungkinan
berdasarkan kondisi tertentu. Pada proses input nilai, keputusan
dilakukan untuk memeriksa apakah nilai sudah lengkap. Cabang `[lengkap]`
melanjutkan proses ke pemeriksaan Admin Akademik, sedangkan cabang
`[belum lengkap]` mengarahkan proses kembali kepada Dosen untuk
melengkapi nilai.

Setelah nilai dilengkapi, alur digabungkan kembali menggunakan *merge*
agar proses dapat dilanjutkan ke tahap berikutnya.

### 2.4 Fork dan Join

*Fork* digunakan untuk membagi satu alur menjadi dua atau lebih
aktivitas yang dapat berjalan bersamaan. Sementara itu, *join* digunakan
untuk menyatukan kembali aktivitas paralel tersebut. Pada praktikum ini,
setelah nilai disahkan dan Sistem menyiapkan publikasi hasil studi,
terdapat dua aktivitas paralel, yaitu menerbitkan KHS pada portal
akademik dan mengirim pemberitahuan hasil studi kepada mahasiswa. Kedua
aktivitas harus selesai sebelum mahasiswa melihat KHS.

### 2.5 Swimlane

*Swimlane* merupakan pembagian area pada *activity diagram* berdasarkan
pihak yang melakukan aktivitas. Setiap *action* ditempatkan pada
*swimlane* yang sesuai agar tanggung jawab Dosen, Sistem, Admin
Akademik, dan Mahasiswa dapat dibedakan dengan jelas.

## 3. Hasil Praktikum

### 3.1 Deskripsi Proses

Praktikum menghasilkan rancangan *activity diagram* untuk proses Input
Nilai Mata Kuliah sampai Lihat KHS. Proses dimulai ketika Dosen
memasukkan nilai mata kuliah. Sistem kemudian menyimpan nilai dan
memeriksa kelengkapannya.

Apabila nilai belum lengkap, proses dikembalikan kepada Dosen untuk
melengkapi nilai yang masih kurang. Setelah dilengkapi, alur kembali ke
proses pemeriksaan. Apabila nilai sudah lengkap, Admin Akademik
melakukan pemeriksaan dan pengesahan nilai.

Setelah nilai disahkan, Sistem menyiapkan publikasi hasil studi.
Selanjutnya, proses dibagi menjadi dua aktivitas paralel, yaitu
menerbitkan KHS pada portal akademik dan mengirim pemberitahuan hasil
studi kepada mahasiswa. Setelah kedua aktivitas selesai, Mahasiswa dapat
melihat KHS dan proses berakhir.

### 3.2 Pembagian Swimlane

  -----------------------------------------------------------------------
  Swimlane                            Aktivitas
  ----------------------------------- -----------------------------------
  Dosen                               Memasukkan nilai mata kuliah dan
                                      melengkapi nilai mata kuliah yang
                                      belum lengkap.

  Sistem                              Menyimpan nilai, menyiapkan
                                      publikasi hasil studi, menerbitkan
                                      KHS pada portal akademik, dan
                                      mengirim pemberitahuan hasil studi
                                      kepada mahasiswa.

  Admin Akademik                      Memeriksa dan mengesahkan nilai.

  Mahasiswa                           Melihat KHS.
  -----------------------------------------------------------------------

### 3.3 Urutan Aktivitas

Urutan aktivitas yang digambarkan dalam diagram adalah:

1.  Proses dimulai dari *initial node*.
2.  Dosen memasukkan nilai mata kuliah.
3.  Sistem menyimpan nilai.
4.  Sistem memeriksa kelengkapan nilai melalui *decision*.
5.  Jika nilai belum lengkap (`[belum lengkap]`), Dosen melengkapi nilai
    mata kuliah yang belum lengkap. Setelah itu, alur kembali melalui
    *merge* untuk melanjutkan pemeriksaan.
6.  Jika nilai lengkap (`[lengkap]`), proses dilanjutkan ke Admin
    Akademik.
7.  Admin Akademik memeriksa dan mengesahkan nilai.
8.  Sistem menyiapkan publikasi hasil studi.
9.  *Fork* membagi proses menjadi dua aktivitas paralel:
    -   Sistem menerbitkan KHS pada portal akademik.
    -   Sistem mengirim pemberitahuan hasil studi kepada mahasiswa.
10. *Join* menyatukan kedua aktivitas setelah keduanya selesai.
11. Mahasiswa melihat KHS.
12. Proses berakhir pada *activity final node*.

### 3.4 Pemetaan Aktivitas ke Skenario Pertemuan 5

Pemetaan berikut menunjukkan sumber use case dari setiap aktivitas. Nama
dan rincian langkah perlu dicocokkan kembali dengan tabel skenario
SIA-UC08 dan SIA-UC09 milik praktikan.

  ------------------------------------------------------------------------
                    No. Aktivitas pada   Swimlane         Sumber Skenario
                        Activity Diagram                  
  --------------------- ---------------- ---------------- ----------------
                      1 Memasukkan nilai Dosen            SIA-UC08 Input
                        mata kuliah                       Nilai Mata
                                                          Kuliah

                      2 Menyimpan nilai  Sistem           SIA-UC08 Input
                                                          Nilai Mata
                                                          Kuliah

                      3 Memeriksa        Sistem           Pemeriksaan alur
                        kelengkapan                       pada tugas
                        nilai                             Pertemuan 6
                                                          berdasarkan
                                                          proses input
                                                          nilai

                      4 Melengkapi nilai Dosen            SIA-UC08 Input
                        mata kuliah yang                  Nilai Mata
                        belum lengkap                     Kuliah

                      5 Memeriksa dan    Admin Akademik   SIA-UC08 Input
                        mengesahkan                       Nilai Mata
                        nilai                             Kuliah

                      6 Menyiapkan       Sistem           Tahap setelah
                        publikasi hasil                   nilai disahkan
                        studi                             pada instruksi
                                                          tugas Pertemuan
                                                          6

                      7 Menerbitkan KHS  Sistem           SIA-UC09 Lihat
                        pada portal                       KHS
                        akademik                          

                      8 Mengirim         Sistem           Tahap publikasi
                        pemberitahuan                     hasil studi pada
                        hasil studi                       instruksi tugas
                        kepada mahasiswa                  Pertemuan 6

                      9 Melihat KHS      Mahasiswa        SIA-UC09 Lihat
                                                          KHS
  ------------------------------------------------------------------------

**Catatan:** Jobsheet Pertemuan 6 menetapkan urutan aktivitas utama dan
unsur diagram pada tugas ini. Untuk memenuhi keterlacakan secara tepat,
nomor atau bunyi langkah pada tabel di atas sebaiknya disesuaikan dengan
tabel skenario SIA-UC08 dan SIA-UC09 yang telah dibuat pada Pertemuan 5.
Aktivitas pemeriksaan kelengkapan, penyiapan publikasi, dan
pemberitahuan juga perlu dipastikan sesuai dengan rincian skenario yang
digunakan.

### 3.5 Unsur UML yang Diterapkan

  -----------------------------------------------------------------------
  Unsur                               Penerapan pada Diagram
  ----------------------------------- -----------------------------------
  Initial node                        Menandai awal proses input nilai.

  Decision                            Memeriksa apakah nilai sudah
                                      lengkap.

  Guard `[lengkap]`                   Mengarahkan proses ke Admin
                                      Akademik untuk pemeriksaan dan
                                      pengesahan.

  Guard `[belum lengkap]`             Mengarahkan proses kembali ke Dosen
                                      untuk melengkapi nilai.

  Merge                               Menggabungkan kembali alur setelah
                                      Dosen melengkapi nilai.

  Fork                                Membagi proses setelah Sistem
                                      menyiapkan publikasi hasil studi.

  Join                                Menyatukan proses penerbitan KHS
                                      dan pengiriman pemberitahuan.

  Activity final node                 Menandai akhir proses setelah
                                      Mahasiswa melihat KHS.
  -----------------------------------------------------------------------

## 4. Analisis

Berdasarkan rancangan proses, *activity diagram* membantu memperjelas
hubungan aktivitas antara Dosen, Sistem, Admin Akademik, dan Mahasiswa.
Pembagian empat *swimlane* membuat tanggung jawab masing-masing pihak
terlihat sehingga aktivitas tidak tertukar. Contohnya, kegiatan
memasukkan dan melengkapi nilai menjadi tanggung jawab Dosen, sedangkan
penyimpanan serta publikasi hasil studi dilakukan oleh Sistem.

Penggunaan *decision* memperlihatkan bahwa proses penginputan nilai
tidak selalu langsung dilanjutkan ke pengesahan. Nilai harus diperiksa
terlebih dahulu. Jika belum lengkap, proses kembali kepada Dosen.
Penggunaan *merge* diperlukan agar alur setelah perbaikan dapat
bergabung kembali sebelum proses diteruskan. Dengan demikian, nilai yang
belum lengkap tidak langsung masuk ke tahap pengesahan.

Penerapan *fork* dan *join* menunjukkan bahwa penerbitan KHS dan
pengiriman pemberitahuan dapat berlangsung secara paralel setelah nilai
disahkan. Kedua aktivitas tersebut tidak perlu digambarkan sebagai
proses yang harus menunggu satu sama lain. Namun, mahasiswa baru
diarahkan untuk melihat KHS setelah kedua aktivitas selesai dan
disatukan melalui *join*.

Secara keseluruhan, diagram harus memiliki satu *initial node* dan satu
*activity final node*, seluruh aktivitas harus terhubung, setiap cabang
*decision* harus memiliki *guard*, serta setiap aktivitas harus
ditempatkan pada *swimlane* yang tepat. Kesesuaian nama aktivitas dan
sumber langkah tetap perlu diperiksa menggunakan tabel skenario SIA-UC08
dan SIA-UC09 pada Pertemuan 5.

## 5. Kesimpulan

Berdasarkan praktikum yang dilakukan, dapat disimpulkan bahwa *activity
diagram* dapat digunakan untuk menggambarkan proses Input Nilai Mata
Kuliah sampai Lihat KHS secara runtut dan terstruktur. Melalui empat
*swimlane*, tanggung jawab Dosen, Sistem, Admin Akademik, dan Mahasiswa
dapat dibedakan dengan jelas.

Penggunaan *decision* dan *merge* membantu menggambarkan proses
pemeriksaan serta perbaikan nilai yang belum lengkap. Sementara itu,
*fork* dan *join* menggambarkan penerbitan KHS dan pengiriman
pemberitahuan yang berjalan secara paralel. Dengan demikian, diagram
dapat memberikan gambaran alur proses dari awal sampai akhir, selama
setiap aktivitas tetap sesuai dan dapat ditelusuri ke tabel skenario
SIA-UC08 dan SIA-UC09 pada Pertemuan 5.
