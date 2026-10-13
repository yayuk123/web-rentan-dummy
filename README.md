# Portal Mahasiswa Dummy (Web Rentan Sengaja)

Aplikasi web satu halaman (HTML, CSS, JavaScript) untuk praktikum Keamanan Sistem Informasi.
Semua data adalah **data sintetis**. Seluruh logika berjalan di browser (tanpa server dan tanpa database sungguhan).
Kerentanan dibuat **dengan sengaja** untuk tujuan belajar.

## Akun dummy
| Username | Sandi |
|---|---|
| mhs1 | mhs123 |
| mhs2 | 123456 |

## Kerentanan yang sengaja dibuat
1. **IDOR / kontrol akses lemah**: halaman `#/profil/{id}` tidak memeriksa pemilik data. Setelah login sebagai `mhs1`, ubah alamat menjadi `#/profil/2` untuk melihat data mahasiswa lain.
2. **Stored XSS**: komentar di Forum disimpan lalu dirender sebagai HTML mentah. Komentar `<img src=x onerror="alert('XSS dummy')">` akan dijalankan setiap Forum dibuka. Gunakan tombol *Reset komentar* untuk membersihkan.
3. **Percobaan sandi tanpa pembatasan**: halaman Masuk menerima percobaan sandi tanpa batas, jeda, atau penguncian akun.

## Perbaikan yang seharusnya
- IDOR: cek otorisasi di server (id yang diminta harus milik sesi pengguna).
- Stored XSS: escape output, validasi input, Content-Security-Policy.
- Brute force: rate limiting, penguncian sementara, CAPTCHA, sandi kuat, MFA.

## Cara menjalankan
Buka `index.html` di browser, atau kunjungi alamat Netlify proyek ini.

> Hanya untuk pembelajaran. Jangan memasukkan data pribadi atau sandi asli.
