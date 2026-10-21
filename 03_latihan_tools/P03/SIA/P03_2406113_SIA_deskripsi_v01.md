# Spesifikasi Use Case Sistem Informasi Akademik
<<<<<<< HEAD
=======

>>>>>>> 6d957bc84d58e6e52bffaebb526fef3c05b05eb5
## SIA-UC02 — Ajukan KRS

| Elemen                | Keterangan                                                                       |
|-----------------------|----------------------------------------------------------------------------------|
| Tujuan                | Menyimpan pengajuan KRS mahasiswa.                                               |
| Aktor Utama           | Mahasiswa                                                                        |
| Sumber Kebutuhan      | SIA-R03                                                                          |
| Pemicu                | Mahasiswa memilih fungsi pengajuan KRS.                                          |
| Prasyarat             | Mahasiswa telah terautentikasi; data mata kuliah, prasyarat, dan jadwal tersedia.|
| Pascakondisi Berhasil | Pengajuan tersimpan dengan status Menunggu Persetujuan Dosen Wali.               |
| Pascakondisi Gagal    | Pengajuan baru tidak berhasil disimpan.                                          |
| Include               | SIA-UC03 — Validasi KRS                                                          |
| Extension Point       | Konfirmasi keberhasilan penyimpanan pengajuan KRS.                               |
| Extend                | Tidak ada                                                                        |

---

## SIA-UC03 — Validasi KRS

| Elemen | Keterangan |
|---|---|
| Tujuan | Memastikan pengajuan KRS memenuhi seluruh aturan validasi. |
| Aktor Utama | Tidak ada aktor langsung; dipanggil oleh SIA-UC02. |
| Sumber Kebutuhan | SIA-R04 |
| Pemicu | SIA-UC02 menjalankan validasi setelah pengajuan dikirim. |
| Prasyarat | Mahasiswa telah memilih mata kuliah dan mengirim pengajuan KRS. |
| Pascakondisi Berhasil | Seluruh pemeriksaan validasi terpenuhi. |
| Pascakondisi Gagal | Satu atau lebih pemeriksaan validasi tidak terpenuhi. |
| Include | Tidak ada |
| Extension Point | Tidak ada |
| Extend | Tidak ada |

---

## SIA-UC04 — Unduh Bukti Pengajuan KRS

| Elemen | Keterangan |
|---|---|
| Tujuan | Menyediakan bukti pengajuan KRS yang berhasil disimpan. |
| Aktor Utama | Mahasiswa |
| Sumber Kebutuhan | SIA-R05 |
| Pemicu | Mahasiswa memilih opsi unduh bukti setelah pengajuan berhasil disimpan. |
| Prasyarat | Pengajuan KRS telah berhasil disimpan. |
| Pascakondisi Berhasil | Bukti pengajuan KRS berhasil diunduh. |
| Pascakondisi Gagal | Pengunduhan gagal, tetapi pengajuan tetap tersimpan. |
| Include | Tidak ada |
| Extension Point | Tidak ada |
| Extend | SIA-UC02 — Ajukan KRS |

---

## SIA-UC05 — Proses Keputusan KRS

| Elemen | Keterangan |
|---|---|
| Tujuan | Memproses dan mencatat keputusan persetujuan atau penolakan KRS beserta catatannya. |
| Aktor Utama | Dosen Wali |
| Sumber Kebutuhan | SIA-R06 |
| Pemicu | Dosen wali memilih pengajuan KRS untuk diproses. |
| Prasyarat | Dosen wali telah terautentikasi dan pengajuan KRS tersedia untuk diproses. |
| Pascakondisi Berhasil | Keputusan persetujuan atau penolakan berhasil dicatat beserta catatannya. |
| Pascakondisi Gagal | Keputusan baru tidak berhasil dicatat. |
| Include | Tidak ada |
| Extension Point | Tidak ada |
| Extend | Tidak ada |