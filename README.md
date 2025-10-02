# docker-nginx-php-mysql

## Deskripsi
Repository ini berisi konfigurasi Docker untuk menjalankan stack **Nginx + PHP + MariaDB + phpMyAdmin** secara otomatis. Cocok untuk pengembangan aplikasi berbasis PHP.

## Struktur Folder
- `build/nginx/` : Konfigurasi Nginx
- `build/php/` : Dockerfile & konfigurasi PHP
- `htdocs/` : Folder web utama (source code PHP)
- `docker-compose.yaml` : File utama untuk menjalankan semua service

## Cara Penggunaan

### 1. Pastikan Sudah Install
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

### 2. Jalankan Project
Buka terminal di folder ini, lalu jalankan:
```sh
docker-compose up --build
```
Tunggu hingga semua service berjalan.

### 3. Akses Aplikasi
- **Web utama**: [http://localhost](http://localhost)
- **phpMyAdmin**: [http://localhost:8080](http://localhost:8080)
- **MariaDB**: Host `db`, port `3307`, user `homestead`, password `secret`, root password `root`

### 4. Struktur Web
Letakkan file PHP Anda di folder `htdocs`. Contoh file sudah tersedia: `index.php`.

### 5. Konfigurasi
- **Nginx**: Ubah konfigurasi di `build/nginx/conf.d/`
- **PHP**: Ubah konfigurasi di `build/php/php.ini`
- **Database**: Data tersimpan di volume `inventarisdb` (tidak hilang saat container dimatikan)

## Tips
- Untuk menghentikan semua service:  
  ```sh
  docker-compose down
  ```
- Untuk rebuild jika ada perubahan konfigurasi:  
  ```sh
  docker-compose up --build
  ```

## Troubleshooting
- Jika port sudah dipakai, ubah port di `docker-compose.yaml`
- Jika ada error permission, jalankan dengan hak akses administrator

---

**Selamat mencoba!**  
Jika ada pertanyaan, silakan buka issue di repository ini.
