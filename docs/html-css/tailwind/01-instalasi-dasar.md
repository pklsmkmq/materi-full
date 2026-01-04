# Pertemuan 1 — Instalasi & Dasar Tailwind CSS

## Tujuan Pembelajaran
Setelah mempelajari modul ini, peserta didik mampu:  
- Memahami konsep dasar Tailwind CSS  
- Menjalankan project Tailwind CSS menggunakan Vite  
- Menggunakan class Tailwind dasar untuk styling sederhana  
- Menyadari perbedaan pendekatan CSS konvensional dan Tailwind

## Pertanyaan Pemantik
Sebelum mulai, jawab singkat (diskusi boleh):

1. Saat membuat tampilan website, bagian mana yang paling sering kamu tulis di CSS?
2. Menurutmu, apa yang terjadi jika satu website memiliki ratusan file CSS?
3. Apakah mungkin styling website dilakukan **tanpa menulis CSS dari nol**?
4. Jika styling bisa dilakukan langsung di HTML, apa kelebihan dan kekurangannya?

> jawaban pemantik ditulis dibuku / cari diinternet.

---

## Apa itu Tailwind CSS?

Tailwind CSS adalah framework CSS yang menyediakan **class siap pakai** untuk mengatur tampilan website.  
Berbeda dengan CSS biasa yang menulis aturan di file `.css`, Tailwind mendorong kita untuk **menulis styling langsung di HTML**.

### Contoh Perbandingan

**CSS biasa**
```css
.title {
  font-size: 24px;
  font-weight: bold;
  color: blue;
}
```

```html
<h1 class="title">Judul</h1>
```

**Tailwind CSS**
```html
<h1 class="text-2xl font-bold text-blue-600">
  Judul
</h1>
```
  
👉 Dengan Tailwind:  
- Tidak perlu membuat class baru  
- Styling langsung terlihat  
- Ukuran, warna, dan jarak konsisten

---
  

## Persiapan Alat

Pastikan perangkat sudah memiliki:  
- **Node.js (LTS)**  
- **VS Code**  
- **Terminal**  

Cek Node dan npm:

```bash
node -v
npm -v
```

