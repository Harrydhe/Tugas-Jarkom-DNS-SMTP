# Tugas4--DNS

# Apa Itu DNS?

**DNS (Domain Name System)** adalah sistem yang berfungsi menerjemahkan nama domain yang mudah diingat oleh manusia (seperti `google.com`) menjadi alamat IP yang merupakan serangkaian angka yang digunakan komputer untuk berkomunikasi di internet. Bayangkan DNS sebagai buku telepon raksasa yang menghubungkan nama dengan nomor telepon.

## Mengapa DNS Penting?

- **Kemudahan Pengingat**: Kita lebih mudah mengingat "google.com" daripada "142.250.186.142".
- **Efisiensi**: DNS membuat pencarian alamat IP menjadi lebih cepat.
- **Fleksibilitas**: Perubahan alamat IP tidak langsung memengaruhi akses ke situs web.

## Cara Kerja DNS

1. **Pengguna Memasukkan Nama Domain:**
   - Anda mengetikkan alamat situs web (misalnya, `www.example.com`) di browser Anda.

2. **Permintaan ke DNS Resolver:**
   - Browser Anda mengirimkan permintaan ke DNS resolver (biasanya disediakan oleh ISP Anda) untuk mengetahui alamat IP yang sesuai dengan nama domain tersebut.

3. **Pencarian di Cache:**
   - DNS resolver pertama-tama akan memeriksa cache-nya (tempat penyimpanan sementara). Jika alamat IP sudah ada di cache, maka DNS resolver akan langsung memberikan alamat IP tersebut kepada browser Anda.

4. **Permintaan ke Root Server:**
   - Jika alamat IP tidak ditemukan di cache, DNS resolver akan mengirimkan permintaan ke root server DNS. Root server adalah server tingkat atas yang mengetahui lokasi server DNS otoritatif untuk domain tingkat atas (TLD) seperti `.com`, `.net`, dan sebagainya.

5. **Permintaan ke Server DNS Otoritatif:**
   - Root server akan mengarahkan DNS resolver ke server DNS otoritatif untuk domain yang Anda cari. Server DNS otoritatif adalah server yang memiliki informasi lengkap tentang nama domain tersebut.

6. **Mendapatkan Alamat IP:**
   - Server DNS otoritatif akan memberikan alamat IP yang sesuai kepada DNS resolver.

7. **Browser Mengakses Situs Web:**
   - DNS resolver akan mengirimkan alamat IP tersebut ke browser Anda. Browser kemudian akan menghubungi server web di alamat IP tersebut untuk mengambil halaman web yang Anda minta.

## Diagram Alir Kerja DNS

![Cara kerja DNS](https://github.com/Harrydhe/Tugas4--DNS/blob/main/assets/DNS.png)

## Komponen Utama DNS

- **DNS Resolver**: Komputer atau perangkat lunak yang melakukan pencarian alamat IP.
- **Root Server**: Server tingkat atas yang mengarahkan permintaan ke server DNS otoritatif.
- **Server DNS Otoritatif**: Server yang memiliki informasi lengkap tentang nama domain.
- **Cache**: Tempat penyimpanan sementara untuk menyimpan hasil pencarian DNS.

## Kesimpulan

DNS adalah sistem yang sangat penting dalam dunia internet. Dengan DNS, kita dapat dengan mudah mengakses situs web tanpa perlu mengingat deretan angka yang rumit. Proses kerja DNS melibatkan beberapa tahap, mulai dari permintaan pengguna hingga browser menerima alamat IP yang benar.

## Informasi Tambahan

- **DNS Hierarchy**: DNS memiliki hierarki yang terdiri dari root server, TLD server, authoritative server, dan recursive resolver.
- **DNS Caching**: Caching sangat penting untuk meningkatkan kinerja DNS. Dengan caching, hasil pencarian DNS dapat disimpan sementara sehingga permintaan berikutnya dapat dilayani lebih cepat.
- **DNS Security**: DNS juga rentan terhadap serangan seperti DNS hijacking dan DNS amplification. Untuk meningkatkan keamanan, terdapat protokol DNSSEC.
