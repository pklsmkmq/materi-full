# Pertemuan 2 — Jarak (Margin & Padding) dan Customisasi Tailwind CSS

## Pertanyaan Pemantik

Renungkan pertanyaan berikut sebelum mulai:

1. Saat melihat tampilan website yang “tidak enak dilihat”, biasanya masalahnya ada di mana?
2. Menurutmu, lebih penting mana: warna yang bagus atau jarak antar elemen yang rapi? Kenapa?
3. Jika desainer meminta jarak **123px**, apakah Tailwind bisa mengakomodasi permintaan tersebut?

---

## Pengantar Materi

Pada pertemuan sebelumnya, kamu sudah mengenal **text, color, dan background**.  
Pada pertemuan ini, kita akan belajar **jarak (spacing)**, karena:

> **UI yang rapi hampir selalu ditentukan oleh jarak, bukan warna.**

Selain itu, kita juga akan belajar:  
- menggunakan **custom value** seperti `m-[100px]`  
- menggunakan **warna custom** seperti `bg-[#000]`  
- mendefinisikan **warna primary / secondary** agar konsisten di seluruh project

---

## 1. Padding (jarak ke dalam elemen)

Padding memberi jarak antara **isi** dan **border** elemen.

### Contoh Dasar
```html
<div class="bg-blue-100 p-4">
  Box dengan padding 4
</div>

<div class="bg-blue-100 p-8">
  Box dengan padding 8
</div>
```

Penjelasan singkat:
- `p-4` → padding sedang
- `p-8` → padding lebih besar

---

### Padding Arah Tertentu
```html
<div class="bg-green-100 px-8 py-2">
  Padding horizontal besar, vertikal kecil
</div>
```

- `px-8` → kiri & kanan
- `py-2` → atas & bawah

---

### Tantangan Padding
1. Buat box dengan background abu-abu.
2. Beri padding kiri–kanan besar, atas–bawah kecil.
3. Ubah padding-nya sampai terlihat paling nyaman menurutmu.  

---

## 2. Margin (jarak antar elemen)

Margin memberi jarak **di luar elemen**.

### Contoh Dasar
```html
<div class="bg-red-100 p-4 mb-4">
  Box pertama
</div>

<div class="bg-red-100 p-4">
  Box kedua
</div>
```

- `mb-4` → margin bawah

---

### Margin Arah Tertentu
```html
<p class="mt-6">
  Paragraf dengan jarak atas lebih besar
</p>
```

---

### Tantangan Margin
1. Buat 3 box berjajar vertikal.
2. Atur jarak antar box agar tidak terlalu rapat dan tidak terlalu jauh.

---

Kadang kita butuh jarak **yang tidak ada di skala Tailwind**.

## 3. Custom Margin & Padding

### Contoh Custom Margin
```html
<div class="bg-yellow-100 m-[100px]">
  Margin 100px di semua sisi
</div>
```

### Contoh Custom Padding
```html
<div class="bg-yellow-100 p-[32px]">
  Padding custom 32px
</div>
```

> Catatan:  
> Gunakan custom value **hanya jika benar-benar diperlukan**.

---

### Tantangan Custom
1. Buat satu elemen dengan margin `80px`.
2. Buat satu elemen lain dengan padding `24px`.

> 📸 **[SISIPKAN SCREENSHOT]**: hasil Tantangan B1.

---


## 4. Custom Color

Tailwind mengizinkan kita memakai warna custom langsung.

```html
<div class="bg-[#000000] p-4 text-white">
  Background hitam
</div>

<div class="bg-[#22c55e] p-4 text-white">
  Background hijau custom
</div>
```

---

### Tantangan Custom Color
1. Buat box dengan background warna favoritmu (hex).
2. Pastikan teksnya tetap terbaca.

---

## 5. Warna Primary & Secondary (Konsep Desain Sistem)

Agar project rapi, kita sebaiknya **tidak menulis warna sembarangan**.

Misalnya:
- Primary → warna utama brand
- Secondary → warna pendukung

### Menambahkan Warna ke Tailwind Config

Buka file `tailwind.config.js`, lalu ubah menjadi:

```js
/** @type {import('tailwindcss').Config} */
export default {
  content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
  theme: {
    extend: {
      colors: {
        primary: "#2563eb",
        secondary: "#22c55e",
      },
    },
  },
  plugins: [],
};
```

---

### Menggunakan Warna Primary & Secondary

Setelah disimpan dan server dijalankan ulang:

```html
<button class="bg-primary px-4 py-2 text-white">
  Tombol Primary
</button>

<button class="bg-secondary px-4 py-2 text-white">
  Tombol Secondary
</button>
```

---

### Tantangan Warna Primary
1. Ubah warna `primary` menjadi warna lain.
2. Tambahkan warna `danger` (merah).
3. Gunakan warna `danger` pada tombol.

---

## Mini Proyek Pertemuan 2 — Card Produk dengan Spacing Rapi

Buat satu card produk dengan aturan:
- Gunakan **margin** dan **padding** yang rapi
- Gunakan **warna primary** untuk tombol
- Gunakan **custom spacing** minimal 1 kali

Contoh struktur awal:
```html
<div class="max-w-sm rounded-xl bg-white p-6 shadow-md">
  <h2 class="text-xl font-bold">Sabun Susu</h2>
  <p class="mt-2 text-slate-600">
    Sabun lembut untuk kulit sensitif.
  </p>
  <button class="mt-4 bg-primary px-4 py-2 text-white">
    Beli
  </button>
</div>
```

---


## Ringkasan

- Margin & padding mengatur jarak antar dan di dalam elemen
- Tailwind menyediakan skala spacing yang konsisten
- Custom value (`m-[...]`, `p-[...]`) bisa digunakan jika perlu
- Warna primary & secondary membuat desain lebih konsisten
  
---

## Tugas Refleksi Pembelajaran

Jawab dengan kalimat sendiri:

1. Kenapa jarak (spacing) sangat mempengaruhi tampilan UI?
2. Kapan sebaiknya menggunakan custom spacing?
3. Apa keuntungan memiliki warna primary & secondary?