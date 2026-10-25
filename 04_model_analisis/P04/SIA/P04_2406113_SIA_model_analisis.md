# Katalog Aktor dan Use Case — Diagram Kumulatif SIA

## Aktor
| Aktor | Jenis | Peran |
|---|---|---|
| Civitas Akademika | Aktor umum | Melihat kalender akademik; fungsi bersama diwariskan oleh aktor khususnya. |
| Mahasiswa | Aktor khusus dari Civitas Akademika | Melihat jadwal kuliah, mengajukan KRS, mengunduh bukti pengajuan KRS, melihat KHS. |
| Dosen | Aktor khusus dari Civitas Akademika | Mengelola jadwal kuliah sesuai kewenangan, menginput nilai mata kuliah yang diampu, melihat kalender akademik melalui pewarisan. |
| Admin Akademik | Aktor | Mengelola data mahasiswa. |
| Dosen Wali | Aktor | Memvalidasi KRS dan memproses keputusan KRS sesuai model Pertemuan 3. |

> Catatan konsistensi: asosiasi fungsi bersama untuk kalender akademik digambar satu kali dari Civitas Akademika. Mahasiswa dan Dosen mewarisi perilaku tersebut melalui generalization aktor. Asosiasi fungsi lama KRS/jadwal dipertahankan dari model Pertemuan 3; sesuaikan detail aktor dan relasi include/extend dengan berkas asli P03 bila model lokal sebelumnya memiliki rincian yang berbeda.

## Katalog gabungan use case
| ID | Nama use case | Aktor terkait | Sumber kebutuhan | Status |
|---|---|---|---|---|
| SIA-UC01 | Lihat Jadwal Kuliah | Mahasiswa | Pertemuan 2 (SIA-R01) | Tetap |
| SIA-UC02 | Kelola Jadwal Kuliah | Dosen | Pertemuan 2 (SIA-R02) | Tetap |
| SIA-UC03 | Ajukan KRS | Mahasiswa | Pertemuan 3 (SIA-R03) | Tetap |
| SIA-UC04 | Validasi KRS | Dosen Wali | Pertemuan 3 (SIA-R04) | Tetap |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Mahasiswa | Pertemuan 3 (SIA-R05) | Tetap |
| SIA-UC06 | Proses Keputusan KRS | Dosen Wali | Pertemuan 3 (SIA-R06) | Tetap |
| SIA-UC07 | Lihat Kalender Akademik | Civitas Akademika | SIA-R07 | Baru |
| SIA-UC08 | Input Nilai Mata Kuliah | Dosen | SIA-R08 | Baru |
| SIA-UC09 | Lihat KHS | Mahasiswa | SIA-R09 | Baru |
| SIA-UC10 | Kelola Data Mahasiswa | Admin Akademik | SIA-R10 | Baru |
| SIA-UC11 | Tambah Data Mahasiswa | Admin Akademik | SIA-R11 | Baru |
| SIA-UC12 | Ubah Data Mahasiswa | Admin Akademik | SIA-R11 | Baru |
| SIA-UC13 | Hapus Data Mahasiswa | Admin Akademik | SIA-R11 | Baru |

## Generalization aktor
- `Mahasiswa —|> Civitas Akademika` dan `Dosen —|> Civitas Akademika`.
- Mahasiswa dan Dosen mewarisi use case `Lihat Kalender Akademik` dari Civitas Akademika.
- Asosiasi ke `Lihat Kalender Akademik` cukup dibuat satu kali dari Civitas Akademika agar tidak menduplikasi relasi yang sama.

## Generalization use case
- `Tambah Data Mahasiswa —|> Kelola Data Mahasiswa`
- `Ubah Data Mahasiswa —|> Kelola Data Mahasiswa`
- `Hapus Data Mahasiswa —|> Kelola Data Mahasiswa`
- Tambah: membuat dan menyimpan satu rekaman mahasiswa baru setelah data wajib lolos validasi.
- Ubah: memperbarui atribut data mahasiswa yang sudah ada setelah rekaman ditemukan dan perubahan lolos validasi.
- Hapus: menghapus rekaman mahasiswa hanya jika mahasiswa tidak memiliki data akademik aktif; jika masih ada, operasi ditolak.

## Collaboration
| ID | Nama collaboration | Use case yang direalisasikan |
|---|---|---|
| SIA-CO01 | Input Nilai Mata Kuliah | SIA-UC08 — Input Nilai Mata Kuliah |
| SIA-CO02 | Lihat KHS | SIA-UC09 — Lihat KHS |

## Relasi lama yang dipertahankan
Pertahankan relasi `<<include>>` dan `<<extend>>` di antara SIA-UC03 sampai SIA-UC06 persis seperti pada diagram Pertemuan 3 yang menjadi sumber. Jangan menebak atau mengubah arah relasi lama ketika menggabungkan diagram kumulatif. Jika diagram P03 mengikuti model yang umum dipakai dalam praktikum, verifikasi arah panah dan labelnya pada berkas asli sebelum finalisasi.
