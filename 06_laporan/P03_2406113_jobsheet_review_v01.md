<!-- Pemeriksaan Konsistensi Diagram dan Deskripsi Use Case -->

| No. | Situasi                                                        | Hasil     | Penjelasan                                                                                                      |
|-----|----------------------------------------------------------------|-----------|-----------------------------------------------------------------------------------------------------------------|
| 1   | Validasi berhasil dan mahasiswa tidak mengunduh bukti.         | Konsisten | Pengajuan KRS berhasil diselesaikan tanpa mengunduh bukti KRS.                                                  |
| 2   | Validasi gagal.                                                | Konsisten | Pengajuan KRS tidak dapat dilanjutkan karena prasyarat tidak terpenuhi.                                         |
| 3   | Validasi berhasil dan mahasiswa memilih mengunduh bukti.       | Konsisten | Pengajuan KRS berhasil dan mahasiswa dapat mengunduh bukti KRS melalui relasi <<extend>>.                     |

<!-- Kesimpulan -->

Diagram dan deskripsi use case konsisten untuk ketiga situasi tersebut. Relasi «include»n menunjukkan bahwa validasi prasyarat merupakan bagian dari proses pengajuan KRS, sedangkan relasi «extend» menunjukkan bahwa pengunduhan bukti KRS merupakan proses tambahan yang bersifat opsional.