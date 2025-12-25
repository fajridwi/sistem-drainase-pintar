<<<<<<< HEAD
# Sistem Drainase Pintar

<p align="justify">
Sistem Pemantauan dan Pelaporan Banjir merupakan aplikasi berbasis web yang dikembangkan menggunakan framework Laravel dengan tujuan untuk mendukung proses pelaporan, pemantauan, dan penanganan kejadian banjir atau genangan air secara terintegrasi. Aplikasi ini dirancang sebagai media penghubung antara masyarakat dan pemerintah dalam upaya meningkatkan kecepatan, ketepatan, serta transparansi penanganan banjir di suatu wilayah.
</p>

<p align="justify">
Melalui aplikasi ini, masyarakat dapat dengan mudah melaporkan kejadian banjir yang terjadi di lingkungan sekitar dengan mengisi informasi yang relevan, seperti lokasi kejadian, kondisi genangan, dan keterangan tambahan. Laporan yang dikirimkan akan tersimpan dalam sistem dan dapat langsung diakses oleh pihak pemerintah atau petugas terkait untuk dilakukan pemantauan dan tindak lanjut.
</p>

<p align="justify">
Di sisi pemerintah, aplikasi ini menyediakan dashboard monitoring yang menampilkan daftar laporan banjir secara terstruktur, lengkap dengan status penanganan yang dapat diperbarui sesuai dengan progres di lapangan. Fitur ini membantu petugas dalam mengelola laporan masuk, menentukan prioritas penanganan, serta memantau kondisi wilayah terdampak secara lebih efektif.
</p>

<p align="justify">
Selain itu, sistem ini juga dilengkapi dengan fitur komunikasi antara masyarakat dan pihak pemerintah, sehingga memungkinkan terjadinya interaksi dua arah. Melalui fitur tersebut, masyarakat dapat memperoleh informasi terkait status laporan yang telah dikirimkan, sementara pemerintah dapat memberikan tanggapan, klarifikasi, atau informasi lanjutan secara langsung melalui sistem.
</p>

<p align="justify">
Aplikasi ini dirancang dengan konsep role-based access, di mana setiap pengguna memiliki hak akses yang berbeda sesuai dengan perannya, seperti masyarakat, pemerintah, dan admin. Dengan penerapan autentikasi pengguna, keamanan data laporan dapat terjaga dengan baik, serta setiap aktivitas pengguna dapat dikelola secara terstruktur.
</p>

<p align="justify">
Dengan adanya Sistem Pemantauan dan Pelaporan Banjir ini, diharapkan proses pelaporan dan penanganan banjir dapat dilakukan secara lebih cepat, terorganisir, dan transparan, serta mampu mendukung pengambilan keputusan oleh pihak pemerintah berdasarkan data laporan yang terkumpul. Aplikasi ini juga diharapkan dapat meningkatkan partisipasi masyarakat dalam upaya mitigasi bencana banjir melalui pemanfaatan teknologi informasi berbasis web.
</p>


## Anggota Kelompok
| Nama | NIM |
|------|------|
| Khusnia Fitri | 1203230030 |
| Ahmad Assyifa Dzaky Rahman | 1203230058 |
| Muhammad Fajri Dwi Prasetya Subandi | 1203230076 |


