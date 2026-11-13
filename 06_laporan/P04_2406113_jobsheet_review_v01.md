# LAPORAN PRAKTIKUM PERTEMUAN 4
## USE CASE DIAGRAM LANJUTAN: GENERALIZATION DAN COLLABORATION

### 1. Tujuan Praktikum

1. Memahami konsep generalization dan collaboration.
2. Mengidentifikasi aktor umum dan aktor khusus.
3. Menentukan relasi antar Use Case.
4. Mengembangkan diagram Use Case secara kumulatif dari pertemuan sebelumnya.

### 2. Dasar Teori

Generalization merupakan hubungan antara elemen umum dan elemen khusus yang mewarisi fungsi dari elemen umum. Collaboration menggambarkan kerja sama beberapa bagian untuk merealisasikan suatu Use Case. Keduanya digunakan dalam UML untuk memperjelas struktur dan perilaku sistem.

### 3. Hasil Praktikum

## 3.1 Sistem Peminjaman Peralatan Laboratorium

**A. Identifikasi Aktor**

| Aktor | Tujuan |
|---|---|
| Peminjam | Aktor umum untuk peminjaman peralatan. |
| Mahasiswa | Melihat ketersediaan, mengajukan peminjaman, dan mencetak bukti. |
| Dosen | Melihat ketersediaan dan mengajukan peminjaman. |
| Petugas Laboran | Mengelola peralatan, memproses keputusan, dan mencatat pengembalian. |
| Kepala Laboran | Melihat laporan peminjaman. |

**B. Katalog Use Case**

| ID | Nama Use Case |
|---|---|
| LAB-UC01 | Lihat Ketersediaan Peralatan |
| LAB-UC02 | Kelola Data Peralatan |
| LAB-UC03 | Ajukan Peminjaman |
| LAB-UC04 | Periksa Ketersediaan |
| LAB-UC05 | Cetak Bukti Pengajuan |
| LAB-UC06 | Proses Keputusan Peminjaman |
| LAB-UC07 | Lihat Laporan Peminjaman |
| LAB-UC08 | Tambah Data Peralatan |
| LAB-UC09 | Ubah Data Peralatan |
| LAB-UC10 | Hapus Data Peralatan |
| LAB-UC11 | Catat Pengembalian Peralatan |
| LAB-UC12 | Periksa Kondisi Peralatan |

**C. Relasi Use Case**

- Generalization aktor: Mahasiswa dan Dosen mewarisi fungsi Peminjam.
- Generalization Use Case: LAB-UC08, LAB-UC09, dan LAB-UC10 merupakan bentuk khusus LAB-UC02.
- Include: LAB-UC03 `<<include>>` LAB-UC04.
- Include: LAB-UC11 `<<include>>` LAB-UC12.
- Extend: LAB-UC05 `<<extend>>` LAB-UC03.

Perilaku khusus pengelolaan peralatan:
1. Tambah menghasilkan data peralatan baru.
2. Ubah menghasilkan data peralatan yang diperbarui.
3. Hapus menghapus data jika tidak sedang dipinjam dan tidak memiliki pengajuan aktif.

**D. Collaboration**

| ID | Nama Collaboration | Use Case |
|---|---|---|
| LAB-CO01 | Ajukan Peminjaman | LAB-UC03 |
| LAB-CO02 | Catat Pengembalian Peralatan | LAB-UC11 |

**E. Batasan Sistem**

1. Sistem hanya mencatat informasi, bukan perpindahan fisik peralatan.
2. Pengguna harus login sesuai hak akses.
3. Pengembalian hanya dapat dicatat untuk peminjaman berstatus Dipinjam.
4. Kondisi alat terdiri dari Baik, Rusak Ringan, dan Rusak Berat.
5. Keterlambatan dan denda belum dimodelkan.

Pertanyaan terbuka: Bagaimana aturan penanganan keterlambatan pengembalian dan apakah akan dikenakan denda?

## 3.2 Sistem Informasi Akademik (SIA)

**A. Identifikasi Aktor**

