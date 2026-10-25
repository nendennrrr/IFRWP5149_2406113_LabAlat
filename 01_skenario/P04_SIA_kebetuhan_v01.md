# Tugas Praktik Pertemuan 4 — Sistem Informasi Akademik: Layanan Hasil Studi

## Skenario
Mahasiswa dan Dosen merupakan Civitas Akademika yang dapat melihat kalender akademik resmi institusi. Dosen menginput nilai mata kuliah yang diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin Akademik mengelola data mahasiswa melalui fungsi tambah, ubah, dan hapus. Collaboration merealisasikan use case Input Nilai Mata Kuliah dan Lihat KHS.

## Kebutuhan
| ID      | Kebutuhan                                                                        |
|---------|----------------------------------------------------------------------------------|
| SIA-R07 | Mahasiswa dan Dosen, sebagai Civitas Akademika, dapat melihat kalender akademik. |
| SIA-R08 | Dosen dapat menginput nilai mata kuliah yang diampunya.                          |
| SIA-R09 | Mahasiswa dapat melihat KHS untuk semester yang nilainya sudah dipublikasikan.   |
| SIA-R10 | Admin Akademik dapat mengelola data mahasiswa.                                   |
| SIA-R11 | Pengelolaan data mahasiswa terdiri dari tiga bentuk khusus: tambah, ubah, dan hapus data mahasiswa.                                                                              |
| SIA-R12 | Model menunjukkan collaboration yang merealisasikan Input Nilai Mata Kuliah dan Lihat KHS.                                                                                         |

## Batas dan asumsi
- Kode kebutuhan dimulai dari SIA-R07 agar kebutuhan Pertemuan 2 (SIA-R01–SIA-R02) dan Pertemuan 3 (SIA-R03–SIA-R06) tetap memiliki identitas berbeda.
- Pengguna telah terautentikasi dan memiliki hak akses sesuai peran.
- Kalender akademik adalah agenda resmi institusi (awal semester, batas KRS, masa ujian, dan sejenisnya), bukan jadwal kuliah.
- Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut.
- Nilai yang baru diinput belum tampil pada KHS sampai dipublikasikan secara resmi.
- Hapus Data Mahasiswa hanya diizinkan jika mahasiswa tidak memiliki data akademik aktif.
- Pengajuan KRS tetap ditampilkan sebagai bagian diagram kumulatif dari Pertemuan 3.
- Pembayaran dan perancangan basis data berada di luar ruang lingkup tugas.

## Hasil uji konsistensi, review, dan revisi
### Situasi A
Mahasiswa dapat melihat kalender akademik walaupun tidak ada garis asosiasi langsung dari aktor Mahasiswa ke use case Lihat Kalender Akademik. Hal ini benar karena Mahasiswa merupakan aktor khusus dari Civitas Akademika dan mewarisi asosiasi aktor umum tersebut. Asosiasi bersama cukup digambar satu kali dari Civitas Akademika.

### Situasi B
Jika dosen yang bukan pengampu mencoba menginput nilai, sistem menolak operasi dan tidak menyimpan perubahan. Prasyarat use case tidak terpenuhi karena dosen tersebut bukan pengampu mata kuliah yang dipilih. Sistem menampilkan pesan bahwa hanya dosen pengampu yang berhak menginput nilai.

### Situasi C
Jika Admin Akademik mencoba menghapus data mahasiswa yang masih memiliki data akademik aktif, sistem menolak penghapusan, mempertahankan data mahasiswa, dan menampilkan alasan penolakan. Penghapusan hanya boleh dilakukan jika tidak ada data akademik aktif.
