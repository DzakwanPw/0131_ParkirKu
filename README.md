# ParkirKu

**ParkirKu: Aplikasi Reservasi dan Pencatatan Parkir Kendaraan Kampus Berbasis Android Menggunakan Jetpack Compose**

| | |
|---|---|
| Mata kuliah | Pengembangan Aplikasi Mobile (TI505) |
| Tema | Transportasi |
| Nama | Dzakwan |
| NIM | 20240140131 |
| Kelas | C |

## Deskripsi

ParkirKu adalah aplikasi Android berbasis Jetpack Compose dan arsitektur MVVM untuk membantu mahasiswa mereservasi slot parkir dan mencatat kendaraan di area kampus. Pengguna mendata kendaraan, melihat status slot (kosong, terisi, dipesan), membuat reservasi, serta melakukan check-in dan check-out dengan perhitungan durasi. Admin mengelola area dan slot parkir serta memantau reservasi. Aplikasi memakai autentikasi JWT dengan refresh token, role-based access (Admin dan Mahasiswa), Navigation Compose, REST API dengan database MySQL, 5 entitas data terhubung (User, Kendaraan, Area Parkir, Slot Parkir, Reservasi) dengan 5 fitur CRUDS, serta penyimpanan file lokal untuk foto kendaraan.

## Peran Pengguna

| Peran | Hak akses |
|---|---|
| Mahasiswa | Kelola kendaraan sendiri, melihat slot, membuat reservasi, check-in, check-out, melihat riwayat |
| Admin | Kelola area parkir, slot parkir, dan pengguna; melihat semua reservasi |

## Entitas dan Relasi

1. **User**
2. **Kendaraan** (milik User)
3. **Area Parkir**
4. **Slot Parkir** (berada di satu Area Parkir)
5. **Reservasi** (menghubungkan User, Kendaraan, dan Slot Parkir)

```
User ──< Kendaraan
User ──< Reservasi >── Kendaraan
AreaParkir ──< SlotParkir ──< Reservasi
```

## Alur Aplikasi

1. Login atau register.
2. Mahasiswa menambah kendaraan (plat, jenis, foto).
3. Mahasiswa melihat daftar area dan slot beserta statusnya.
4. Mahasiswa memesan slot: reservasi berstatus **Dipesan**, slot menjadi **Dipesan**.
5. Check-in: waktu masuk dicatat, reservasi **Aktif**, slot **Terisi**.
6. Check-out: waktu keluar dicatat, durasi dihitung, reservasi **Selesai**, slot kembali **Kosong**.
7. Pembatalan sebelum check-in: reservasi **Dibatalkan**, slot kembali **Kosong**.

Aturan utama: status slot hanya berubah mengikuti status reservasi.

## Fitur CRUDS

| Fitur | Pengguna | Pencarian |
|---|---|---|
| Kendaraan saya | Mahasiswa | plat nomor |
| Reservasi | Mahasiswa dan Admin | status atau plat |
| Area parkir | Admin | nama area |
| Slot parkir | Admin | kode slot |
| Pengguna | Admin | nama atau email |

## Teknologi (rencana)

- Kotlin, Jetpack Compose (Material 3), Navigation Compose
- Arsitektur MVVM (ViewModel, Repository)
- REST API (rencana: Node.js + Express) dengan database MySQL
- Autentikasi JWT dan refresh token
- Penyimpanan file lokal untuk foto kendaraan

## Status Fitur

- [ ] Login dan register (JWT + refresh token)
- [ ] Role-based access (Admin dan Mahasiswa)
- [ ] CRUDS Kendaraan
- [ ] CRUDS Reservasi
- [ ] CRUDS Area Parkir
- [ ] CRUDS Slot Parkir
- [ ] CRUDS Pengguna
- [ ] Check-in dan check-out dengan perhitungan durasi
- [ ] Penyimpanan file lokal (foto kendaraan)
- [ ] REST API dan database MySQL
- [ ] Validasi form dan penanganan error

## Progress Mingguan

| Minggu | Progress |
|---|---|
| 1 | Menentukan tema dan judul, mengirim form pengumpulan judul, merancang sistem (5 entitas, relasi, 5 fitur CRUDS, alur reservasi), menentukan rencana teknis, membuat repository dan README |
| 2 | _(diisi)_ |
| 3 | _(diisi)_ |
| 4 | _(diisi)_ |

## Cara Menjalankan

_(akan diisi setelah aplikasi dan API tersedia)_
