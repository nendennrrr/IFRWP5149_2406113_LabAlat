# LAPORAN PRAKTIKUM PERTEMUAN 1
## Pengenalan Lingkungan Praktikum dan Kakas Pemodelan UML

## 1. Tujuan Praktikum

1. Mengenal lingkungan praktikum dan kakas yang digunakan untuk membuat diagram UML.
2. Menyiapkan workspace atau folder proyek dengan struktur yang rapi dan mudah dikelola.
3. Mempraktikkan fitur dasar kakas UML, seperti membuat kanvas, menambahkan elemen, menghubungkan elemen, memberi label, menyimpan, dan mengekspor diagram.
4. Memastikan berkas sumber diagram dapat dibuka kembali dan disunting.
5. Membuat dokumentasi praktikum melalui README dan logbook.

## 2. Dasar Teori

### 2.1 Unified Modeling Language (UML)

Unified Modeling Language (UML) merupakan bahasa pemodelan yang digunakan untuk menggambarkan rancangan, struktur, maupun perilaku suatu sistem. UML membantu pengembang memahami sistem melalui representasi visual sebelum proses pembangunan perangkat lunak dilakukan.

### 2.2 Kakas Pemodelan UML

Kakas pemodelan UML merupakan aplikasi yang digunakan untuk membuat dan mengelola diagram. Beberapa contoh kakas yang dapat digunakan adalah draw.io (diagrams.net), Visual Paradigm, dan StarUML.

| Kakas | Kegunaan |
|---|---|
| draw.io / diagrams.net | Membuat diagram secara daring maupun melalui aplikasi desktop. |
| Visual Paradigm | Membuat dan mengelola berbagai jenis diagram UML. |
| StarUML | Membantu pemodelan sistem menggunakan diagram UML. |

### 2.3 Workspace dan Struktur Proyek

Workspace adalah ruang kerja digital untuk menyimpan seluruh berkas praktikum. Struktur folder yang teratur membantu pengguna menemukan dokumen, membedakan hasil latihan dengan model yang telah divalidasi, serta memudahkan pemeriksaan dan pengembangan pada pertemuan berikutnya.

Berikut struktur folder proyek yang digunakan sebagai acuan:

| Nama Folder | Isi atau Kegunaan |
|---|---|
| `00_administrasi` | Logbook dan dokumen administrasi praktikum. |
| `01_skenario` | Dokumen skenario kasus praktikum. |
| `02_template` | Template metadata artefak. |
| `03_latihan_tools` | Berkas sumber dan hasil ekspor diagram latihan. |
| `04_model_analisis` | Tempat penyimpanan model analisis. |
| `05_model_desain` | Tempat penyimpanan model desain. |
| `06_laporan` | Laporan singkat praktikum. |

### 2.4 Diagram Aktivitas

Diagram aktivitas merupakan salah satu diagram UML yang digunakan untuk menggambarkan urutan aktivitas dalam suatu proses. Pada latihan pertemuan ini, diagram dibuat secara sederhana dengan empat elemen, yaitu node awal, aktivitas "Buka daftar peralatan", aktivitas "Lihat informasi ketersediaan", dan node akhir. Keempat elemen dihubungkan menggunakan alur kontrol.

### 2.5 Berkas Sumber dan Hasil Ekspor

Berkas sumber menyimpan diagram agar dapat dibuka dan disunting kembali. Pada draw.io, berkas sumber umumnya disimpan dengan ekstensi `.drawio`. Sementara itu, hasil ekspor seperti PNG atau SVG digunakan untuk menampilkan dan memeriksa diagram.

| Jenis Berkas | Format | Fungsi |
|---|---|---|
| Berkas sumber | `.drawio` | Menyimpan diagram agar dapat dibuka dan disunting kembali. |
| Hasil ekspor | `.png` | Menampilkan diagram dalam bentuk gambar. |
| Hasil ekspor | `.svg` | Menampilkan diagram dalam format gambar vektor. |

## 3. Hasil Praktikum

Praktikum pertemuan pertama berfokus pada persiapan lingkungan kerja dan pengenalan fitur dasar kakas UML. Hasil pekerjaan yang perlu disiapkan berdasarkan jobsheet dirangkum dalam tabel berikut.

| No. | Kegiatan | Hasil yang Diharapkan |
|---|---|---|
| 1 | Membuat workspace proyek | Folder induk dan subfolder tersusun sesuai struktur jobsheet. |
| 2 | Menyiapkan dokumentasi | Tersedia README, dokumen skenario, template metadata, dan logbook. |
| 3 | Membuat diagram aktivitas | Diagram memuat empat elemen sesuai skenario S-ORI-01. |
| 4 | Menghubungkan elemen | Terdapat tiga alur kontrol yang menghubungkan setiap elemen. |
| 5 | Menyimpan dan mengekspor diagram | Tersedia berkas sumber dan hasil ekspor dengan versi yang sama. |
| 6 | Membuka ulang berkas sumber | Berkas dapat dibuka kembali dan diagram masih dapat disunting. |

### 3.1 Rancangan Diagram Aktivitas Latihan

Diagram aktivitas dibuat berdasarkan skenario S-ORI-01, yaitu mahasiswa membuka daftar peralatan dan melihat informasi ketersediaan.

