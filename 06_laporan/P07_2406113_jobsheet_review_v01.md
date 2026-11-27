# LAPORAN PRAKTIKUM PERTEMUAN 7

## Sequence Diagram: Interaksi Objek Berdasarkan Skenario dan Kandidat Class

## 1. Tujuan

Tujuan dari praktikum ini adalah:

1. Menentukan aktor, objek, dan *lifeline* pada *sequence diagram* dari baris Aktor tabel skenario serta kandidat *class* Pertemuan 7 dengan penulisan nama objek sesuai nama *class* (misalnya `:Peralatan`, `:Peminjaman`, dan `:Pengembalian`).
2. Menyusun urutan pesan dari atas ke bawah mengikuti urutan langkah pada tabel skenario, membedakan pesan kegiatan aktor dan pesan respon sistem maupun pesan balasan.
3. Menggambarkan relasi *include* sebagai fragmen `ref`, cabang *Skenario Alternative* sebagai fragmen `alt` dengan dua *operand* ber-*guard*, serta relasi *extend* sebagai fragmen `opt` yang memuat *condition* dan *extension point*.
4. Menggambarkan *activation bar* yang menempel pada *lifeline* serta pesan balasan berpanah terbuka bergaris putus-putus pada titik pengembalian hasil yang tepat.
5. Memeriksa konsistensi pemanggilan *method* pada label pesan terhadap kompartemen *method* pada *class* tujuan di kandidat *class*.
6. Menggambar *sequence diagram* studi kasus laboratorium (`LAB-UC03`, `LAB-UC11`, dan `LAB-UC06`) serta tugas mandiri Sistem Informasi Akademik (`SIA-UC08` sampai `SIA-UC09`), disertai logbook perbaikan.

## 2. Dasar Teori

### 2.1 Sequence Diagram

*Sequence diagram* merupakan diagram interaksi dalam UML (OMG UML 2.5.1) yang memodelkan urutan pertukaran pesan antar peserta (aktor dan objek) untuk satu *use case* tertentu. Dimensi vertikal pada diagram merepresentasikan waktu yang berjalan dari atas ke bawah, sedangkan dimensi horizontal menunjukkan peserta interaksi.

Berbeda dengan *activity diagram* yang berfokus pada alur proses dan perpindahan antar *swimlane*, *sequence diagram* merinci objek mana yang bertanggung jawab mengerjakan setiap langkah pada tabel skenario serta *method* apa yang dipanggil.

### 2.2 Unsur-Unsur Sequence Diagram

Beberapa unsur notasi utama yang digunakan dalam penyusunan *sequence diagram* adalah:

