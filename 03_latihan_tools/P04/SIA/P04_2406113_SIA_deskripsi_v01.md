# Deskripsi Use Case — Pertemuan 4

## SIA-UC08 — Input Nilai Mata Kuliah
| Elemen | Deskripsi |
|---|---|
| ID | SIA-UC08 |
| Nama | Input Nilai Mata Kuliah |
| Tujuan | Dosen memasukkan nilai mahasiswa untuk mata kuliah yang diampunya setelah masa perkuliahan berakhir. |
| Aktor utama | Dosen |
| Pemicu | Dosen memilih fungsi input nilai untuk mata kuliah yang diampunya. |
| Prasyarat | Pengguna telah terautentikasi; dosen memiliki hak akses; masa perkuliahan mata kuliah telah berakhir; dan dosen adalah pengampu mata kuliah yang dipilih. |
| Pascakondisi berhasil | Nilai yang valid tersimpan sebagai nilai yang belum dipublikasikan, kecuali ketentuan publikasi resmi telah dilakukan melalui proses yang berwenang. Nilai belum ditampilkan di KHS sebelum dipublikasikan. |
| Pascakondisi gagal | Nilai tidak disimpan atau perubahan dibatalkan; data nilai sebelumnya tetap utuh; sistem menampilkan alasan kegagalan. |
| Collaboration | SIA-CO01 — Input Nilai Mata Kuliah |

### Alur utama
1. Dosen membuka menu Input Nilai Mata Kuliah.
2. Sistem menampilkan daftar mata kuliah yang diampu dosen tersebut.
3. Dosen memilih mata kuliah dan kelas/daftar mahasiswa yang akan dinilai.
4. Sistem memeriksa bahwa dosen merupakan pengampu mata kuliah terpilih.
5. Sistem menampilkan daftar mahasiswa dan kolom nilai.
6. Dosen memasukkan nilai untuk mahasiswa yang sesuai.
7. Sistem memvalidasi kelengkapan dan rentang nilai.
8. Sistem menyimpan nilai yang valid dengan status belum dipublikasikan.
9. Sistem menampilkan konfirmasi bahwa nilai berhasil disimpan.

### Alur alternatif dan pengecualian
- **A1 — Dosen bukan pengampu:** Pada langkah 4, jika dosen bukan pengampu mata kuliah, sistem menolak akses, tidak menyimpan nilai, dan menampilkan pesan bahwa hanya dosen pengampu yang boleh menginput nilai.
- **A2 — Nilai di luar rentang sah:** Pada langkah 7, jika satu atau lebih nilai berada di luar rentang yang ditetapkan institusi (misalnya skala 0–100 apabila itulah skala resmi), sistem menolak nilai yang tidak sah, menandai kolom terkait, meminta koreksi, dan tidak menyimpan nilai tidak sah. Untuk penyimpanan satu transaksi, seluruh transaksi dibatalkan agar tidak terjadi penyimpanan parsial.
- **A3 — Data belum lengkap:** Sistem menunjukkan data yang belum diisi dan meminta dosen melengkapinya sebelum penyimpanan.
- **A4 — Gangguan penyimpanan:** Sistem menampilkan kegagalan penyimpanan; nilai tidak dinyatakan berhasil tersimpan dan data sebelumnya tetap utuh.

## SIA-UC09 — Lihat KHS (ringkas)
| Elemen | Deskripsi |
|---|---|
| ID | SIA-UC09 |
| Nama | Lihat KHS |
| Tujuan | Mahasiswa melihat Kartu Hasil Studi untuk semester yang dipilih. |
| Aktor utama | Mahasiswa |
| Prasyarat | Mahasiswa telah terautentikasi dan memiliki hak akses ke data akademiknya sendiri. |
| Alur ringkas | Mahasiswa memilih semester; sistem mengambil hasil studi mahasiswa untuk semester tersebut; sistem hanya menampilkan nilai yang sudah dipublikasikan secara resmi. |
| Alur alternatif | Jika belum ada nilai yang dipublikasikan untuk semester tersebut, sistem menampilkan pemberitahuan bahwa KHS belum tersedia atau belum lengkap. |
| Pascakondisi | KHS ditampilkan dengan hanya memuat nilai yang sudah dipublikasikan; nilai yang masih berstatus belum dipublikasikan tidak ditampilkan. |
| Collaboration | SIA-CO02 — Lihat KHS |