## Daftar Isi
1. [Fitur Aplikasi](#fitur-aplikasi)
2. [Prasyarat](#prasyarat)
3. [Instalasi](#instalasi)
4. [Struktur Proyek](#struktur-proyek)
5. [Menjalankan Aplikasi](#menjalankan-aplikasi)


## Fitur Aplikasi
Berdasarkan ide dan proposal tugas besar, aplikasi ini menyediakan fitur-fitur berikut:

### Autentikasi dan Otorisasi
- Login dan registrasi pengguna
- Role-based access control:
  - Masyarakat
  - Pemerintah
- Pengelolaan sesi pengguna secara aman

### Pelaporan Banjir
- Masyarakat dapat melaporkan kejadian banjir atau genangan air
- Laporan berisi informasi lokasi, deskripsi kejadian, dan waktu pelaporan
- Data laporan tersimpan di sistem dan dapat dipantau oleh petugas

### Pemantauan dan Status Laporan
- Pemerintah dapat melihat seluruh laporan yang masuk
- Update status laporan sesuai progres penanganan
- Monitoring laporan melalui dashboard

### Komunikasi
- Fitur komunikasi antara masyarakat dan pemerintah
- Memberikan tanggapan atau klarifikasi terhadap laporan
- Mendukung interaksi dua arah melalui sistem

### Dashboard Monitoring
- Dashboard ringkasan kondisi banjir
- Menampilkan data laporan secara terstruktur
- Mendukung pengambilan keputusan oleh petugas


## Prasyarat
Untuk menjalankan aplikasi ini, diperlukan perangkat lunak berikut:

### Backend
- PHP 8.1 atau lebih tinggi
- Composer
- Framework Laravel

### Database
- SQLite (default)
- MySQL (opsional)

### Frontend
- Node.js versi 16 atau lebih tinggi
- NPM

### Tools Pendukung
- Git
- Visual Studio Code (disarankan)

### Sistem Operasi
- Windows / Linux / macOS


## Instalasi
1. Clone Repository
   ```bash
   git clone https://github.com/username/sistem-pemantauan-banjir.git
   cd sistem-pemantauan-banjir
   ```
2. Install Dependency Backend
   ```bash
   composer install
   ```
3. Konfigurasi Environment
   ```bash
   copy .env.example .env
   php artisan key:generate
   ```
4. Konfigurasi Database (SQLite)
   Buat file database:
   ```bash
   type nul > database\database.sqlite
   ```
   Lalu jalankan migrasi:
   ```bash
   php artisan migrate
   ```

5. Install Dependency Frontend
   ```bash
   npm install
   ```

## Struktur Proyek
```
sistem-pemantauan-banjir-main/
├── .editorconfig
├── .env.example
├── .gitattributes
├── .gitignore
├── README.md
├── artisan
├── composer.json
├── composer.lock
├── package.json
├── package-lock.json
├── vite.config.js
│
├── app/
│   ├── Events/
│   │   └── NewReportNotification.php
│   │
│   ├── Http/
│   │   ├── Controllers/
│   │   │   ├── AdminReportController.php
│   │   │   ├── ConversationController.php
│   │   │   ├── DashboardController.php
│   │   │   ├── FloodMonitoringController.php
│   │   │   ├── MessageController.php
│   │   │   ├── ProfileController.php
│   │   │   ├── ReportController.php
│   │   │   ├── ReportStatusController.php
│   │   │   └── Auth/
│   │   │       ├── AuthenticatedSessionController.php
│   │   │       ├── ConfirmablePasswordController.php
│   │   │       ├── EmailVerificationNotificationController.php
│   │   │       ├── EmailVerificationPromptController.php
│   │   │       ├── NewPasswordController.php
│   │   │       ├── PasswordController.php
│   │   │       ├── PasswordResetLinkController.php
│   │   │       ├── RegisteredUserController.php
│   │   │       └── VerifyEmailController.php
│   │   │
│   │   └── Middleware/
│   │
│   ├── Models/
│   │   ├── Conversation.php
│   │   ├── FloodMonitoring.php
│   │   ├── Message.php
│   │   ├── Report.php
│   │   ├── ReportStatus.php
│   │   └── User.php
│   │
│   └── Providers/
│
├── bootstrap/
│   └── app.php
│
├── config/
│   ├── app.php
│   ├── auth.php
│   ├── cache.php
│   ├── database.php
│   ├── filesystems.php
│   ├── mail.php
│   ├── queue.php
│   └── session.php
│
├── database/
│   ├── factories/
│   ├── migrations/
│   └── seeders/
│
├── public/
│   └── index.php
│
├── resources/
│   ├── css/
│   ├── js/
│   └── views/
│       ├── admin/
│       ├── auth/
│       ├── layouts/
│       ├── masyarakat/
│       └── pemerintah/
│
├── routes/
│   ├── web.php
│   ├── api.php
│   └── auth.php
│
├── storage/
│   ├── app/
│   ├── framework/
│   └── logs/
│
└── tests/
    ├── Feature/
    │   ├── DashboardTest.php
    │   ├── FloodMonitoringMasyarakatTest.php
    │   ├── FloodMonitoringPemerintahTest.php
    │   ├── LoginTest.php
    │   ├── RegisterTest.php
    │   ├── ReportTest.php
    │   └── ReportStatusTest.php
    └── Unit/
        └── ExampleTest.php
```

## Menjalankan Aplikasi
Aplikasi dijalankan menggunakan dua terminal:

Terminal 1 – Backend
```bash
php artisan serve
```

Terminal 2 – Frontend
```bash
npm run dev
```

Akses aplikasi melalui browser:
```bash
http://127.0.0.1:8000
```
=======
<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework. You can also check out [Laravel Learn](https://laravel.com/learn), where you will be guided through building a modern Laravel application.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains thousands of video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the [Laravel Partners program](https://partners.laravel.com).

### Premium Partners

- **[Vehikl](https://vehikl.com)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel)**
- **[DevSquad](https://devsquad.com/hire-laravel-developers)**
- **[Redberry](https://redberry.international/laravel-development)**
- **[Active Logic](https://activelogic.com)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
>>>>>>> cee3f63 (first commit)
