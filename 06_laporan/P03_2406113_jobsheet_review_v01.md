# LAPORAN PRAKTIKUM PERTEMUAN 3
## USE CASE DIAGRAM DAN USE CASE DESCRIPTION

## 1. Tujuan Praktikum

1. Memahami konsep Use Case Diagram dalam pemodelan sistem.
2. Mengidentifikasi aktor yang berinteraksi dengan sistem.
3. Menentukan kebutuhan fungsional berdasarkan skenario yang diberikan.
4. Memahami penggunaan relasi `include` dan `extend` pada Use Case Diagram.
5. Menyusun katalog Use Case berdasarkan kebutuhan sistem.
6. Membuat Use Case Description untuk menjelaskan alur interaksi antara aktor dan sistem.

## 2. Dasar Teori

### 2.1 Use Case Diagram

Use Case Diagram merupakan salah satu diagram UML (Unified Modeling Language) yang digunakan untuk menggambarkan hubungan antara aktor dengan fungsi-fungsi yang tersedia dalam suatu sistem. Diagram ini membantu menjelaskan layanan yang dapat digunakan oleh setiap aktor sesuai dengan hak akses dan perannya.

### 2.2 Aktor

Aktor merupakan pihak yang berinteraksi dengan sistem, baik berupa manusia maupun sistem lain. Aktor memiliki tujuan tertentu ketika menggunakan sistem. Contohnya adalah mahasiswa, petugas laboratorium, kepala laboratorium, admin akademik, dan dosen wali.

### 2.3 Use Case

Use Case merupakan gambaran fungsi atau layanan yang disediakan oleh sistem untuk memenuhi kebutuhan aktor. Setiap Use Case menjelaskan suatu tujuan yang ingin dicapai aktor melalui interaksi dengan sistem.

### 2.4 Relasi Include

Relasi `include` digunakan ketika suatu Use Case selalu membutuhkan perilaku dari Use Case lain sebagai bagian dari prosesnya. Dengan demikian, Use Case yang disertakan menjadi bagian wajib dari proses utama.

### 2.5 Relasi Extend

Relasi `extend` digunakan untuk menggambarkan perilaku tambahan yang hanya dijalankan apabila kondisi tertentu terpenuhi. Use Case utama tetap dapat berjalan meskipun perilaku tambahan tersebut tidak dilakukan.

### 2.6 Use Case Description

Use Case Description merupakan penjelasan tertulis mengenai suatu Use Case. Deskripsi ini biasanya mencakup nama Use Case, aktor, tujuan, kondisi awal, kondisi akhir, alur utama, serta alur alternatif.

## 3. Hasil Praktikum

### 3.1 Sistem Peminjaman Peralatan Laboratorium

#### A. Deskripsi Skenario

Mahasiswa dapat melihat ketersediaan peralatan dan mengajukan peminjaman dengan memilih peralatan, jumlah, serta rentang waktu peminjaman. Sistem akan memeriksa ketersediaan peralatan sebelum pengajuan disimpan. Apabila peralatan tersedia dan data telah lengkap, pengajuan disimpan dengan status Menunggu Keputusan.

Setelah pengajuan berhasil, mahasiswa dapat memilih untuk mencetak bukti pengajuan. Petugas laboratorium bertugas mengelola data peralatan serta memberikan keputusan berupa persetujuan atau penolakan pengajuan. Sementara itu, kepala laboratorium dapat melihat laporan peminjaman.

#### B. Tabel Kebutuhan Fungsional

| ID | Kebutuhan Fungsional |
|---|---|
| LAB-R01 | Mahasiswa dapat melihat ketersediaan peralatan. |
| LAB-R02 | Petugas dapat mengelola data peralatan. |
| LAB-R03 | Mahasiswa dapat mengajukan peminjaman dan sistem memeriksa ketersediaan sebelum menyimpan pengajuan. |
| LAB-R04 | Mahasiswa dapat mencetak bukti pada konfirmasi pengajuan jika memilihnya. |
| LAB-R05 | Petugas dapat menetapkan persetujuan atau penolakan pengajuan. |
| LAB-R06 | Kepala laboratorium dapat melihat laporan peminjaman. |

