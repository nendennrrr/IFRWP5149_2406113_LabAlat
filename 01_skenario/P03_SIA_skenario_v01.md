<!-- Deskripsi Skenario -->
Skenario tugas:
Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap pengajuan menjalankan validasi KRS yang memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, sistem menyimpan pengajuan berstatus menunggu persetujuan dosen wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS dan memberikan catatan keputusan.

<!-- Tabel Kebutuhan -->
|  ID   |Kebutuhan|                             tugas                              |
|-------|---------|----------------------------------------------------------------|
|SIA-R01|Mahasiswa|                  dapat melihat jadwal kuliah                   |
|SIA-R02|  Admin  |             akademik dapat mengelola jadwal kuliah             |
|SIA-R03|Mahasiswa|                      dapat mengajukan KRS                      |
|SIA-R04| Sistem  |            memvalidasi KRS sebagai bagian pengajuan            |
|SIA-R05|Mahasiswa|dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan |
|SIA-R06|  Dosen  |      wali dapat memproses persetujuan atau penolakan KRS       |

<!-- Batasan Sistem -->
Batas dan asumsi:
• Pengguna telah terautentikasi.
• Data mata kuliah, prasyarat, dan jadwal tersedia.
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
• KRS tersimpan belum berarti disetujui.
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas.

<!-- Tabel Identifikasi Aktor -->
|  Aktor           |   Tujuan terhadap sistem                                            |
|------------------|---------------------------------------------------------------------|
|Mahasiswa         |Mahasiswa mengajukan KRS dengan memilih mata kuliah                  |
|Admin Akademik    |Admin akademik dapat mengelola jadwal kuliah                         |
|Dosen Wali        |Dosen wali dapat memproses persetujuan atau penolakan KRS            |

<!-- Tabel Katalog Use Case -->
| ID Use Case | Nama Use Case             | Peran dalam Model                                      |
|:------------|:--------------------------|:-------------------------------------------------------|
| SIA-UC01    | Melihat Jadwal Kuliah     | Fungsi untuk melihat jadwal kuliah.                    |
| SIA-UC02    | Ajukan KRS                | Fungsi utama pengajuan KRS oleh mahasiswa.             |
| SIA-UC03    | Validasi KRS              | Perilaku wajib yang disertakan dalam pengajuan KRS.    |
| SIA-UC04    | Unduh Bukti Pengajuan KRS | Perilaku tambahan jika mahasiswa memilih mengunduh bukti. |
| SIA-UC05    | Proses Keputusan KRS      | Fungsi dosen wali untuk menyetujui atau menolak KRS.   |
| SIA-UC06    | Kelola Jadwal Kuliah      | Fungsi admin akademik untuk mengelola jadwal kuliah.   |

<!-- Relasi Include -->
SIA-UC02 «include» SIA-UC03
Alasan: validasi KRS menjadi bagian wajib dalam proses pengajuan KRS.

<!-- Relasi Extends -->
SIA-UC04 «extend» SIA-UC02
Alasan: pengunduhan bukti merupakan perilaku tambahan yang dilakukan jika mahasiswa memilih mengunduh bukti setelah pengajuan berhasil disimpan.


