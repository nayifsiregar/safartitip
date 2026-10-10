# SafarTitip — Website Jastip Timur Tengah & Open Bagasi

Website **landing page + formulir konsultasi WhatsApp** yang siap dihosting sebagai situs statis di **Vercel**. Tidak membutuhkan Node.js, framework, database, hosting berbayar, atau proses build.

## ⚠️ Langkah penting sebelum dipublikasikan

1. Buka `index.html` dengan editor teks (misalnya VS Code).
2. Cari `SITE_CONFIG` di bagian paling bawah file.
3. Ubah `whatsappNumber: ""` menjadi nomor admin dalam format internasional, **tanpa tanda +, spasi, atau nol di depan**.

   Misalnya jika nomor admin adalah **0812 3456 7890** (CONTOH SAJA), tulis:

   ```js
   whatsappNumber: "6281234567890",
   ```

4. Simpan dan uji formulir. Setelah nomor benar, tombol **Buat Pesan WhatsApp** akan membuka WhatsApp berisi detail konsultasi. Pengunjung tetap perlu menekan tombol *kirim* di WhatsApp.
5. Sesuaikan daftar negara, kebijakan penerimaan barang, narasi bisnis, dan status operasi apabila kebutuhan aktual berbeda. **Website sengaja tidak menampilkan tarif, jadwal, kapasitas, klaim testimoni, atau pengiriman yang belum terkonfirmasi.**

Jika nomor belum diisi, situs tetap berjalan tetapi akan menampilkan **draf pesan yang dapat disalin**, bukan berpura-pura mengirim ke admin.

## Cara upload ke Vercel

### Metode A — Melalui GitHub (paling direkomendasikan)

1. Ekstrak ZIP ini, lalu buat repository GitHub baru dan upload isi folder `SafarTitip-vercel/` ke root repository (pastikan `index.html` ada di root).
2. Masuk ke [vercel.com/new](https://vercel.com/new), lalu **Import Git Repository**.
3. Pilih repository, set **Framework Preset: Other** dan **Root Directory: `./`**. Tidak perlu menambahkan build command.
4. Klik **Deploy**. Selesai. Update berikutnya cukup melalui GitHub.

### Metode B — Melalui Vercel CLI

```sh
npm i -g vercel
cd SafarTitip-vercel
vercel --prod
```

Ikuti instruksi login dan project dari Vercel CLI. Situs akan mendapat URL `*.vercel.app`.

## Struktur berkas

```text
SafarTitip-vercel/
├── index.html                   # Seluruh HTML + CSS + JavaScript
├── vercel.json                  # Konfigurasi statis dan header
├── README.md                    # Panduan
└── assets/
    ├── favicon.svg
    ├── apple-touch-icon.png
    ├── og-cover.png
    ├── safartitip-logo.webp
    └── safartitip-logo-small.webp
```

## Fitur

- Desain premium hijau zamrud–emas, responsif di layar ponsel/tablet/laptop.
- Profil brand, katalog jastip / bagasi / oleh-oleh, cara kerja, informasi biaya, FAQ.
- Form validasi HTML5; pilihan asal/tujuan; pratinjau pengajuan langsung.
- Pesan otomatis diformat lalu dibuka melalui tautan WhatsApp admin.
- Form bekerja **tanpa database** dan **tidak menyimpan informasi pengunjung ke server**. Data yang diisi diteruskan kepada WhatsApp hanya ketika pengunjung membuka WhatsApp.
- Font diambil dari Google Fonts; ketika offline sistem menggunakan font fallback.
- Logo teroptimasi WebP, favicon dan preview Open Graph.
- Versi `SafarTitip-HTML-Satu-File.html` juga tersedia terpisah bila hanya membutuhkan satu berkas HTML. Ubah namanya menjadi `index.html` sebelum deploy.

## Penting tentang ketentuan bisnis

Penerimaan barang wajib mematuhi aturan maskapai, batas bagasi, deklarasi bea cukai, perpajakan serta perizinan impor/ekspor yang berlaku. Hindari menerima titipan yang asal, isi atau pemiliknya tidak dapat diverifikasi. Jangan menjanjikan slot atau tarif tanpa konfirmasi nyata.

## Kustomisasi

- Nama brand / slogan: cari teks `SafarTitip` di `index.html`.
- Warna: ubah CSS `:root` pada bagian atas `index.html`.
- Gambar logo: ganti `assets/safartitip-logo.webp` dengan file WebP Anda.
- Negara dan jenis layanan: edit elemen `<select>` dan kartu layanan.
- Kontak WhatsApp admin: `SITE_CONFIG.whatsappNumber`.
- Domain pribadi: tambahkan domain melalui **Vercel → Project → Settings → Domains**.

## Catatan

Website ini **bukan sistem pemrosesan pesanan otomatis**. Tidak memiliki database, dashboard admin, pelacakan bagasi, atau pembayaran online. Fungsi utamanya adalah pengenalan jasa dan penyaluran konsultasi melalui WhatsApp.
