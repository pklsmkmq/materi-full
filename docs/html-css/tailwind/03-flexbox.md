# Pertemuan 3 — Flexbox dengan Tailwind CSS

## Pertanyaan Pemantik

Jawab dan diskusikan sebelum mulai praktik:

1. Pernahkah kamu kesulitan membuat elemen sejajar kiri–kanan?
2. Menurutmu, kenapa layout website modern jarang memakai `float`?
3. Jika kamu ingin membuat navbar, layout apa yang paling cocok?

---

## Pengantar Singkat

Flexbox adalah teknik layout untuk mengatur **posisi dan jarak elemen dalam satu arah**  
(horizontal **atau** vertikal).

Di Tailwind, Flexbox sangat sering digunakan karena:  
- class-nya singkat  
- mudah dibaca  
- cocok untuk navbar, card, dan section landing page

---

## 1. Dasar Flexbox

### Mengaktifkan Flex

```html
<div class="flex bg-slate-100 p-4">
  <div class="bg-blue-200 p-2">Item 1</div>
  <div class="bg-blue-300 p-2">Item 2</div>
</div>
```

Penjelasan:
- `flex` → mengaktifkan flexbox
- item otomatis berjajar **horizontal**

---

#### Praktik
1. Tambahkan 1 item lagi (Item 3)
2. Ubah warna background tiap item
3. Perhatikan perubahan susunannya

---

### Arah Flex (`flex-row` & `flex-col`)

```html
<div class="flex flex-col bg-slate-100 p-4">
  <div class="bg-green-200 p-2">Atas</div>
  <div class="bg-green-300 p-2">Tengah</div>
  <div class="bg-green-400 p-2">Bawah</div>
</div>
```

- `flex-row` → default (kiri ke kanan)
- `flex-col` → atas ke bawah

---

#### Praktik
1. Ubah `flex-col` menjadi `flex-row`
2. Amati perbedaannya
3. Kembalikan ke susunan yang menurutmu paling cocok

---

## 2. Perataan Elemen (Align & Justify)

### Justify Content (arah utama)

```html
<div class="flex justify-between bg-yellow-100 p-4">
  <div class="bg-yellow-300 p-2">Kiri</div>
  <div class="bg-yellow-300 p-2">Tengah</div>
  <div class="bg-yellow-300 p-2">Kanan</div>
</div>
```

Contoh nilai:  
- `justify-start`  
- `justify-center`  
- `justify-between`  
- `justify-around`

---

#### Praktik
1. Coba semua nilai `justify-*`
2. Pilih yang paling cocok untuk navbar
3. Catat alasanmu

---

## 3. Align Items (arah silang)

```html
<div class="flex items-center bg-purple-100 p-4 h-32">
  <div class="bg-purple-300 p-2">Item A</div>
  <div class="bg-purple-300 p-2">Item B</div>
</div>
```

- `items-start`  
- `items-center`  
- `items-end`

---

#### Praktik
1. Ubah nilai `items-*`
2. Perhatikan posisi vertikal item
3. Pilih yang paling rapi menurutmu

---

## 4. Jarak antar Elemen

### Gap (jarak otomatis)

```html
<div class="flex gap-4 bg-slate-200 p-4">
  <div class="bg-slate-400 p-2">A</div>
  <div class="bg-slate-400 p-2">B</div>
  <div class="bg-slate-400 p-2">C</div>
</div>
```

- `gap-2`, `gap-4`, `gap-8`

---

### Praktik
1. Ubah nilai `gap`
2. Bandingkan dengan margin manual
3. Tentukan mana yang lebih praktis

> 📸 **[SISIPKAN SCREENSHOT]**: hasil Praktik C1.

---

## TUGAS PRAKTIK UTAMA

### Tugas Praktik 1 — Navbar Sederhana

Buat **navbar** dengan ketentuan:
- Logo di kiri
- Menu di kanan
- Gunakan flexbox
- Jarak antar menu rapi

Struktur awal (boleh dimodifikasi):
```html
<nav class="flex items-center justify-between bg-white p-4 shadow">
  <div class="text-xl font-bold text-primary">Toko Sabun</div>
  <ul class="flex gap-4">
    <li>Home</li>
    <li>Produk</li>
    <li>Kontak</li>
  </ul>
</nav>
```

---

### Tugas Praktik 2 — Card Produk Horizontal

Buat card produk **horizontal** (gambar di kiri, teks di kanan).

```html
<div class="flex items-center gap-4 rounded-xl bg-white p-4 shadow">
  <div class="h-24 w-24 bg-slate-300"></div>
  <div>
    <h3 class="text-lg font-bold">Sabun Herbal</h3>
    <p class="text-slate-600">
      Sabun alami dengan aroma segar.
    </p>
    <button class="mt-2 bg-primary px-3 py-1 text-white">
      Beli
    </button>
  </div>
</div>
```

---

### Tugas Praktik 3 — Section Landing Page

Buat satu section landing page:
- Teks di kiri
- Gambar/placeholder di kanan
- Gunakan flexbox

```html
<section class="flex gap-6 bg-slate-100 p-8">
  <div class="flex-1">
    <h2 class="text-2xl font-bold">Sabun Alami</h2>
    <p class="mt-2 text-slate-600">
      Dibuat dari bahan alami untuk perawatan kulit sehari-hari.
    </p>
  </div>
  <div class="flex-1 h-40 bg-slate-300"></div>
</section>
```

---

## Ringkasan

- Flexbox mengatur layout satu arah
- `flex`, `justify-*`, `items-*`, dan `gap` adalah class inti
- Flexbox sangat cocok untuk navbar, card, dan section
- Praktik langsung mempercepat pemahaman