#### C. Identifikasi Aktor

| Aktor | Tujuan terhadap Sistem |
|---|---|
| Mahasiswa | Melihat ketersediaan, mengajukan peminjaman, dan mencetak bukti pengajuan. |
| Petugas Laboratorium | Mengelola data peralatan dan memproses keputusan peminjaman. |
| Kepala Laboratorium | Melihat laporan peminjaman. |

#### D. Katalog Use Case

| ID Use Case | Nama Use Case | Peran dalam Model |
|---|---|---|
| LAB-UC01 | Lihat Ketersediaan Peralatan | Fungsi utama mahasiswa. |
| LAB-UC02 | Kelola Data Peralatan | Fungsi utama petugas laboratorium. |
| LAB-UC03 | Ajukan Peminjaman | Fungsi utama mahasiswa. |
| LAB-UC04 | Periksa Ketersediaan | Perilaku wajib yang disertakan dalam UC03. |
| LAB-UC05 | Cetak Bukti Pengajuan | Perilaku tambahan jika mahasiswa memilih mencetak bukti. |
| LAB-UC06 | Proses Keputusan Peminjaman | Fungsi petugas untuk menyetujui atau menolak pengajuan. |
| LAB-UC07 | Lihat Laporan Peminjaman | Fungsi utama kepala laboratorium. |

#### E. Relasi Antar Use Case

**1. Relasi Include**

LAB-UC03 `<<include>>` LAB-UC04

Alasan: Pemeriksaan ketersediaan merupakan bagian wajib dari proses pengajuan peminjaman. Sistem harus memeriksa ketersediaan peralatan sebelum pengajuan berhasil disimpan.

**2. Relasi Extend**

LAB-UC05 `<<extend>>` LAB-UC03

- Extension Point: Bukti pengajuan tersedia.
- Kondisi: Mahasiswa memilih untuk mencetak bukti.
- Alasan: Pencetakan bukti merupakan tindakan tambahan yang bersifat opsional. Pengajuan tetap berhasil meskipun mahasiswa tidak mencetak bukti.

#### F. Batas Sistem dan Aturan

1. Sistem hanya mencatat dan menyediakan informasi peminjaman. Perpindahan fisik peralatan tidak termasuk dalam proses perangkat lunak.
2. Pengguna telah melakukan autentikasi dan memiliki hak akses sesuai perannya.
3. Pengajuan yang berhasil disimpan memiliki status Menunggu Keputusan, bukan otomatis Disetujui.
4. Pengajuan dengan peralatan yang tidak tersedia tidak disimpan sebagai pengajuan berhasil.
5. Pencetakan bukti bukan merupakan syarat keberhasilan pengajuan.
6. Persetujuan petugas belum dimodelkan sebagai reservasi teknis stok.
7. Pengambilan, pengembalian, kondisi peralatan, dan denda belum termasuk dalam model ini.

#### G. Use Case Description

**1. Use Case LAB-UC01 – Lihat Ketersediaan Peralatan**

| Komponen | Deskripsi |
|---|---|
| Nama Use Case | Lihat Ketersediaan Peralatan |
| ID | LAB-UC01 |
| Aktor | Mahasiswa |
| Tujuan | Mengetahui ketersediaan peralatan laboratorium. |
| Kondisi Awal | Mahasiswa telah login ke sistem. |
| Kondisi Akhir | Informasi ketersediaan peralatan ditampilkan. |
| Alur Utama | 1. Mahasiswa membuka menu ketersediaan peralatan. 2. Sistem mengambil data peralatan. 3. Sistem menampilkan daftar peralatan beserta informasi ketersediaannya. 4. Mahasiswa melihat informasi peralatan. |

