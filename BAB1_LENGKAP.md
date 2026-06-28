# KATA PENGANTAR

Assalamu'alaikum Warahmatullahi Wabarakatuh.

Puji syukur ke hadirat Allah SWT atas segala rahmat, hidayah, dan karunia-Nya sehingga penulis dapat menyelesaikan laporan tugas akhir yang berjudul **"Rancang Bangun Platform Pelaporan Kondisi Jalan Berbasis Web di Kota Pekanbaru"** dengan baik. Shalawat serta salam senantiasa tercurah kepada Nabi Muhammad SAW, beserta keluarga, sahabat, dan pengikutnya hingga akhir zaman.

Laporan ini disusun sebagai salah satu syarat dalam menyelesaikan studi pada Program Studi Teknik Informatika, Fakultas Teknik, Universitas Islam Riau. Dalam penyusunan laporan ini, penulis membahas mengenai perancangan dan pembangunan sebuah platform berbasis web yang memungkinkan masyarakat Kota Pekanbaru untuk melaporkan kondisi kerusakan jalan secara langsung melalui sistem yang terintegrasi dengan peta digital, serta memfasilitasi proses verifikasi oleh Admin Dinas PUPR, penugasan oleh Koordinator Lapangan, hingga pelaksanaan perbaikan oleh Teknisi Lapangan.

Penulis menyadari bahwa laporan ini tidak akan terselesaikan tanpa bantuan, dukungan, dan bimbingan dari berbagai pihak. Oleh karena itu, pada kesempatan ini, penulis menyampaikan ucapan terima kasih yang sebesar-besarnya kepada:

1. **Bapak Akmar, S.T., M.Kom.** selaku Dosen Pembimbing yang telah memberikan arahan, bimbingan, dan masukan yang sangat berharga selama penyusunan laporan ini.
2. Kedua orang tua dan keluarga tercinta yang senantiasa memberikan doa, dukungan moril, dan motivasi yang tiada henti.
3. Bapak dan Ibu Dosen Program Studi Teknik Informatika, Fakultas Teknik, Universitas Islam Riau yang telah memberikan ilmu pengetahuan selama masa perkuliahan.
4. Rekan-rekan mahasiswa yang telah membantu dan memberikan dukungan dalam penyelesaian tugas akhir ini.

Penulis menyadari bahwa laporan ini masih memiliki kekurangan dan keterbatasan. Oleh karena itu, kritik dan saran yang membangun sangat diharapkan demi kesempurnaan laporan ini. Semoga laporan ini dapat memberikan manfaat bagi pengembangan ilmu pengetahuan, khususnya di bidang sistem informasi dan teknologi web.

Pekanbaru, 2026

Penulis,

Muhammad Rifa'i
NIM. 233510484


# BAB I: PENDAHULUAN

## 1.1 Latar Belakang

Jalan merupakan salah satu infrastruktur vital yang memiliki peran strategis dalam mendukung aktivitas perekonomian, mobilitas masyarakat, dan konektivitas antar wilayah. Kondisi jalan yang baik dan terawat menjadi faktor penting dalam mendukung kelancaran transportasi serta meningkatkan keselamatan pengguna jalan. Namun, pada kenyataannya, kerusakan jalan masih menjadi permasalahan yang sering dijumpai di berbagai daerah di Indonesia, termasuk di Kota Pekanbaru.

Kota Pekanbaru sebagai ibu kota Provinsi Riau merupakan salah satu kota dengan pertumbuhan ekonomi dan jumlah penduduk yang signifikan. Tingginya volume kendaraan yang melintas, intensitas curah hujan yang tinggi, serta faktor lainnya menyebabkan infrastruktur jalan di beberapa titik mengalami kerusakan seperti jalan berlubang, retak, ambles, hingga kerusakan aspal. Kerusakan jalan ini tidak hanya mengganggu kenyamanan dan keselamatan pengguna, tetapi juga berpotensi menimbulkan kerugian ekonomi.

Berdasarkan hasil observasi, proses pelaporan kerusakan jalan yang berjalan saat ini masih menggunakan mekanisme manual, seperti pengaduan melalui surat, telepon, atau datang langsung ke kantor Dinas Pekerjaan Umum dan Penataan Ruang (PUPR). Pendekatan ini memiliki beberapa kelemahan, antara lain:
1. **Kurangnya transparansi** — masyarakat tidak dapat memantau perkembangan laporan yang telah disampaikan.
2. **Tidak terstruktur** — data laporan tidak terdokumentasi dengan rapi sehingga menyulitkan proses analisis dan prioritas penanganan.
3. **Koordinasi yang lambat** — tidak adanya sistem yang menghubungkan antara pelapor, admin, koordinator lapangan, dan teknisi secara real-time.
4. **Tidak adanya informasi lokasi yang presisi** — pelaporan tanpa koordinat geografis yang akurat menyulitkan petugas dalam menemukan lokasi kerusakan.

