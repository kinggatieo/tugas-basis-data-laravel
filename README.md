# 📘 Panduan Lengkap Instalasi Laravel di Windows (dengan XAMPP)

Dokumentasi ini menjelaskan secara lengkap cara menyiapkan proyek Laravel di Windows menggunakan XAMPP, PHP, Composer, dan Laravel Installer. Fokus utama adalah penggunaan Laravel dan Eloquent ORM.

---

## 📦 Persyaratan Awal

- ✅ XAMPP (sudah termasuk PHP & MySQL)
- ✅ Composer (manajer paket untuk PHP)
- ✅ Laravel Installer (melalui Composer)
- ✅ Editor kode seperti VS Code

---

## 🔧 Langkah 1: Instalasi XAMPP

1. Unduh XAMPP di: [https://www.apachefriends.org/index.html](https://www.apachefriends.org/index.html)
2. Instal menggunakan pengaturan default.
3. Jalankan **Apache** dan **MySQL** melalui XAMPP Control Panel.
4. Cek apakah PHP tersedia:

   ```bash
   C:\xampp\php\php.exe -v

⚙️ Langkah 2: Menambahkan PHP ke PATH (User Environment Variable)

Agar perintah php bisa dikenali di Command Prompt:

    Buka Start Menu → cari: Edit environment variables for your account

    Di bagian User variables, cari Path → klik Edit

    Klik New → masukkan:

C:\xampp\php

Klik OK pada semua jendela.

Tutup dan buka kembali cmd, lalu cek:

    php -v

📥 Langkah 3: Instal Composer

    Unduh Composer di: https://getcomposer.org/download/

    Jalankan installer dan arahkan ke:
    C:\xampp\php\php.exe

    Setelah selesai, cek dengan:

    composer -V

🚀 Langkah 4: Instal Laravel

Install Laravel secara global:

composer global require laravel/installer

    Tambahkan direktori Composer ke PATH agar perintah laravel bisa dipakai:

%USERPROFILE%\AppData\Roaming\Composer\vendor\bin

Lalu uji:

laravel --version

🧪 Langkah 5: Membuat Proyek Laravel Baru

laravel new nama-proyek-anda
cd nama-proyek-anda
php artisan serve

Akses aplikasi di: http://localhost:8000
⚙️ Langkah 6: Konfigurasi Database (.env)

Edit file .env:

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=nama_database
DB_USERNAME=root
DB_PASSWORD=

    Gunakan phpMyAdmin (via http://localhost/phpmyadmin) untuk membuat database.

🧱 Langkah 7: Membuat Model, Migration, dan Controller

Contoh: membuat Post

php artisan make:model Post -mcr

Edit file migration di database/migrations/xxxx_xx_xx_create_posts_table.php:

$table->string('title');
$table->text('content');

Jalankan migration:

php artisan migrate

🧠 Contoh Penggunaan ORM Eloquent
🔹 Membuat Data

Post::create([
  'title' => 'Judul Pertama',
  'content' => 'Ini konten pertama.'
]);

🔹 Menampilkan Semua Data

$posts = Post::all();

🔹 Mengupdate Data

$post = Post::find(1);
$post->title = 'Judul Baru';
$post->save();

🔹 Menghapus Data

$post = Post::find(1);
$post->delete();

🎯 Kesimpulan

Dengan mengikuti panduan ini, kamu telah:

    Menginstal XAMPP, PHP, Composer

    Mengatur Laravel menggunakan Laravel Installer

    Membuat proyek Laravel baru

    Menghubungkan ke database

    Menggunakan Eloquent ORM untuk manipulasi data

Laravel adalah framework modern yang sangat kuat dengan sintaks yang elegan dan didukung oleh komunitas besar. Cocok untuk pengembangan aplikasi web dari skala kecil hingga besar.
✅ Rekomendasi Lanjutan

    Pelajari Eloquent Relationships (One-to-Many, Many-to-Many)

    Gunakan Laravel Tinker untuk testing via CLI

    Implementasi fitur autentikasi dengan:

    php artisan ui bootstrap --auth
    npm install && npm run dev


---

### 📌 Cara Pakai

1. Simpan file ini sebagai `README.md` di dalam folder proyek Laravel kamu
2. Buka dengan editor seperti VS Code atau tampilkan langsung di GitHub

Kalau kamu ingin ditambahkan bagian **diagram alur Eloquent**, **struktur folder Laravel**, atau contoh proyek mini seperti blog atau todo app, tinggal bilang saja!