**2. Use Case LAB-UC03 – Ajukan Peminjaman**

| Komponen | Deskripsi |
|---|---|
| Nama Use Case | Ajukan Peminjaman |
| ID | LAB-UC03 |
| Aktor | Mahasiswa |
| Tujuan | Mengajukan peminjaman peralatan laboratorium. |
| Kondisi Awal | Mahasiswa telah login dan data peralatan tersedia. |
| Kondisi Akhir | Pengajuan tersimpan dengan status Menunggu Keputusan apabila validasi berhasil. |
| Alur Utama | 1. Mahasiswa membuka menu pengajuan peminjaman. 2. Mahasiswa memilih peralatan yang akan dipinjam. 3. Mahasiswa mengisi jumlah dan rentang waktu peminjaman. 4. Sistem memeriksa kelengkapan data. 5. Sistem menjalankan LAB-UC04 untuk memeriksa ketersediaan. 6. Jika peralatan tersedia, sistem menyimpan pengajuan. 7. Sistem memberikan status Menunggu Keputusan. 8. Sistem menampilkan konfirmasi pengajuan. |
| Alur Alternatif | 1. Jika data belum lengkap, sistem meminta mahasiswa melengkapi data. 2. Jika peralatan tidak tersedia, sistem menampilkan informasi bahwa peralatan tidak tersedia dan pengajuan tidak disimpan sebagai pengajuan berhasil. |

**3. Use Case LAB-UC04 – Periksa Ketersediaan**

| Komponen | Deskripsi |
|---|---|
| Nama Use Case | Periksa Ketersediaan |
| ID | LAB-UC04 |
| Aktor | Tidak memiliki aktor langsung; dipanggil oleh LAB-UC03. |
| Tujuan | Memastikan peralatan tersedia sebelum pengajuan disimpan. |
| Kondisi Awal | Mahasiswa telah mengisi data pengajuan peminjaman. |
| Kondisi Akhir | Hasil pemeriksaan ketersediaan diperoleh oleh proses pengajuan. |
| Alur Utama | 1. Sistem menerima pilihan peralatan, jumlah, dan rentang waktu. 2. Sistem memeriksa data ketersediaan peralatan. 3. Sistem memberikan hasil pemeriksaan kepada proses pengajuan. |
| Alur Alternatif | Jika peralatan tidak tersedia, sistem memberikan hasil bahwa pengajuan tidak dapat dilanjutkan sebagai pengajuan berhasil. |

**4. Use Case LAB-UC05 – Cetak Bukti Pengajuan**

| Komponen | Deskripsi |
|---|---|
| Nama Use Case | Cetak Bukti Pengajuan |
| ID | LAB-UC05 |
| Aktor | Mahasiswa |
| Tujuan | Mendapatkan bukti pengajuan peminjaman. |
| Kondisi Awal | Pengajuan berhasil disimpan dan sistem menampilkan konfirmasi. |
| Kondisi Akhir | Bukti pengajuan dicetak jika mahasiswa memilih tindakan tersebut. |
| Alur Utama | 1. Sistem menampilkan konfirmasi pengajuan. 2. Mahasiswa memilih opsi cetak bukti. 3. Sistem menyiapkan bukti pengajuan. 4. Mahasiswa mencetak bukti pengajuan. |
| Alur Alternatif | Jika mahasiswa tidak memilih cetak, proses pengajuan tetap selesai tanpa mencetak bukti. |

**5. Use Case LAB-UC06 – Proses Keputusan Peminjaman**

