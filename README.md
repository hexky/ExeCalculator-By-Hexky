# ExeRevers Calculator

Kalkulator valuasi akun Mobile Legends: Bang Bang. Pengguna mengisi data rank, koleksi skin, dan item langka, lalu sistem menghitung estimasi harga akun berdasarkan Poin Koleksi dan riset pasar FJB.

Dibuat oleh **Hexky**.

---

## Fitur

**Kalkulator Valuasi**
Hitung estimasi harga akun dari rank saat ini, rank historis, win rate, total match, emblem max, koleksi skin per tier, recall limited, dan border limited. Hasil keluar dalam bentuk harga, range pasar, grade, dan breakdown per komponen. Setiap perubahan input langsung memperbarui estimasi tanpa perlu submit.

**Animasi Hasil**
Proses hitung menampilkan animasi bertahap: loading, checklist komponen, lalu angka final yang berjalan naik. Bisa dilewati kapan saja.

**Komentar dan Feedback**
Pengguna yang login bisa mengirim masukan dengan rating akurasi. Ada validasi otomatis untuk memblokir link, nomor telepon, dan kata promosi. Ada jeda 24 jam antar pengiriman per akun.

**Sistem Akun**
Login lewat Google. Setelah login pertama, pengguna memilih username unik. Username dipakai untuk komentar publik.

**Panel Admin**
Console teks untuk owner dan staff. Bisa ban, unban, cek user, cari user, kirim announcement, dan hapus komentar.

---

## Sistem Data

Data disimpan di Firebase Realtime Database dengan struktur sebagai berikut.

`users/{uid}` menyimpan profil pengguna: username, email, status ban, role owner/staff, dan timestamp feedback terakhir.

`usernames/{username}` memetakan username ke UID untuk cek duplikat dan pencarian.

`data/feedback` menyimpan semua komentar. Tiap entri punya pengirim, waktu, teks, rating, dan UID.

`data/announcement` menyimpan teks pengumuman yang tampil di halaman utama.

Konfigurasi Firebase di file `html` sengaja dikosongkan. Isi dengan kredensial project milikmu sebelum menjalankan.

---

## Struktur Project

Project ini satu file HTML mandiri. CSS dan JavaScript ditulis langsung di dalam `1 file html`.
