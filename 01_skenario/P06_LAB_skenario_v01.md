Tabel berikut adalah jembatan resmi antara Jobsheet Pertemuan 5 dan
pertemuan ini. Setiap barisnya dipakai pada contoh penerapan dan pada langkah
praktik.

| Unsur pada Tabel Skenario Pertemuan 5        | Menjadi pada Activity Diagram                                                 |
|----------------------------------------------|-------------------------------------------------------------------------------|
| Skenario Normal                              | Alur utama: rangkaian action dari initial node sampai activity final node.    |
| Skenario Alternative                         | Cabang decision dengan guard yang menyatakan syarat cabang tersebut.          |
| Langkah include (selalu terjadi)             | Action wajib pada alur utama, ditempatkan pada urutan langkahnya di dalam skenari misalnya Periksa Ketersediaan dari LAB-UC04.                                                                           |
| Langkah extend (bersyarat)                   | Cabang decision tersendiri dengan condition yang sama dengan condition extend pada diagram Pertemuan 4, misalnya cabang [ya, memilih cetak] menuju Cetak Bukti Pengajuan dari LAB-UC05.                      |
| Kolom Kegiatan (aktor)                       | Action pada swimlane aktor tersebut.                                          |
| Kolom Respon Sistem                          | Action pada swimlane Sistem.                                                   |
| Skenario Akhir                               | Activity final node; kondisi selesai pada skenario menjadi keadaan akhir alur. |
| Dua pemeriksaan yang tidak saling bergantung | Fork dan join: kedua pemeriksaan digambar paralel dan disatukan kembali sebelum keputusan akhir.                                                                                                                  |