| Komponen | Deskripsi |
|---|---|
| Nama Use Case | Proses Keputusan Peminjaman |
| ID | LAB-UC06 |
| Aktor | Petugas Laboratorium |
| Tujuan | Memberikan keputusan terhadap pengajuan peminjaman. |
| Kondisi Awal | Petugas telah login dan terdapat pengajuan peminjaman yang menunggu keputusan. |
| Kondisi Akhir | Pengajuan memiliki keputusan disetujui atau ditolak. |
| Alur Utama | 1. Petugas membuka daftar pengajuan. 2. Sistem menampilkan pengajuan yang tersedia. 3. Petugas memilih salah satu pengajuan. 4. Petugas memeriksa informasi pengajuan. 5. Petugas memberikan keputusan berupa persetujuan atau penolakan. 6. Sistem menyimpan keputusan. |
| Alur Alternatif | Petugas dapat memilih keputusan berbeda sesuai hasil pemeriksaan pengajuan. |

**6. Use Case LAB-UC02 – Kelola Data Peralatan**

| Komponen | Deskripsi |
|---|---|
| Nama Use Case | Kelola Data Peralatan |
| ID | LAB-UC02 |
| Aktor | Petugas Laboratorium |
| Tujuan | Mengelola informasi peralatan laboratorium. |
| Kondisi Awal | Petugas telah login ke sistem. |
| Kondisi Akhir | Data peralatan tersimpan atau diperbarui. |
| Alur Utama | 1. Petugas membuka menu data peralatan. 2. Sistem menampilkan data peralatan. 3. Petugas menambahkan atau memperbarui data peralatan. 4. Sistem menyimpan perubahan data. |

**7. Use Case LAB-UC07 – Lihat Laporan Peminjaman**

| Komponen | Deskripsi |
|---|---|
| Nama Use Case | Lihat Laporan Peminjaman |
| ID | LAB-UC07 |
| Aktor | Kepala Laboratorium |
| Tujuan | Melihat informasi dan laporan peminjaman peralatan. |
| Kondisi Awal | Kepala laboratorium telah login ke sistem. |
| Kondisi Akhir | Laporan peminjaman ditampilkan. |
| Alur Utama | 1. Kepala laboratorium membuka menu laporan peminjaman. 2. Sistem mengambil data peminjaman. 3. Sistem menampilkan laporan peminjaman. 4. Kepala laboratorium melihat laporan. |

### 3.2 Sistem Informasi Akademik (SIA)

#### A. Deskripsi Skenario

Mahasiswa mengajukan Kartu Rencana Studi (KRS) dengan memilih mata kuliah yang akan diambil. Setiap pengajuan akan menjalankan proses validasi untuk memeriksa kelengkapan data, prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, sistem menyimpan pengajuan dengan status Menunggu Persetujuan Dosen Wali.

Setelah pengajuan berhasil disimpan, mahasiswa dapat memilih untuk mengunduh bukti pengajuan. Dosen wali bertugas memproses KRS dengan memberikan persetujuan atau penolakan serta menyertakan catatan keputusan. Admin akademik bertugas mengelola jadwal kuliah.

#### B. Tabel Kebutuhan Fungsional

| ID | Kebutuhan Fungsional |
|---|---|
| SIA-R01 | Mahasiswa dapat melihat jadwal kuliah. |
| SIA-R02 | Admin akademik dapat mengelola jadwal kuliah. |
| SIA-R03 | Mahasiswa dapat mengajukan KRS. |
| SIA-R04 | Sistem memvalidasi KRS sebagai bagian dari proses pengajuan. |
| SIA-R05 | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan. |
| SIA-R06 | Dosen wali dapat memproses persetujuan atau penolakan KRS. |

#### C. Identifikasi Aktor

| Aktor | Tujuan terhadap Sistem |
|---|---|
| Mahasiswa | Melihat jadwal kuliah dan mengajukan KRS dengan memilih mata kuliah. |
| Admin Akademik | Mengelola jadwal kuliah. |
| Dosen Wali | Memproses persetujuan atau penolakan KRS dan memberikan catatan keputusan. |

#### D. Katalog Use Case

