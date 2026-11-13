# LAPORAN PRAKTIKUM PERTEMUAN 5
## SKENARIO USE CASE: DARI DIAGRAM KE LANGKAH KEGIATAN

### 1. Tujuan Praktikum
1. Memahami hubungan antara diagram use case dan skenario use case.
2. Menelaah kesesuaian langkah kegiatan pada skenario dengan diagram kumulatif Pertemuan 4.
3. Memahami alur utama dan alur alternatif dalam suatu proses sistem.

### 2. Dasar Teori
Skenario use case merupakan penjelasan mengenai langkah-langkah interaksi antara aktor dan sistem untuk mencapai tujuan tertentu. Skenario ini menggambarkan proses secara lebih rinci dibandingkan diagram use case.

Diagram use case menunjukkan aktor, fungsi sistem, serta hubungan antarfungsi. Sementara itu, skenario use case menjelaskan urutan kegiatan yang terjadi ketika suatu fungsi dijalankan. Oleh karena itu, skenario harus sesuai dengan diagram dan kebutuhan sistem yang telah ditentukan.

### 3. Hasil dan Pembahasan

#### 3.1 Sistem Peminjaman dan Pengembalian Peralatan Laboratorium Kampus

Studi kasus ini menggunakan diagram kumulatif Pertemuan 4 sebagai acuan, yaitu kebutuhan LAB-R01 sampai LAB-R11 dan 17 hubungan pada diagram. Pada pertemuan ini tidak terdapat penambahan kebutuhan maupun use case baru.

Hal-hal yang perlu diperhatikan dalam penelaahan skenario adalah:

1. Mahasiswa dan dosen berperan sebagai Peminjam yang dapat melihat ketersediaan peralatan dan mengajukan peminjaman.
2. Petugas Laboratorium bertugas mengelola data peralatan, meliputi tambah, ubah, dan hapus data.
3. Petugas mencatat pengembalian peralatan yang memiliki status Dipinjam.
4. Sistem memeriksa dan mencatat kondisi peralatan saat pengembalian, yaitu Baik, Rusak Ringan, atau Rusak Berat.
5. Pengajuan peminjaman harus melalui pemeriksaan ketersediaan peralatan.
6. Pencetakan bukti peminjaman menjadi proses tambahan sesuai hubungan extend pada diagram.
7. Pencatatan pengembalian mencakup pemeriksaan kondisi peralatan sesuai hubungan include.
8. Penghapusan data peralatan hanya dapat dilakukan apabila peralatan tidak sedang dipinjam dan tidak memiliki pengajuan aktif.

Sistem juga memiliki batasan, yaitu perpindahan fisik peralatan tidak dimodelkan, pengguna harus sudah melakukan autentikasi, dan pengembalian hanya dapat dilakukan untuk peminjaman berstatus Dipinjam. Aturan keterlambatan dan denda tidak dibahas karena berada di luar ruang lingkup studi kasus.

#### 3.2 Sistem Informasi Akademik

Studi kasus Sistem Informasi Akademik menggunakan diagram kumulatif Pertemuan 4 dengan kebutuhan SIA-R01 sampai SIA-R12. Tidak terdapat kebutuhan maupun use case baru pada pertemuan ini.

Hal-hal yang perlu diperhatikan dalam penelaahan skenario adalah:

1. Mahasiswa dan dosen merupakan bagian dari Civitas Akademika sehingga keduanya dapat melihat kalender akademik.
2. Dosen hanya dapat menginput nilai mata kuliah yang diampunya.
3. Mahasiswa dapat melihat Kartu Hasil Studi (KHS) apabila nilai pada semester tersebut sudah dipublikasikan.
4. Admin Akademik bertugas mengelola data mahasiswa, meliputi tambah, ubah, dan hapus data.
5. Use case Input Nilai Mata Kuliah dan Lihat KHS direalisasikan melalui collaboration yang bersesuaian.
6. Penghapusan data mahasiswa hanya dapat dilakukan apabila tidak terdapat data akademik aktif yang menghalangi penghapusan.

Kalender yang dimaksud merupakan kalender akademik resmi institusi, bukan jadwal perkuliahan. Nilai yang belum dipublikasikan tidak dapat ditampilkan pada KHS. Selain itu, dosen yang bukan pengampu mata kuliah tidak memiliki hak untuk menginput nilai mata kuliah tersebut.

#### 3.3 Penelaahan Skenario Use Case

Penelaahan terhadap kedua belas tabel skenario dilakukan dengan memperhatikan beberapa aspek berikut:

1. Aktor yang menjalankan kegiatan harus sesuai dengan hak akses pada diagram.
2. Nama dan tujuan use case harus sesuai dengan diagram kumulatif Pertemuan 4.
3. Urutan langkah kegiatan harus menggambarkan proses sistem dengan benar.
4. Alur alternatif harus sesuai dengan kondisi dan aturan sistem.
5. Hubungan include, extend, dan generalization harus diterapkan sesuai fungsinya.
6. Collaboration harus sesuai dengan use case yang direalisasikannya.
7. Skenario tidak boleh menambahkan kebutuhan atau fungsi baru di luar ketentuan studi kasus.

### 4. Analisis
Berdasarkan studi kasus, skenario use case berfungsi untuk menjelaskan proses yang terdapat pada diagram secara lebih terperinci. Pada sistem peminjaman peralatan laboratorium, skenario harus menggambarkan proses pengajuan, pengelolaan peralatan, dan pengembalian beserta pemeriksaan kondisinya.

Pada Sistem Informasi Akademik, skenario harus memperhatikan hak akses setiap aktor, seperti dosen yang hanya dapat menginput nilai mata kuliah yang diampunya dan mahasiswa yang hanya dapat melihat KHS setelah nilai dipublikasikan. Dengan demikian, seluruh langkah kegiatan harus tetap sesuai dengan diagram kumulatif Pertemuan 4 dan tidak menambahkan fungsi baru.

### 5. Kesimpulan
Praktikum Pertemuan 5 membahas penelaahan skenario use case berdasarkan diagram kumulatif Pertemuan 4. Penelaahan dilakukan pada Sistem Peminjaman dan Pengembalian Peralatan Laboratorium serta Sistem Informasi Akademik. Melalui kegiatan ini, dapat dipahami bahwa skenario use case harus memiliki kesesuaian dengan aktor, fungsi sistem, hubungan antarfungsi, hak akses, dan aturan proses yang telah ditentukan.

### 6. Referensi
1. Jobsheet Praktikum Analisis dan Perancangan Sistem, Pertemuan 4: Use Case Diagram Lanjutan: Generalization dan Collaboration.
2. Jobsheet Praktikum Analisis dan Perancangan Sistem, Pertemuan 5: Skenario Use Case: Dari Diagram ke Langkah Kegiatan.