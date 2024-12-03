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


**DNS (Domain Name System)** adalah sistem yang berfungsi untuk menerjemahkan nama domain yang mudah diingat (seperti `google.com`) menjadi alamat IP yang digunakan oleh komputer untuk berkomunikasi di internet.

## 1. Hierarki DNS

DNS memiliki struktur hierarkis yang mirip dengan sistem direktori pada komputer. Hierarki ini dimulai dari:

- **Root Server**: Tingkat paling atas dalam hierarki DNS. Ada beberapa root server di seluruh dunia yang berfungsi sebagai titik awal untuk semua permintaan DNS.
- **TLD Server (Top-Level Domain)**: Server yang menangani domain tingkat atas seperti `.com`, `.net`, `.org`, dan sebagainya.
- **Authoritative Server**: Server yang memiliki informasi spesifik tentang sebuah domain. Biasanya dikelola oleh pemilik domain.
- **Recursive Resolver**: Server yang melakukan pencarian DNS atas nama klien.

## 2. Jenis-Jenis Record DNS

Selain alamat IP (tipe A), DNS juga mendukung berbagai jenis record lainnya, seperti:

- **AAAA**: Untuk alamat IPv6.
- **CNAME**: Alias untuk nama domain lain.
- **MX**: Untuk server mail exchange (server email).
- **NS**: Untuk server name server (server DNS otoritatif).
- **TXT**: Untuk menyimpan teks, sering digunakan untuk verifikasi domain.

## 3. DNS Caching

**DNS caching** adalah proses menyimpan hasil pencarian DNS secara sementara untuk mempercepat permintaan DNS di masa mendatang. Cache DNS dapat berada di berbagai tingkat, mulai dari browser, sistem operasi, hingga DNS resolver.

## 4. DNS Over HTTPS (DoH)

**DoH (DNS Over HTTPS)** adalah protokol yang mengenkripsi lalu lintas DNS melalui HTTPS, sehingga meningkatkan privasi pengguna. Dengan DoH, ISP tidak dapat melihat situs web yang Anda kunjungi.

## 5. DNS Over TLS (DoT)

**DoT (DNS Over TLS)** juga merupakan protokol yang mengenkripsi lalu lintas DNS, tetapi menggunakan TLS sebagai protokol transport.

## 6. DNSSEC

**DNSSEC (DNS Security Extensions)** adalah mekanisme keamanan yang dirancang untuk melindungi DNS dari pemalsuan. DNSSEC menggunakan tanda tangan digital untuk memverifikasi integritas data DNS.

## 7. Masalah Umum pada DNS

Beberapa masalah umum yang terjadi pada DNS antara lain:

- **DNS Hijacking**: Serangan di mana peretas mengalihkan lalu lintas DNS ke server palsu.
- **DNS Amplification**: Serangan DDoS yang memanfaatkan DNS untuk memperkuat serangan.
- **DNS Cache Poisoning**: Serangan yang menyuntikkan data palsu ke dalam cache DNS.

## Cara Kerja DNS Secara Lebih Detail

### Proses Resolusi DNS

1. **Pengguna Memasukkan Nama Domain**:
   - Pengguna mengetikkan nama domain di browser.
   
2. **Permintaan ke DNS Resolver**:
   - Browser mengirimkan permintaan ke DNS resolver yang terdekat.

3. **Pencarian di Cache Lokal**:
   - DNS resolver memeriksa cache lokalnya terlebih dahulu. Jika ditemukan, alamat IP langsung diberikan.

4. **Permintaan ke Root Server**:
   - Jika tidak ditemukan di cache lokal, permintaan diteruskan ke root server.

5. **Permintaan ke TLD Server**:
   - Root server mengarahkan permintaan ke TLD server yang sesuai.

6. **Permintaan ke Authoritative Server**:
   - TLD server mengarahkan permintaan ke authoritative server untuk domain tersebut.

7. **Mendapatkan Alamat IP**:
   - Authoritative server memberikan alamat IP kepada DNS resolver.

8. **Kembali ke Browser**:
   - DNS resolver mengembalikan alamat IP ke browser.

9. **Koneksi ke Server Web**:
   - Browser menggunakan alamat IP untuk terhubung ke server web.

## Contoh Kasus Penggunaan DNS

- **Akses ke Situs Web**: Setiap kali Anda mengunjungi situs web, DNS menerjemahkan nama domain menjadi alamat IP.
- **Email**: DNS digunakan untuk menemukan server mail exchange (MX) untuk mengirim dan menerima email.
- **Aplikasi Jaringan**: Banyak aplikasi jaringan menggunakan DNS untuk menemukan server yang diperlukan.

## Kesimpulan

DNS adalah komponen penting dalam infrastruktur internet. Dengan memahami cara kerjanya, Anda akan lebih memahami bagaimana internet berfungsi dan bagaimana data mengalir dari satu perangkat ke perangkat lainnya.