| ID Use Case | Nama Use Case | Peran dalam Model |
|---|---|---|
| SIA-UC01 | Melihat Jadwal Kuliah | Fungsi mahasiswa untuk melihat jadwal kuliah. |
| SIA-UC02 | Ajukan KRS | Fungsi utama pengajuan KRS oleh mahasiswa. |
| SIA-UC03 | Validasi KRS | Perilaku wajib yang disertakan dalam pengajuan KRS. |
| SIA-UC04 | Unduh Bukti Pengajuan KRS | Perilaku tambahan jika mahasiswa memilih mengunduh bukti. |
| SIA-UC05 | Proses Keputusan KRS | Fungsi dosen wali untuk menyetujui atau menolak KRS. |
| SIA-UC06 | Kelola Jadwal Kuliah | Fungsi admin akademik untuk mengelola jadwal kuliah. |

#### E. Relasi Antar Use Case

**1. Relasi Include**

SIA-UC02 `<<include>>` SIA-UC03

Alasan: Validasi KRS merupakan bagian wajib dari proses pengajuan KRS. Sistem harus memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal sebelum pengajuan berhasil disimpan.

**2. Relasi Extend**

SIA-UC04 `<<extend>>` SIA-UC02

Alasan: Pengunduhan bukti merupakan perilaku tambahan yang hanya dilakukan jika mahasiswa memilih mengunduh bukti setelah pengajuan berhasil disimpan. Pengajuan tetap berhasil meskipun mahasiswa tidak mengunduh bukti.

#### F. Batas Sistem dan Asumsi

1. Pengguna telah melakukan autentikasi sebelum menggunakan sistem.
2. Data mata kuliah, prasyarat, dan jadwal kuliah telah tersedia.
3. Validasi yang gagal menyebabkan pengajuan belum berhasil disimpan.
4. Pengunduhan bukti bukan merupakan syarat keberhasilan pengajuan KRS.
5. KRS yang tersimpan belum berarti telah disetujui oleh dosen wali.
6. Pembayaran, pengisian nilai, dan implementasi basis data berada di luar cakupan tugas.

#### G. Use Case Description

**1. Use Case SIA-UC01 – Melihat Jadwal Kuliah**

| Komponen | Deskripsi |
|---|---|
| Nama Use Case | Melihat Jadwal Kuliah |
| ID | SIA-UC01 |
| Aktor | Mahasiswa |
| Tujuan | Melihat informasi jadwal perkuliahan. |
| Kondisi Awal | Mahasiswa telah login ke sistem. |
| Kondisi Akhir | Informasi jadwal kuliah ditampilkan. |
| Alur Utama | 1. Mahasiswa membuka menu jadwal kuliah. 2. Sistem mengambil data jadwal. 3. Sistem menampilkan jadwal kuliah. 4. Mahasiswa melihat informasi jadwal. |

**2. Use Case SIA-UC02 – Ajukan KRS**

| Komponen | Deskripsi |
|---|---|
| Nama Use Case | Ajukan KRS |
| ID | SIA-UC02 |
| Aktor | Mahasiswa |
| Tujuan | Mengajukan mata kuliah yang akan diambil pada semester berjalan. |
| Kondisi Awal | Mahasiswa telah login dan data mata kuliah tersedia. |
| Kondisi Akhir | Pengajuan KRS tersimpan dengan status Menunggu Persetujuan Dosen Wali apabila validasi berhasil. |
| Alur Utama | 1. Mahasiswa membuka menu pengajuan KRS. 2. Sistem menampilkan daftar mata kuliah. 3. Mahasiswa memilih mata kuliah yang akan diambil. 4. Mahasiswa mengirimkan pengajuan KRS. 5. Sistem menjalankan SIA-UC03 untuk memvalidasi KRS. 6. Jika validasi berhasil, sistem menyimpan pengajuan. 7. Sistem memberikan status Menunggu Persetujuan Dosen Wali. 8. Sistem menampilkan konfirmasi pengajuan. |
| Alur Alternatif | Jika validasi gagal, sistem menampilkan informasi kesalahan dan pengajuan belum berhasil disimpan. Mahasiswa perlu memperbaiki pilihan atau data pengajuan. |