Perkembangan teknologi web saat ini memungkinkan dibangunnya sebuah sistem informasi terpadu yang dapat mengatasi permasalahan tersebut. Dengan memanfaatkan teknologi seperti **React** sebagai framework frontend, **TypeScript** untuk type safety, **Supabase** sebagai Backend as a Service yang menyediakan database PostgreSQL, autentikasi, dan realtime capabilities, serta **Leaflet** sebagai pustaka peta interaktif, sebuah platform pelaporan kondisi jalan dapat dibangun secara efektif dan efisien.

Berdasarkan uraian di atas, penulis tertarik untuk melakukan penelitian dan pembangunan sebuah platform pelaporan kondisi jalan berbasis web di Kota Pekanbaru yang diberi nama **JalanKita Pekanbaru**. Platform ini diharapkan dapat menjembatani komunikasi antara masyarakat sebagai pelapor, Admin Dinas PUPR sebagai verifikator, Koordinator Lapangan sebagai pengawas, serta Teknisi Lapangan sebagai pelaksana perbaikan, dalam satu sistem yang terintegrasi, transparan, dan real-time.

## 1.2 Rumusan Masalah

Berdasarkan latar belakang yang telah diuraikan, maka rumusan masalah dalam penelitian ini adalah sebagai berikut:

1. Bagaimana merancang platform pelaporan kondisi jalan berbasis web yang dapat memfasilitasi proses pelaporan, verifikasi, penugasan, dan perbaikan jalan di Kota Pekanbaru?
2. Bagaimana mengimplementasikan platform pelaporan kondisi jalan dengan fitur peta interaktif, manajemen status laporan, notifikasi real-time, serta peran pengguna yang berbeda (masyarakat, admin, koordinator, dan teknisi)?
3. Bagaimana hasil pengujian terhadap fungsionalitas platform yang dibangun dalam memenuhi kebutuhan pengguna?

## 1.3 Batasan Masalah

Agar penelitian ini lebih terfokus dan terarah, maka ditetapkan batasan masalah sebagai berikut:

1. **Wilayah** — Platform hanya mencakup lokasi pelaporan kerusakan jalan di wilayah administratif Kota Pekanbaru.
2. **Peran Pengguna** — Sistem memiliki empat peran pengguna, yaitu Masyarakat (citizen), Admin Dinas PUPR (admin), Koordinator Lapangan (coordinator), dan Teknisi Lapangan (technician).
3. **Platform** — Aplikasi dibangun berbasis web (web application) dan tidak mencakup pengembangan aplikasi mobile native.
4. **Backend** — Menggunakan Supabase sebagai Backend as a Service yang mencakup database PostgreSQL, autentikasi, penyimpanan file, dan fitur real-time.
5. **Teknologi Frontend** — Menggunakan React 19 dengan TypeScript, Vite sebagai build tool, Tailwind CSS untuk styling, dan Leaflet untuk peta interaktif.
6. **Fitur Kecerdasan Buatan** — Penelitian ini tidak mencakup implementasi kecerdasan buatan atau machine learning untuk deteksi kerusakan jalan secara otomatis.
7. **Sumber Data** — Data kecamatan dan kelurahan yang digunakan adalah data wilayah administratif Kota Pekanbaru.

## 1.4 Tujuan Penelitian

Adapun tujuan dari penelitian ini adalah sebagai berikut:

1. Merancang platform pelaporan kondisi jalan berbasis web yang dapat digunakan oleh masyarakat Kota Pekanbaru untuk melaporkan kerusakan jalan serta memfasilitasi proses verifikasi, penugasan, dan perbaikan oleh pihak terkait.
2. Mengimplementasikan platform pelaporan kondisi jalan menggunakan React, TypeScript, Supabase, dan Leaflet dengan fitur pelaporan berbasis peta interaktif, manajemen status laporan, notifikasi real-time, serta sistem peran pengguna yang terintegrasi.
3. Menguji platform yang dibangun untuk memastikan bahwa seluruh fungsionalitas berjalan sesuai dengan kebutuhan yang telah ditetapkan.

## 1.5 Manfaat Penelitian

Manfaat yang diharapkan dari penelitian ini adalah sebagai berikut:

### 1.5.1 Manfaat Praktis