> ![node & npm](https://bemysmk.smkmadinatulquran.sch.id/file-1767107925599.JPEG)  
> Tampilan terminal saat `node -v` dan `npm -v` berhasil.

---

## Instalasi Tailwind CSS (mengikuti dokumentasi terbaru: Using Vite)

Modul ini memakai Vite agar workflow-nya modern (seperti di industri) dan tetap bisa menulis **HTML biasa**.

### 1) Buat project Vite (vanilla)
Jalankan perintah berikut:

```bash
npm create vite@latest tailwind-belajar -- --template vanilla
cd tailwind-belajar
npm install
```

> ![](https://bemysmk.smkmadinatulquran.sch.id/file-1767108262587.JPEG)  
> folder project berhasil dibuat + proses `npm install`.

### 2) Install Tailwind CSS + plugin Vite (versi terbaru)
Jalankan:

```bash
npm install tailwindcss @tailwindcss/vite
```

Tailwind versi terbaru merekomendasikan memakai plugin Vite ini agar integrasinya lebih mulus. 

> ![](https://bemysmk.smkmadinatulquran.sch.id/file-1767108405640.JPEG)  
> terminal setelah install sukses (tanpa error).

### 3) Tambahkan plugin Tailwind ke `vite.config.js`
Buat file `vite.config.js`, lalu masukkan kode dibawah ini:

```js
import { defineConfig } from "vite";
import tailwindcss from "@tailwindcss/vite";

export default defineConfig({
  plugins: [tailwindcss()],
});
```

Ini sesuai langkah “Configure the Vite plugin” pada dokumentasi resmi. 
  
### 4) Import Tailwind (cukup 1 baris @import yang baru)
Buka `src/style.css`, **hapus isinya**, lalu isi menjadi:

```css
@import "tailwindcss";
```

Tailwind versi terbaru menggunakan **satu baris import** ini. 

### 5) Pastikan CSS sudah diload di HTML
Buka `index.html`, pastikan ada baris seperti ini di `<head>`:

```html
<link href="/src/style.css" rel="stylesheet" />
```

Contoh ini juga ada di dokumentasi resmi. 

### 6) Jalankan project
```bash
npm run dev
```

> Buka link yang muncul (biasanya `http://localhost:5173`).

---

## Tes Tailwind Berjalan
Buka `index.html`, cari isi `<body>`, lalu ganti menjadi:

```html
<body class="bg-blue-800">
</body>
```

---

# Dasar Tailwind: Text, Color, Background (contoh diperbanyak)

> Prinsip belajar di pertemuan 1: **lihat → coba → ubah → simpulkan**.

## A) Text (Ukuran, Tebal, Rata, dan Dekorasi)

### Contoh 1 — Ukuran & ketebalan
```html
<h2 class="text-xl font-semibold">Belajar Tailwind</h2>
<p class="text-sm">Belajar Tailwind Dengan Mudah Dan Menyenangkan</p>
```
Penjelasan singkat:
- `text-xl` = ukuran teks lebih besar
- `font-semibold` = tebal sedang
- `text-sm` = teks kecil

**Tantangan A1**
- Ubah `text-xl` menjadi ukuran lebih besar.
- Ubah `font-semibold` menjadi lebih tebal.

---

### Contoh 2 — Rata teks & jarak antar baris
```html
<p class="text-base leading-relaxed text-slate-700">
  Ini paragraf yang nyaman dibaca karena jarak antar barisnya lebih longgar.
</p>
<p class="text-base leading-tight text-slate-700">
  Ini paragraf yang lebih rapat.
</p>
```

**Tantangan A2**
- Mana yang lebih enak dibaca? Jelaskan 1 kalimat.
- Coba ganti `leading-tight` menjadi nilai lain.

---

### Contoh 3 — Dekorasi teks
```html
<a class="text-blue-600 underline hover:no-underline" href="#">
  Link dengan underline
</a>
```

**Tantangan A3**
- Buat link menjadi warna berbeda saat hover (gunakan class `hover:text-...`).

---

## B) Color (Warna teks dan warna elemen)

### Contoh 1 — Warna teks
```html
<p class="text-red-600">Ini teks merah.</p>
<p class="text-green-600">Ini teks hijau.</p>
<p class="text-slate-600">Ini teks abu-abu.</p>
```

**Tantangan B1**
- Buat 3 teks lain dengan warna berbeda.
- Pilih 1 warna yang menurutmu cocok untuk “info”, “sukses”, “bahaya”.

---

### Contoh 2 — Warna border
```html
<div class="rounded-lg border border-slate-300 p-4">
  Box dengan border abu-abu
</div>

<div class="rounded-lg border border-blue-300 p-4">
  Box dengan border biru muda
</div>
```

**Tantangan B2**
- Ganti border box kedua menjadi “lebih tegas” (coba angka lain: 500/600).

---

## C) Background (Latar belakang)

### Contoh 1 — Background sederhana
```html
<div class="rounded-lg bg-white p-4 shadow">
  Background putih + bayangan
</div>

<div class="rounded-lg bg-blue-50 p-4">
  Background biru muda
</div>
```

**Tantangan C1**
- Buat 1 box dengan background “kuning muda” untuk peringatan.
- Tambahkan teks yang warnanya tetap terbaca.

---

### Contoh 2 — Kombinasi background + text + padding
```html
<div class="rounded-lg bg-emerald-600 p-4 text-white">
  <h3 class="text-lg font-bold">Sukses!</h3>
  <p class="text-white/90">Data berhasil disimpan.</p>
</div>
```

**Tantangan C2**
- Buat versi “gagal/error” dengan warna merah.
- Buat versi “info” dengan warna biru.

---

# Mini Proyek Pertemuan 1: Kartu Produk “Toko Sabun”

Sekarang kita gabungkan text + color + background jadi 1 komponen.

Copy - paste ini ke dalam `<section>` yang sebelumnya berisi “Hello Tailwind!”, atau ganti seluruh isi `<section>`:

```html
<section class="w-full max-w-md rounded-xl bg-white p-6 shadow-md">
  <div class="rounded-lg bg-blue-50 p-4">
    <p class="text-sm font-semibold text-blue-700">Produk Pilihan</p>
    <h2 class="mt-1 text-2xl font-bold text-slate-900">Sabun Herbal</h2>
    <p class="mt-2 text-slate-700">
      Sabun wangi dengan bahan alami. Cocok untuk kulit sensitif dan penggunaan harian.
    </p>

    <div class="mt-4 flex gap-2">
      <button class="rounded-lg bg-blue-600 px-4 py-2 text-white hover:bg-blue-700">
        Beli
      </button>
      <button class="rounded-lg border border-blue-600 px-4 py-2 text-blue-600 hover:bg-blue-50">
        Detail
      </button>
    </div>
  </div>
</section>
```

---

## Tantangan (Setelah Penjelasan)
Kerjakan 4 tantangan ini:

1. Ubah nama produk sabun masing - masing.
2. Ubah background kartu menjadi `bg-amber-50` (atau warna lain yang kamu suka).
3. Ubah tombol “Beli” menjadi warna hijau / yang kamu suka.
4. Tambahkan teks kecil harga, misalnya: “Rp 15.000”, warnanya abu-abu / yang kamu suka.

---
  
## Ringkasan
- Instalasi Tailwind versi terbaru di Vite menggunakan plugin `@tailwindcss/vite` dan `@import "tailwindcss";` di CSS. 
- Tailwind memudahkan styling dengan class utility.
- Pertemuan ini fokus pada: **text, color, background** + latihan komponen sederhana.
  
---
  
## Tugas Refleksi Pembelajaran
Jawab dengan kalimatmu sendiri (boleh singkat, tapi jelas):

1. Apa perbedaan cara styling antara CSS biasa dan Tailwind?
2. Dari materi hari ini, class Tailwind apa yang paling sering kamu pakai? Kenapa?
3. Menurutmu, kapan Tailwind membuat kerja lebih cepat? Kapan justru membuat bingung?