**3. Use Case SIA-UC03 – Validasi KRS**

| Komponen | Deskripsi |
|---|---|
| Nama Use Case | Validasi KRS |
| ID | SIA-UC03 |
| Aktor | Tidak memiliki aktor langsung; dipanggil oleh SIA-UC02. |
| Tujuan | Memastikan pengajuan KRS memenuhi ketentuan akademik. |
| Kondisi Awal | Mahasiswa telah memilih mata kuliah dan mengirimkan pengajuan KRS. |
| Kondisi Akhir | Hasil validasi diperoleh oleh proses pengajuan KRS. |
| Alur Utama | 1. Sistem menerima data mata kuliah yang dipilih. 2. Sistem memeriksa kelengkapan pengajuan. 3. Sistem memeriksa prasyarat mata kuliah. 4. Sistem memeriksa kemungkinan benturan jadwal. 5. Sistem memberikan hasil validasi. |
| Alur Alternatif | Jika terdapat data yang tidak lengkap, prasyarat tidak terpenuhi, atau jadwal bentrok, sistem menyatakan validasi gagal dan pengajuan belum berhasil disimpan. |

**4. Use Case SIA-UC04 – Unduh Bukti Pengajuan KRS**

| Komponen | Deskripsi |
|---|---|
| Nama Use Case | Unduh Bukti Pengajuan KRS |
| ID | SIA-UC04 |
| Aktor | Mahasiswa |
| Tujuan | Mendapatkan bukti pengajuan KRS. |
| Kondisi Awal | Pengajuan KRS berhasil disimpan dan sistem menampilkan konfirmasi. |
| Kondisi Akhir | Bukti pengajuan berhasil diunduh jika mahasiswa memilihnya. |
| Alur Utama | 1. Sistem menampilkan konfirmasi pengajuan KRS. 2. Mahasiswa memilih opsi unduh bukti. 3. Sistem menyiapkan dokumen bukti pengajuan. 4. Mahasiswa mengunduh bukti pengajuan. |
| Alur Alternatif | Jika mahasiswa tidak memilih unduh bukti, proses pengajuan tetap selesai tanpa mengunduh dokumen. |

**5. Use Case SIA-UC05 – Proses Keputusan KRS**

| Komponen | Deskripsi |
|---|---|
| Nama Use Case | Proses Keputusan KRS |
| ID | SIA-UC05 |
| Aktor | Dosen Wali |
| Tujuan | Memberikan keputusan terhadap pengajuan KRS mahasiswa. |
| Kondisi Awal | Dosen wali telah login dan terdapat pengajuan KRS yang menunggu persetujuan. |
| Kondisi Akhir | Pengajuan memiliki keputusan disetujui atau ditolak beserta catatan keputusan. |
| Alur Utama | 1. Dosen wali membuka daftar pengajuan KRS. 2. Sistem menampilkan pengajuan yang menunggu persetujuan. 3. Dosen wali memilih pengajuan mahasiswa. 4. Dosen wali memeriksa mata kuliah yang diajukan. 5. Dosen wali memberikan keputusan berupa persetujuan atau penolakan. 6. Dosen wali memberikan catatan keputusan. 7. Sistem menyimpan keputusan dan catatan tersebut. |
| Alur Alternatif | Dosen wali dapat memberikan keputusan penolakan apabila pengajuan tidak disetujui, kemudian memasukkan catatan keputusan. |

**6. Use Case SIA-UC06 – Kelola Jadwal Kuliah**

