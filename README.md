# Online Shop Laravel 12 dengan Filament 3

Aplikasi manajemen online shop sederhana yang dikembangkan menggunakan Laravel 12 dan Filament 3, dengan fokus pada pengelolaan produk dan kategori.

## Fitur Utama

-   🗂️ **Manajemen Kategori**: Tambah, edit, dan hapus kategori produk
-   📦 **Manajemen Produk**: Kelola inventaris produk dengan informasi detail
-   🔍 **Pencarian & Filter**: Temukan produk dan kategori dengan cepat
-   🔄 **Relasi Otomatis**: Relasi one-to-many antara kategori dan produk
-   🧠 **Auto-generate**: Slug dan SKU dibuat otomatis saat input data
-   💼 **Panel Admin Intuitif**: Antarmuka admin yang mudah digunakan

## Persyaratan Sistem

-   PHP 8.2 atau lebih tinggi
-   Composer
-   MySQL/PostgreSQL/SQLite
-   Node.js & NPM (untuk asset compilation)
-   Web Server (Apache/Nginx)

## Instalasi

### 1. Clone Repository

```bash
git clone https://github.com/username/online-shop-laravel.git
cd online-shop-laravel
```

### 2. Install Dependensi

```bash
composer install
npm install
```

### 3. Setup Lingkungan

```bash
cp .env.example .env
php artisan key:generate
```

Edit file `.env` untuk mengatur koneksi database:

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=online_shop
DB_USERNAME=root
DB_PASSWORD=
```

### 4. Migrasi Database & Seeding

```bash
php artisan migrate
php artisan db:seed
```

### 5. Jalankan Server Pengembangan

```bash
php artisan serve
npm run dev
```

Akses panel admin di: http://localhost:8000/admin

### 6. Buat Akun Admin

```bash
php artisan make:filament-user
```

## Struktur Database

### Tabel `categories`

-   `id` - Primary key
-   `name` - Nama kategori
-   `slug` - URL-friendly name (otomatis)
-   `description` - Deskripsi kategori (opsional)
-   `is_active` - Status kategori (aktif/nonaktif)
-   `timestamps` - Created/updated timestamps

### Tabel `products`

-   `id` - Primary key
-   `category_id` - Foreign key ke kategori
-   `name` - Nama produk
-   `slug` - URL-friendly name (otomatis)
-   `description` - Deskripsi produk (opsional)
-   `price` - Harga produk
-   `stock` - Jumlah stok tersedia
-   `sku` - Stock Keeping Unit (otomatis)
-   `is_active` - Status produk (aktif/nonaktif)
-   `timestamps` - Created/updated timestamps

## Model & Relasi

-   **Category**: Satu kategori memiliki banyak produk (`hasMany`)
-   **Product**: Satu produk termasuk dalam satu kategori (`belongsTo`)

## Penggunaan Dasar

### Mengelola Kategori

1. Login ke panel admin
2. Akses menu "Kategori" di sidebar
3. Gunakan tombol "+ Baru" untuk menambahkan kategori
4. Klik pada baris untuk mengedit atau menghapus kategori

### Mengelola Produk

1. Login ke panel admin
2. Akses menu "Produk" di sidebar
3. Gunakan tombol "+ Baru" untuk menambahkan produk
4. Pilih kategori dari dropdown atau buat baru langsung dari form
5. Klik pada baris untuk mengedit atau menghapus produk

## Pengembangan Lanjutan

Untuk menambahkan fitur baru:

-   **Gambar Produk**: Tambahkan field pada migrasi produk dan form upload di FilamentResource
-   **Variasi Produk**: Buat model dan migrasi baru untuk variasi (ukuran, warna, dll)
-   **Diskon & Promo**: Tambahkan field diskon pada tabel produk
-   **User & Autentikasi**: Gunakan fitur auth Laravel untuk front-end toko

## Kontribusi

1. Fork repository
2. Buat branch fitur (`git checkout -b feature/amazing-feature`)
3. Commit perubahan (`git commit -m 'Add some amazing feature'`)
4. Push ke branch (`git push origin feature/amazing-feature`)
5. Buat Pull Request

## Lisensi

Proyek ini dilisensikan di bawah [MIT License](LICENSE)

---

Dibuat dengan ❤️ menggunakan Laravel 12 dan Filament 3
