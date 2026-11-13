# LAPORAN PRAKTIKUM PERTEMUAN 2
## Unified Modeling Language

## 1. Tujuan Praktikum

1. Memahami konsep aktor dalam pemodelan sistem menggunakan UML.
2. Mengidentifikasi aktor yang terlibat dalam suatu sistem berdasarkan skenario yang diberikan.
3. Mengidentifikasi kebutuhan fungsional berdasarkan aktivitas masing-masing aktor.
4. Menentukan hubungan antara aktor dengan fungsi yang tersedia dalam sistem.
5. Memahami batasan hak akses dan tanggung jawab setiap aktor agar tidak terjadi kesalahan dalam pemodelan sistem.
6. Membuat tabel kebutuhan fungsional sebagai dasar dalam penyusunan diagram use case.

## 2. Dasar Teori

### 2.1 Unified Modeling Language (UML)

Unified Modeling Language (UML) merupakan bahasa pemodelan standar yang digunakan untuk menggambarkan struktur dan perilaku suatu sistem. UML membantu proses analisis dan perancangan perangkat lunak melalui berbagai diagram sehingga kebutuhan sistem dapat dipahami dengan lebih jelas.

### 2.2 Aktor (Actor)

Aktor merupakan pihak yang berinteraksi dengan sistem, baik berupa manusia, organisasi, maupun sistem lain. Aktor memiliki peran tertentu dalam menggunakan fungsi yang disediakan oleh sistem.

Dalam diagram use case, aktor biasanya digambarkan menggunakan simbol manusia sederhana (stick figure) yang berada di luar batas sistem.

### 2.3 Kebutuhan Fungsional

Kebutuhan fungsional merupakan kebutuhan yang menjelaskan layanan atau fungsi yang harus disediakan oleh sistem untuk memenuhi kebutuhan pengguna. Kebutuhan ini menggambarkan aktivitas yang dapat dilakukan oleh aktor ketika berinteraksi dengan sistem.

Contohnya adalah melihat informasi, mengelola data, melakukan pencarian, dan mengubah informasi.

### 2.4 Use Case

Use case merupakan gambaran fungsi atau layanan yang disediakan oleh sistem untuk aktor tertentu. Setiap use case menjelaskan tujuan interaksi antara aktor dengan sistem.

Use case biasanya digambarkan menggunakan bentuk oval yang berisi nama fungsi, sedangkan hubungan antara aktor dan use case ditunjukkan menggunakan garis asosiasi.

### 2.5 Hubungan Aktor dengan Use Case

Hubungan aktor dengan use case disebut association atau asosiasi. Hubungan ini menunjukkan bahwa aktor memiliki keterlibatan dalam menjalankan suatu fungsi pada sistem.

Tidak semua aktor dapat mengakses seluruh fungsi yang tersedia. Setiap fungsi harus dihubungkan dengan aktor sesuai tanggung jawab dan kebutuhan masing-masing.

## 3. Hasil Praktikum

Pada praktikum pertemuan kedua dilakukan identifikasi aktor dan kebutuhan fungsional berdasarkan dua skenario sistem, yaitu sistem pengelolaan peralatan laboratorium dan Sistem Informasi Akademik (SIA).

### 3.1 Skenario Sistem Pengelolaan Peralatan Laboratorium

Pada skenario pertama, mahasiswa dapat melihat informasi ketersediaan peralatan melalui sistem, sedangkan petugas laboratorium bertanggung jawab mengelola data peralatan.

Berdasarkan skenario tersebut, terdapat dua aktor dan dua kebutuhan fungsional yang berhasil diidentifikasi.

**Identifikasi Aktor**

| No. | Aktor | Deskripsi |
|---|---|---|
| 1 | Mahasiswa | Pengguna sistem yang dapat melihat informasi ketersediaan peralatan laboratorium. |
| 2 | Petugas Laboratorium | Pengguna sistem yang bertanggung jawab mengelola data peralatan laboratorium. |

**Tabel Kebutuhan Fungsional**

| ID Kebutuhan | Aktor | Nama Fungsi |
|---|---|---|
| LAB-R01 | Mahasiswa | Lihat ketersediaan peralatan |
| LAB-R02 | Petugas Laboratorium | Kelola data peralatan |

**Hubungan Aktor dengan Fungsi**

| Aktor | Fungsi yang Dapat Diakses |
|---|---|
| Mahasiswa | Lihat ketersediaan peralatan |
| Petugas Laboratorium | Kelola data peralatan |

Berdasarkan hasil identifikasi, mahasiswa hanya dihubungkan dengan fungsi melihat ketersediaan peralatan. Sementara itu, petugas laboratorium hanya dihubungkan dengan fungsi mengelola data peralatan. Kedua aktor memiliki tanggung jawab yang berbeda sesuai dengan kebutuhan sistem.

### 3.2 Skenario Sistem Informasi Akademik (SIA)