| Komponen | Deskripsi |
|---|---|
| Nama Use Case | Kelola Jadwal Kuliah |
| ID | SIA-UC06 |
| Aktor | Admin Akademik |
| Tujuan | Mengelola informasi jadwal perkuliahan. |
| Kondisi Awal | Admin akademik telah login ke sistem. |
| Kondisi Akhir | Data jadwal kuliah berhasil ditambahkan atau diperbarui. |
| Alur Utama | 1. Admin akademik membuka menu pengelolaan jadwal. 2. Sistem menampilkan data jadwal kuliah. 3. Admin akademik menambahkan atau memperbarui jadwal. 4. Sistem menyimpan perubahan data jadwal. |

### 3.3 Ringkasan Hasil Pemodelan

| Keterangan | Sistem Peminjaman Laboratorium | Sistem Informasi Akademik |
|---|---:|---:|
| Jumlah Aktor | 3 | 3 |
| Jumlah Kebutuhan Fungsional | 6 | 6 |
| Jumlah Use Case | 7 | 6 |
| Relasi Include | 1 | 1 |
| Relasi Extend | 1 | 1 |

Berdasarkan hasil pemodelan, kedua sistem memiliki relasi `include` untuk proses yang wajib dilakukan dan relasi `extend` untuk proses tambahan yang bersifat opsional.

## 4. Analisis

Berdasarkan hasil praktikum, Use Case Diagram membantu menggambarkan fungsi sistem serta hubungan antara aktor dengan layanan yang tersedia. Pada sistem peminjaman peralatan laboratorium, mahasiswa memiliki hak untuk melihat ketersediaan dan mengajukan peminjaman, petugas laboratorium bertugas mengelola peralatan serta memproses keputusan, sedangkan kepala laboratorium hanya memiliki fungsi untuk melihat laporan peminjaman. Relasi `include` digunakan pada proses pemeriksaan ketersediaan karena pemeriksaan tersebut wajib dilakukan sebelum pengajuan disimpan. Sementara itu, relasi `extend` digunakan pada proses pencetakan bukti karena mahasiswa dapat memilih untuk mencetak atau tidak.

Pada Sistem Informasi Akademik, mahasiswa dapat melihat jadwal kuliah dan mengajukan KRS, admin akademik bertugas mengelola jadwal kuliah, sedangkan dosen wali memproses persetujuan atau penolakan KRS. Validasi KRS menjadi bagian wajib dari pengajuan karena sistem harus memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Pengunduhan bukti pengajuan menjadi perilaku tambahan karena tidak menentukan keberhasilan pengajuan. Dari kedua skenario tersebut, dapat dipahami bahwa relasi `include` digunakan untuk proses wajib, sedangkan `extend` digunakan untuk proses tambahan berdasarkan kondisi tertentu. Use Case Description juga membantu menjelaskan langkah-langkah interaksi secara lebih terperinci, termasuk kondisi awal, kondisi akhir, alur utama, dan alur alternatif.

## 5. Kesimpulan

Berdasarkan praktikum pertemuan 3, dapat disimpulkan bahwa Use Case Diagram digunakan untuk menggambarkan kebutuhan fungsional sistem dan interaksi antara aktor dengan sistem. Melalui dua skenario yang diberikan, berhasil diidentifikasi aktor, kebutuhan fungsional, katalog Use Case, serta hubungan antar Use Case menggunakan relasi `include` dan `extend`.

Selain itu, Use Case Description memberikan penjelasan lebih rinci mengenai proses yang terjadi pada setiap Use Case, mulai dari kondisi awal hingga kondisi akhir. Dengan demikian, pemodelan ini dapat membantu memahami alur kerja sistem sebelum dilanjutkan ke tahap perancangan dan pengembangan.

## Daftar Pustaka

1. Institut Teknologi Garut. Jobsheet Praktikum Analisis dan Desain Berorientasi Objek Pertemuan 3.
2. Object Management Group (OMG). Unified Modeling Language (UML) Version 2.5.1.
3. diagrams.net. Documentation: Use Case Diagrams.