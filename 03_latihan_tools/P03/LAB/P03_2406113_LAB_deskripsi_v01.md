
| Elemen                    | LAB-UC03 - Ajukan Peminjaman                                         |
|---------------------------|----------------------------------------------------------------------|
| Tujuan                    | Menghasilkan pengajuan peminjaman yang tersimpan                     |
| Aktor Utama               | Mahasiswa                                                            |
| Sumber Kebutuhan          | LAB-R03 dan LAB-R04                                                  |
| Pemicu                    | Mahasiswa memilih fungsi pengajuan peminjaman                        |
| Prasyarat                 | Mahasiswa telah terautentikasi; data peralatan tersedia              |
| Pascakondisi Berhasil     | Pengajuan tersimpan dengan nomor dan status Menunggu Keputusan       |
| Pascakondisi Gagal        | Tidak ada pengajuan baru yang berhasil tersimpan                     |
| Include                   | LAB-UC04 — Periksa Ketersediaan                                      |
| Extension Point           | Bukti pengajuan tersedia, pada langkah 6                             |
| Extend                    | LAB-UC05 jika mahasiswa memilih cetak                                |

