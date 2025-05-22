# tugas-basis-data-laravel

ok jadi pertama anda perlu mendownload xampp sebagai tempat database
✅ Langkah 1: Buka Website Resmi XAMPP

    Kunjungi situs resmi XAMPP di: https://www.apachefriends.org/index.html

✅ Langkah 2: Pilih Versi XAMPP

    Di halaman utama, kamu akan melihat tombol unduh untuk berbagai sistem operasi:

        Windows

        Linux

        macOS

Klik tombol "Download" untuk Windows.

    💡 Pilih versi PHP sesuai kebutuhan. Versi terbaru biasanya sudah cukup.

✅ Langkah 3: Mulai Proses Download

    Setelah kamu klik tombol download, file instalasi akan mulai diunduh (sekitar 150-200MB).

✅ Langkah 4: Instalasi XAMPP

    Setelah file selesai diunduh, klik dua kali file .exe-nya untuk memulai instalasi.

    Klik "Yes" jika ada peringatan dari Windows (UAC).

    Ikuti langkah-langkah berikut:

        Klik "Next".

        Pilih komponen yang ingin diinstal (biarkan default saja sudah cukup).

        Pilih direktori instalasi, default-nya C:\xampp.

        Klik "Next" terus sampai muncul tombol "Install".

        Klik "Install" dan tunggu prosesnya selesai.

✅ Langkah 5: Jalankan XAMPP Control Panel

    Setelah instalasi selesai, pastikan opsi "Start Control Panel" dicentang, lalu klik "Finish".

    XAMPP Control Panel akan terbuka. Di sini kamu bisa:

        Klik Start pada Apache dan MySQL untuk menjalankan server web dan database.

✅ Langkah 6: Uji Coba Server

buka control panel aktifkan apache dan mysql, dan di pilihan apache tekan tombol "admin"
seharusnya akan terbuka tempat database myphpsql


setelah itu buat database dengan new database, namanya tergantung anda tapi ingat namanya untuk nanti 

anda perlu ini https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://getcomposer.org/download/&ved=2ahUKEwjo4f_AjreNAxUoS2cHHbGqKg0QjBB6BAgKEAE&usg=AOvVaw0hifbxuQZySOtGjSzPWfJo

setelah composer ter download perintah ini ke command prompt
composer global require laravel/installer - install laravel
laravel new my-project - membuat laravel project
php artisan serve - membuka server laravel (seharusnya dikasih host untuk membuka webpage)
composer require illuminate/database - download database dalam laravel

ok seharusnya sudah selesai konfigurasi sekarang untuk konfigurasi files

php artisan make:model User - untuk membuat file user (seharusnya sudah ada dari default jadi akan dikasih prompt bahwa file sudah ada)
php artisan migrate -  ini untuk memigrasi semua file resource ke laravel untuk di display
php artisan migrate:status - check migrasi status 

jika tidak ada error mantap lah 

sekarang masukan kode ini 
php artisan tinker

dan ini setelah di atas
User::create([
    'name' => 'John Doe',
    'email' => 'john@example.com',
    'password' => bcrypt('secret'),
]);

hidupkan server dan seharusnya sudah ada hasil

(ada beberapa hal kecil yang perlu di customize seperti di file .env dalam file project mu untuk mengubah ini
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE= nama base dalam xampp
DB_USERNAME= user xampp
DB_PASSWORD= password xampp

dan di dalam file projectmu/resources/views/user/ 
isi index.blade.php (gunakan virtual studio code untuk mengisi)
)