1. **Bagi Masyarakat Kota Pekanbaru** — Memberikan kemudahan dalam melaporkan kerusakan jalan secara digital dilengkapi dengan foto dan lokasi GPS, serta dapat memantau perkembangan penanganan laporan secara transparan.
2. **Bagi Admin Dinas PUPR** — Mempermudah proses verifikasi laporan, manajemen data pengguna, dan pemantauan statistik kerusakan jalan melalui dashboard yang informatif.
3. **Bagi Koordinator Lapangan** — Memudahkan dalam membagi dan menugaskan pekerjaan kepada teknisi serta memantau progress perbaikan secara real-time.
4. **Bagi Teknisi Lapangan** — Mendapatkan informasi tugas yang jelas, lokasi yang presisi, serta kemudahan dalam mendokumentasikan progress perbaikan.

### 1.5.2 Manfaat Akademis

1. Menambah wawasan dan penerapan ilmu pengetahuan di bidang rekayasa perangkat lunak, khususnya dalam pengembangan aplikasi web menggunakan arsitektur modern.
2. Menjadi referensi bagi penelitian selanjutnya yang berkaitan dengan sistem pelaporan infrastruktur berbasis web dan Geographic Information System (GIS).

## 1.6 Metodologi Penelitian

Metodologi penelitian yang digunakan dalam penelitian ini terdiri dari beberapa tahapan sebagai berikut:

### 1.6.1 Metode Pengumpulan Data

1. **Studi Literatur** — Mempelajari referensi dari buku, jurnal, dan dokumentasi teknologi yang digunakan, seperti dokumentasi React, Supabase, Leaflet, serta penelitian terkait sistem pelaporan infrastruktur.
2. **Observasi** — Melakukan pengamatan terhadap proses pelaporan kerusakan jalan yang berjalan saat ini untuk mengidentifikasi kebutuhan dan permasalahan.
3. **Wawancara** — Berdiskusi dengan pihak terkait untuk menggali kebutuhan sistem dan validasi fitur.

### 1.6.2 Metode Pengembangan Perangkat Lunak

Metode pengembangan perangkat lunak yang digunakan adalah **Waterfall**, yang terdiri dari tahapan:

1. **Analisis Kebutuhan (Requirement Analysis)** — Mengidentifikasi kebutuhan fungsional dan nonfungsional sistem berdasarkan permasalahan yang ditemukan.
2. **Perancangan Sistem (System Design)** — Merancang arsitektur sistem, basis data, diagram UML (Use Case, Activity, Sequence, Class), serta antarmuka pengguna.
3. **Implementasi (Implementation)** — Menulis kode program menggunakan React 19, TypeScript, Tailwind CSS, dan Supabase sebagai backend.
4. **Pengujian (Testing)** — Melakukan pengujian fungsional menggunakan metode Black Box untuk memastikan setiap fitur berjalan sesuai spesifikasi.
5. **Deployment** — Menempatkan aplikasi pada server hosting agar dapat diakses oleh pengguna.

### 1.6.3 Metode Pengujian

Pengujian sistem dilakukan menggunakan metode **Black Box Testing**, yaitu menguji fungsionalitas sistem berdasarkan input dan output yang diharapkan tanpa melihat detail implementasi kode. Selain itu, dilakukan pula **pengujian usability** untuk mengevaluasi tingkat kemudahan penggunaan platform oleh pengguna.

## 1.7 Sistematika Penulisan

Sistematika penulisan laporan tugas akhir ini disusun dalam lima bab dengan urutan sebagai berikut:

### BAB I: PENDAHULUAN

Bab ini berisi latar belakang masalah, rumusan masalah, batasan masalah, tujuan penelitian, manfaat penelitian, metodologi penelitian, dan sistematika penulisan laporan.

### BAB II: TINJAUAN PUSTAKA

Bab ini membahas teori-teori dasar yang mendukung penelitian, meliputi konsep sistem informasi berbasis web, Geographic Information System (GIS), framework React, TypeScript, Supabase sebagai Backend as a Service, PostgreSQL, Leaflet, serta konsep workflow dan status management.

### BAB III: ANALISIS DAN PERANCANGAN SISTEM

Bab ini menguraikan analisis permasalahan, analisis kebutuhan fungsional dan nonfungsional, pemodelan sistem menggunakan diagram UML (Use Case, Activity, Sequence, Class), perancangan basis data, perancangan antarmuka, serta arsitektur sistem secara keseluruhan.

### BAB IV: IMPLEMENTASI DAN PENGUJIAN SISTEM

Bab ini menjelaskan implementasi dari perancangan yang telah dibuat, meliputi spesifikasi perangkat keras dan lunak, implementasi basis data, implementasi backend dan frontend, implementasi fitur-fitur sistem, serta hasil pengujian menggunakan metode Black Box dan analisis hasil pengujian.

### BAB V: PENUTUP

Bab ini berisi kesimpulan dari hasil penelitian yang telah dilakukan serta saran untuk pengembangan lebih lanjut dari platform yang telah dibangun.