| Urutan | Elemen Diagram | Keterangan |
|---|---|---|
| 1 | Node awal | Menandai dimulainya aktivitas. |
| 2 | Buka daftar peralatan | Aktivitas pertama yang dilakukan mahasiswa. |
| 3 | Lihat informasi ketersediaan | Aktivitas untuk melihat ketersediaan peralatan. |
| 4 | Node akhir | Menandai berakhirnya aktivitas. |

Alur diagram:

`Node Awal → Buka daftar peralatan → Lihat informasi ketersediaan → Node Akhir`

Diagram diberi judul **"Latihan kakas — S-ORI-01"** dan catatan **"Belum divalidasi sebagai model proses"**.

### 3.2 Data Hasil Pelaksanaan

| No. | Aspek Pemeriksaan | Hasil Aktual |
|---|---|---|
| 1 | Kakas yang digunakan | [Isi nama kakas] |
| 2 | Folder proyek berhasil dibuat | [Ya/Tidak] |
| 3 | Dokumentasi proyek tersedia | [Ya/Tidak] |
| 4 | Diagram aktivitas berhasil dibuat | [Ya/Tidak] |
| 5 | Berkas sumber berhasil disimpan | [Ya/Tidak] |
| 6 | Berkas sumber berhasil dibuka kembali dan disunting | [Ya/Tidak] |
| 7 | Format hasil ekspor | [PNG/SVG/lainnya] |
| 8 | Kendala yang ditemukan | [Isi jika ada] |

## 4. Analisis

Praktikum pertemuan pertama memberikan pemahaman awal mengenai pentingnya menyiapkan lingkungan kerja sebelum membuat pemodelan sistem. Struktur folder yang teratur membuat berkas proyek lebih mudah ditemukan dan membantu memisahkan diagram latihan dari model analisis maupun desain yang nantinya telah diperiksa. Dokumentasi melalui README dan logbook juga berguna untuk mencatat pekerjaan, pemeriksaan, kendala, serta tindak lanjut praktikum.

Latihan diagram aktivitas S-ORI-01 digunakan untuk mengenal fungsi dasar kakas UML, bukan untuk menghasilkan model proses bisnis yang sudah tervalidasi. Melalui latihan tersebut, mahasiswa dapat mempraktikkan pembuatan kanvas, penempatan elemen, pemberian label, dan penghubungan antar-elemen. Penyimpanan berkas sumber dan pengujian dengan membuka kembali berkas menjadi hal penting karena diagram harus tetap dapat diedit, bukan hanya tersedia sebagai gambar hasil ekspor.

Keberhasilan praktikum dapat diperiksa menggunakan beberapa kriteria berikut.

| No. | Kriteria Pemeriksaan | Tujuan |
|---|---|---|
| 1 | Struktur folder tersusun dengan benar | Memastikan workspace tertata. |
| 2 | README dan logbook tersedia | Memastikan dokumentasi praktikum lengkap. |
| 3 | Diagram memiliki empat elemen dan tiga penghubung | Memastikan latihan sesuai instruksi jobsheet. |
| 4 | Label diagram dapat dibaca | Memudahkan pemeriksaan hasil diagram. |
| 5 | Berkas sumber dapat dibuka dan disunting kembali | Memastikan diagram tidak hanya tersimpan sebagai gambar. |
| 6 | Hasil ekspor sesuai dengan berkas sumber | Menjaga konsistensi hasil praktikum. |
| 7 | Diagram diberi status belum divalidasi | Menghindari anggapan bahwa diagram merupakan model proses final. |

Dengan demikian, keberhasilan praktikum tidak hanya dilihat dari tampilan diagram, tetapi juga dari kerapian workspace, kelengkapan dokumentasi, konsistensi nama dan versi berkas, serta kemampuan membuka kembali sumber diagram. Aturan bisnis yang belum ditentukan dalam jobsheet, seperti mekanisme persetujuan atau perhitungan denda, tidak boleh ditambahkan sebagai fakta pada diagram latihan.

## 5. Kesimpulan

Berdasarkan materi praktikum pertemuan pertama, dapat disimpulkan bahwa pengenalan lingkungan praktikum dan kakas pemodelan UML merupakan tahap awal untuk mendukung kegiatan analisis dan desain berorientasi objek. Mahasiswa perlu menyiapkan workspace yang terstruktur, mengenal fitur dasar kakas UML, serta memahami perbedaan antara berkas sumber dan hasil ekspor. Latihan diagram aktivitas S-ORI-01 membantu mahasiswa mencoba proses pembuatan dan penyimpanan diagram secara sederhana. Diagram tersebut masih berstatus latihan dan belum dapat dianggap sebagai model proses yang tervalidasi. Keberhasilan pelaksanaan praktikum perlu dibuktikan melalui hasil pekerjaan aktual, pemeriksaan berkas, dan dokumentasi dalam logbook.

## Referensi

1. Institut Teknologi Garut. *Jobsheet Praktikum Analisis dan Desain Berorientasi Objek, Pertemuan 1: Pengenalan Lingkungan Praktikum dan Kakas Pemodelan UML*.
2. diagrams.net. Dokumentasi draw.io. https://www.drawio.com/docs/
3. Object Management Group. *Unified Modeling Language (UML), Version 2.5.1*. https://www.omg.org/spec/UML/2.5.1/About-UML/