| Unsur | Fungsi |
| :--- | :--- |
| **Aktor** | Pihak di luar sistem yang memulai atau menerima interaksi dengan objek antarmuka. Namanya ditulis tanpa tanda titik dua. |
| **Lifeline dan Nama Objek** | Kotak kepala berisi nama peserta (`:NamaClass`) diikuti garis putus-putus vertikal sebagai garis waktu peserta selama interaksi berlangsung. |
| **Objek Antarmuka** | Objek batas (misalnya `:Sistem Peminjaman` atau `:Sistem Hasil Studi`) yang menyalurkan interaksi aktor ke objek domain. |
| **Activation Bar** | Persegi panjang tipis vertikal pada *lifeline* yang menunjukkan rentang waktu suatu peserta aktif menjalankan panggilan pesan hingga mengembalikan hasil. |
| **Pesan Sinkron** | Garis utuh mendatar dengan mata panah penuh yang menunjukkan pengirim menunggu penerima menyelesaikan panggilan sebelum melanjutkan proses. |
| **Pesan Balasan** | Garis putus-putus mendatar dengan mata panah terbuka yang mengembalikan hasil pemrosesan kepada pengirim pada titik hasil tersedia. |
| **Pesan ke Diri Sendiri** | Panah keluar dari suatu *lifeline* dan kembali ke *lifeline* yang sama untuk menggambarkan pemrosesan internal objek tersebut. |
| **Combined Fragment (`alt`, `opt`, `ref`, `loop`)** | Bingkai interaksi untuk memodelkan percabangan alternatif (`alt`), kondisi opsional/*extend* (`opt`), rujukan *use case* lain/*include* (`ref`), dan perulangan (`loop`). |

### 2.3 Kaidah Penurunan dari Skenario dan Kandidat Class

*Sequence diagram* diturunkan secara sistematis dari tabel skenario (Pertemuan 5) dan kandidat *class* (Pertemuan 7) dengan aturan berikut:

1. **Ketertelusuran Objek:** Seluruh *lifeline* objek domain harus berasal dari kandidat *class* dengan penulisan persis sama diawali titik dua (`:`). Dokumen keluaran seperti bukti pengajuan atau KHS tidak digambar sebagai *lifeline*, melainkan sebagai pesan hasil kepada aktor.
2. **Konsistensi Method:** Nama *method* yang dipanggil pada label pesan wajib tercantum pada kompartemen *method* dari *class* tujuannya (misalnya `periksaKetersediaan()`, `ajukan()`, `prosesKeputusan()`, `catatPengembalian()`, `inputNilai()`, dan `publikasikan()`).
3. **Pemetaan Fragmen:** Relasi *include* dipetakan ke fragmen `ref`, relasi *extend* dipetakan ke fragmen `opt` lengkap dengan *condition* dan *extension point*, serta percabangan *Skenario Alternative* dipetakan ke fragmen `alt` dengan dua *operand* yang masing-masing memiliki *guard* dalam kurung siku (`[...]`).

## 3. Hasil Praktikum

### 3.1 Studi Kasus Laboratorium (LAB)

Pada studi kasus Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus, disusun tiga *sequence diagram* utama:

#### A. Sequence Diagram LAB-UC03: Ajukan Peminjaman
* **Peserta:** `Peminjam` (aktor), `:Sistem Peminjaman` (objek antarmuka), `:Peminjaman` (objek domain), dan `:Peralatan` (objek domain).
* **Penyusunan Bertahap:**
  * **Tahap 1 (Alur Normal):** Menggambarkan urutan 8 pesan utama mulai dari memilih peralatan, memanggil `periksaKetersediaan()` pada `:Peralatan`, mengisi data peminjaman, memeriksa kelengkapan isian (pesan ke diri sendiri pada `:Sistem Peminjaman`), menampilkan ringkasan, mengirim pengajuan, memanggil `ajukan()` pada `:Peminjaman` dengan status *Menunggu Keputusan*, hingga menampilkan nomor pengajuan.
  * **Tahap 2 (*Include* dan Fragmen `alt`):** Membungkus panggilan `periksaKetersediaan()` dalam fragmen `ref` `Periksa Ketersediaan (LAB-UC04)`, menambahkan fragmen `alt` ketersediaan (`[peralatan tersedia]` kosong dan `[peralatan tidak tersedia]` menampilkan pesan gagal), serta fragmen `alt` kelengkapan isian (`[isian lengkap]` dan `[isian tidak lengkap]`).
  * **Tahap 3 (Pesan Balasan dan Fragmen `opt`):** Menambahkan pesan balasan status ketersediaan dan nomor pengajuan, serta fragmen `opt` dengan kondisi `[mahasiswa memilih cetak]` dan *extension point* `Bukti pengajuan tersedia` untuk relasi *extend* `LAB-UC05`.

#### B. Sequence Diagram LAB-UC11: Catat Pengembalian Peralatan
* **Peserta:** `Petugas Laboratorium`, `:Sistem Peminjaman`, `:Pengembalian`, `:Peminjaman`, dan `:Peralatan`.
* **Alur Utama dan Fragmen:** Memuat validasi status peminjaman melalui fragmen `alt` (untuk status bukan *Dipinjam*), pemanggilan fragmen `ref` `Periksa Kondisi Peralatan (LAB-UC12)` yang mengeksekusi `periksaKondisi()` pada `:Peralatan`, fragmen `alt` penanganan kondisi *Rusak Ringan* atau *Rusak Berat*, pemanggilan `catatPengembalian()` pada `:Pengembalian`, serta pembaruan status peminjaman menjadi *Selesai*.

#### C. Sequence Diagram LAB-UC06: Proses Keputusan Peminjaman
* **Peserta:** `Petugas Laboratorium`, `:Sistem Peminjaman`, dan `:Peminjaman`.
* **Alur Utama dan Fragmen:** Mengambil daftar pengajuan berstatus *Menunggu Keputusan*, menangani pengecualian melalui fragmen `alt` bila pengajuan tidak ditemukan atau status telah berubah, serta fragmen `alt` keputusan dengan *operand* `[petugas menyetujui]` yang memanggil `prosesKeputusan()` untuk mengubah status menjadi *Disetujui* dan *operand* `[petugas menolak]` yang mengubah status menjadi *Ditolak*.

### 3.2 Tugas Sistem Informasi Akademik (SIA-UC08 sampai SIA-UC09)

#### A. Deskripsi Proses
*Sequence diagram* SIA menggabungkan alur `SIA-UC08` (Input Nilai Mata Kuliah), proses pengesahan serta publikasi dari *activity diagram* Pertemuan 6, hingga `SIA-UC09` (Lihat KHS) dalam satu kesatuan interaksi yang utuh.

#### B. Pembagian Peserta (Lifeline)

| Peserta | Jenis | Tanggung Jawab dalam Interaksi |
| :--- | :--- | :--- |
| **Dosen** | Aktor | Membuka fungsi input nilai, memilih mata kuliah yang diampu dan mahasiswa, serta mengisikan nilai. |
| **:Sistem Hasil Studi** | Objek Antarmuka | Menampilkan daftar mata kuliah/formulir, memvalidasi rentang nilai, menampilkan konfirmasi, mengirim pemberitahuan hasil studi, dan menampilkan KHS. |
| **:Nilai Mata Kuliah** | Objek Domain | Memeriksa rentang nilai, menyimpan nilai melalui `inputNilai()` (status belum terpublikasi), mempublikasikan nilai melalui `publikasikan()`, dan menyediakan data nilai semester. |
| **Admin Akademik** | Aktor | Memeriksa dan mengesahkan nilai mata kuliah yang telah diinputkan oleh dosen. |
| **Mahasiswa** | Aktor | Menerima pemberitahuan hasil studi, membuka menu KHS, memilih semester, dan melihat KHS. |

#### C. Fragmen Interaksi pada Sequence Diagram SIA

| Unsur Fragmen | Penerapan pada Diagram |
| :--- | :--- |
| **Fragmen `alt` (Rentang Nilai)** | Memisahkan kondisi `[nilai dalam rentang sah]` untuk melanjutkan penyimpanan melalui `inputNilai()` dengan kondisi `[nilai di luar rentang sah]` untuk menampilkan pesan kesalahan kepada Dosen. |
| **Fragmen `alt` (Status Publikasi KHS)** | Memisahkan kondisi `[nilai semester sudah dipublikasikan]` untuk mengambil data dari `:Nilai Mata Kuliah` dan menampilkan KHS dengan kondisi `[nilai semester belum dipublikasikan]` untuk menampilkan informasi bahwa nilai belum tersedia. |

### 3.3 Ringkasan Checklist Evaluasi dan Logbook Perbaikan

Berdasarkan pemeriksaan menggunakan *checklist* penilaian Pertemuan 7:
* Seluruh objek domain telah diawali tanda titik dua (`:`) dan sesuai dengan nama *class* pada diagram kandidat *class*.
* Dokumen keluaran seperti bukti pengajuan dan KHS tidak dimodelkan sebagai *lifeline*, melainkan sebagai pesan keluaran menuju aktor terkait.
* Pemanggilan *method* seperti `periksaKetersediaan()`, `ajukan()`, `periksaKondisi()`, `catatPengembalian()`, `prosesKeputusan()`, `inputNilai()`, dan `publikasikan()` telah disesuaikan dengan *class* tujuannya.
* Perbaikan pada tugas mandiri `LAB-UC06` (seperti penempatan *activation bar*, penulisan *guard* secara eksplisit, dan arah panah pesan balasan) telah dicatat pada logbook perbaikan sebelum berkas final diekspor ke format `.png`.

## 4. Analisis

Penyusunan *sequence diagram* secara bertahap (Tahap 1 hingga Tahap 3) memudahkan pemetaan dari tabel skenario ke dalam model interaksi objek. Pemisahan alur normal terlebih dahulu memastikan bahwa urutan vertikal pesan sinkron dan pesan balasan sudah selaras dengan nomor langkah pada tabel skenario sebelum ditambahkan kompleksitas fragmen `ref`, `alt`, dan `opt`.

Penggunaan pesan ke diri sendiri (*self-message*) pada objek antarmuka (seperti memeriksa kelengkapan isian pada `:Sistem Peminjaman`) menunjukkan pemisahan tanggung jawab (*separation of concerns*) yang jelas: validasi antarmuka ditangani oleh objek batas, sedangkan logika bisnis dan perubahan status data ditangani oleh objek domain (`:Peminjaman`, `:Peralatan`, `:Pengembalian`, dan `:Nilai Mata Kuliah`). Selain itu, penggunaan fragmen `ref` menjaga diagram induk tetap ringkas tanpa perlu menyalin ulang langkah-langkah dari *use case* yang di-*include*.

Pada kasus SIA, penggabungan alur dari input nilai hingga lihat KHS memperlihatkan ketergantungan status data antar-aktor. Nilai yang disimpan dosen melalui `inputNilai()` belum dapat diakses pada KHS mahasiswa sebelum melalui tahap pengesahan oleh Admin Akademik dan pemanggilan `publikasikan()` oleh sistem. Penempatan fragmen `alt` pada pengecekan status publikasi memastikan mahasiswa hanya memperoleh tampilan KHS untuk semester yang nilainya sudah sah dan terpublikasi.

## 5. Kesimpulan

Berdasarkan praktikum yang telah dilaksanakan, dapat disimpulkan bahwa *sequence diagram* memodelkan interaksi antar-objek secara terurut berdasarkan waktu untuk merealisasikan skenario *use case* dan kandidat *class*. Kepatuhan terhadap aturan penamaan *lifeline* objek, pemetaan fragmen (`ref`, `alt`, dan `opt`), penempatan *activation bar*, serta konsistensi pemanggilan *method* pada *class* tujuan menjamin bahwa rancangan interaksi selaras dengan dokumen analisis sebelumnya (skenario Pertemuan 5, *activity diagram* Pertemuan 6, dan kandidat *class* Pertemuan 7).