| Aktor | Tujuan |
|---|---|
| Civitas Akademika | Aktor umum untuk melihat kalender akademik. |
| Mahasiswa | Melihat jadwal, mengajukan KRS, dan melihat KHS. |
| Dosen | Melihat kalender akademik dan menginput nilai. |
| Admin Akademik | Mengelola jadwal dan data mahasiswa. |
| Dosen Wali | Memproses persetujuan atau penolakan KRS. |

**B. Katalog Use Case**

| ID | Nama Use Case |
|---|---|
| SIA-UC01 | Melihat Jadwal Kuliah |
| SIA-UC02 | Ajukan KRS |
| SIA-UC03 | Validasi KRS |
| SIA-UC04 | Unduh Bukti Pengajuan KRS |
| SIA-UC05 | Proses Keputusan KRS |
| SIA-UC06 | Kelola Jadwal Kuliah |
| SIA-UC07 | Lihat Kalender Akademik |
| SIA-UC08 | Input Nilai Mata Kuliah |
| SIA-UC09 | Lihat KHS |
| SIA-UC10 | Kelola Data Mahasiswa |
| SIA-UC11 | Tambah Data Mahasiswa |
| SIA-UC12 | Ubah Data Mahasiswa |
| SIA-UC13 | Hapus Data Mahasiswa |

**C. Relasi Use Case**

- Generalization aktor: Mahasiswa dan Dosen mewarisi fungsi Civitas Akademika.
- Generalization Use Case: SIA-UC11, SIA-UC12, dan SIA-UC13 merupakan bentuk khusus SIA-UC10.
- Include: SIA-UC02 `<<include>>` SIA-UC03.
- Extend: SIA-UC04 `<<extend>>` SIA-UC02.

Perilaku khusus pengelolaan mahasiswa:
1. Tambah menghasilkan data mahasiswa baru.
2. Ubah menghasilkan data mahasiswa yang diperbarui.
3. Hapus menghapus data mahasiswa jika tidak memiliki data akademik aktif.

**D. Collaboration**

| ID | Nama Collaboration | Use Case |
|---|---|---|
| SIA-CO01 | Input Nilai Mata Kuliah | SIA-UC08 |
| SIA-CO02 | Lihat KHS | SIA-UC09 |

**E. Batasan Sistem**

1. Pengguna telah login sesuai hak akses.
2. Kalender akademik merupakan agenda resmi institusi, bukan jadwal kuliah.
3. Nilai hanya dapat diinput oleh dosen pengampu.
4. Nilai baru tampil pada KHS setelah dipublikasikan.
5. Data mahasiswa yang masih memiliki data akademik aktif tidak dapat dihapus.
6. Pembayaran dan basis data tidak termasuk ruang lingkup tugas.

## 3.3 Hasil Uji Konsistensi

| Situasi | Hasil |
|---|---|
| A | Mahasiswa tetap dapat melihat kalender akademik melalui pewarisan fungsi dari Civitas Akademika. |
| B | Dosen yang bukan pengampu ditolak saat menginput nilai dan perubahan tidak disimpan. |
| C | Admin tidak dapat menghapus mahasiswa yang masih memiliki data akademik aktif. |

## 4. Analisis

Generalization membantu menyederhanakan diagram dengan mengelompokkan aktor dan Use Case yang memiliki fungsi umum. Collaboration menunjukkan realisasi dari Use Case utama. Pada kedua sistem, seluruh fungsi pertemuan sebelumnya tetap dipertahankan dan ditambahkan fungsi baru sesuai kebutuhan. Hasil uji konsistensi juga memastikan bahwa hak akses dan aturan sistem sudah sesuai dengan skenario.

## 5. Kesimpulan

Praktikum pertemuan 4 memberikan pemahaman mengenai penerapan generalization dan collaboration dalam Use Case Diagram. Generalization digunakan untuk menggambarkan pewarisan fungsi, sedangkan collaboration menunjukkan realisasi suatu Use Case. Diagram yang dihasilkan merupakan pengembangan dari pertemuan sebelumnya sehingga seluruh kebutuhan tetap terwakili.

### Daftar Pustaka

1. Jobsheet Praktikum Analisis dan Desain Berorientasi Objek Pertemuan 4.
2. Object Management Group (OMG), UML Version 2.5.1.