Pada skenario kedua, mahasiswa dapat melihat jadwal kuliah melalui Sistem Informasi Akademik. Sementara itu, admin akademik memiliki tanggung jawab untuk mengelola jadwal kuliah.

Dalam skenario ini, mahasiswa tidak memiliki hak untuk mengelola jadwal kuliah dan admin akademik tidak dihubungkan dengan fungsi melihat jadwal sebagai pengguna mahasiswa.

**Identifikasi Aktor**

| No. | Aktor | Deskripsi |
|---|---|---|
| 1 | Mahasiswa | Pengguna sistem yang dapat melihat informasi jadwal kuliah. |
| 2 | Admin Akademik | Pengguna sistem yang bertanggung jawab mengelola jadwal kuliah. |

**Tabel Kebutuhan Fungsional**

| ID Kebutuhan | Aktor | Nama Fungsi |
|---|---|---|
| SIA-R01 | Mahasiswa | Lihat jadwal kuliah |
| SIA-R02 | Admin Akademik | Kelola jadwal kuliah |

**Hubungan Aktor dengan Fungsi**

| Aktor | Fungsi yang Dapat Diakses |
|---|---|
| Mahasiswa | Lihat jadwal kuliah |
| Admin Akademik | Kelola jadwal kuliah |

Berdasarkan hasil identifikasi, mahasiswa hanya memiliki hubungan dengan fungsi melihat jadwal kuliah. Admin akademik hanya memiliki hubungan dengan fungsi mengelola jadwal kuliah. Pembagian tersebut dilakukan agar setiap fungsi sesuai dengan tanggung jawab masing-masing aktor.

### 3.3 Rekapitulasi Hasil Identifikasi

Berikut merupakan rekapitulasi aktor dan kebutuhan fungsional dari kedua skenario praktikum.

| No. | Sistem | Jumlah Aktor | Jumlah Kebutuhan Fungsional |
|---|---|---:|---:|
| 1 | Sistem Pengelolaan Peralatan Laboratorium | 2 | 2 |
| 2 | Sistem Informasi Akademik | 2 | 2 |
| **Total** | **2 Sistem** | **4** | **4** |

## 4. Analisis

Berdasarkan hasil praktikum, proses identifikasi aktor dan kebutuhan fungsional dilakukan dengan memahami aktivitas serta tanggung jawab setiap pengguna dalam sistem. Pada sistem pengelolaan peralatan laboratorium, terdapat mahasiswa yang berperan melihat ketersediaan peralatan dan petugas laboratorium yang bertugas mengelola data peralatan. Sementara itu, pada Sistem Informasi Akademik, mahasiswa berperan melihat jadwal kuliah dan admin akademik bertanggung jawab mengelola jadwal tersebut.

Dari kedua skenario tersebut, dapat diketahui bahwa setiap aktor memiliki hak akses dan fungsi yang berbeda. Hubungan antara aktor dan fungsi harus disesuaikan dengan kebutuhan yang telah ditentukan dalam skenario. Mahasiswa tidak dihubungkan dengan fungsi pengelolaan data peralatan maupun pengelolaan jadwal kuliah. Begitu pula admin akademik tidak dihubungkan dengan fungsi melihat jadwal kuliah sebagai pengguna mahasiswa. Hal ini menunjukkan bahwa identifikasi aktor dan kebutuhan fungsional perlu dilakukan secara tepat agar pemodelan sistem tidak menghasilkan hubungan yang keliru.

Hasil identifikasi ini dapat digunakan sebagai dasar dalam pembuatan diagram use case. Dengan adanya tabel kebutuhan fungsional, proses pemodelan menjadi lebih terarah karena setiap aktor dan fungsi sudah memiliki identitas serta hubungan yang jelas.

## 5. Kesimpulan

Berdasarkan praktikum pertemuan kedua, dapat disimpulkan bahwa identifikasi aktor dan kebutuhan fungsional merupakan tahapan penting dalam proses analisis sistem. Melalui dua skenario yang diberikan, yaitu sistem pengelolaan peralatan laboratorium dan Sistem Informasi Akademik, berhasil diidentifikasi empat aktor dan empat kebutuhan fungsional. Setiap aktor memiliki fungsi yang berbeda sesuai dengan tanggung jawabnya masing-masing. Selain itu, hubungan antara aktor dan fungsi harus disesuaikan dengan skenario agar tidak terjadi kesalahan dalam menentukan hak akses. Hasil identifikasi tersebut menjadi dasar dalam penyusunan diagram use case untuk menggambarkan interaksi antara pengguna dengan sistem.

## Referensi

1. Institut Teknologi Garut. *Jobsheet Praktikum Analisis dan Desain Berorientasi Objek, Pertemuan 2*.
2. Object Management Group. *Unified Modeling Language (UML), Version 2.5.1*. https://www.omg.org/spec/UML/2.5.1/About-UML/
3. diagrams.net. Dokumentasi draw.io. https://www.drawio.com/docs/