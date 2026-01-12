# Pertemuan 2 — Jarak (Margin & Padding) dan Customisasi Tailwind CSS

## Pertanyaan Pemantik

Renungkan pertanyaan berikut sebelum mulai:

1. Saat melihat tampilan website yang “tidak enak dilihat”, biasanya masalahnya ada di mana?
2. Menurutmu, lebih penting mana: warna yang bagus atau jarak antar elemen yang rapi? Kenapa?
3. Jika desainer meminta jarak **123px**, apakah Tailwind bisa mengakomodasi permintaan tersebut?

---

## Pengantar Materi

Pada pertemuan sebelumnya, kamu sudah mengenal **text, color, dan background**.

Pada pertemuan ini, fokus kita adalah:

- Mengatur **jarak (spacing)**: margin dan padding  
- Memakai **custom spacing** seperti `m-[100px]`, `px-[22px]`  
- Memakai **custom color** seperti `bg-[#000]`  
- Membuat **warna utama (primary) dan warna pendukung (secondary)** ala “design system”  
- Menambahkan **custom font (contoh: Poppins)**

> Catatan penting (Tailwind v4):  
> Di Tailwind CSS v4, kustomisasi “theme” **tidak harus** lewat `tailwind.config.js`. Sekarang ada cara **CSS-first** memakai `@theme` di file CSS.

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

## 5. Warna Primary & Secondary (Konsep Desain Sistem)

Agar project rapi, kita sebaiknya **tidak menulis warna sembarangan**.

Misalnya:  
- Primary → warna utama brand  
- Secondary → warna pendukung

### Menambahkan Warna ke Style css
  
Buka file CSS utama Tailwind kamu, misalnya `src/style.css`.

```css
@import "tailwindcss";

@theme {
  /* Color tokens (nama bebas, tapi disarankan konsisten) */
  --color-primary: #2563eb;
  --color-secondary: #22c55e;
  --color-danger: #ef4444;
}
```

Sekarang kamu bisa pakai:

```html
<button class="bg-primary text-white px-4 py-2 rounded-lg">
  Tombol Primary
</button>

<button class="bg-secondary text-white px-4 py-2 rounded-lg">
  Tombol Secondary
</button>

<button class="bg-danger text-white px-4 py-2 rounded-lg">
  Tombol Danger
</button>
```

---

## 6. Custom Font

Tambahkan import Google Fonts **di baris paling atas** file CSS kamu.
  
```css
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap");
@import "tailwindcss";

@theme {
  --font-poppins: "Poppins", sans-serif;

  --color-primary: #2563eb;
  --color-secondary: #22c55e;
  --color-danger: #ef4444;
}
```
   
Sekarang cukup pakai class `font-poppins` di elemen atau di body.
  
```html
<body class="font-poppins">
  ...
</body>
```
  
---

## 7. Studi Kasus

### A. Siapkan Section Container

Buat file baru `custom.html` lalu masukkan pada body section dengan background lembut dan padding yang rapi:  

```html
<section class="bg-slate-50 py-10">
  <div class="mx-auto max-w-6xl px-6">
    <!-- isi card akan ditaruh di sini -->
  </div>
</section>
```

---

### B. Buat Judul Section

```html
<h2 class="text-2xl font-semibold text-slate-900">
  Produk pilihan
</h2>

<p class="mt-2 max-w-2xl text-slate-600">
  Pilih produk terbaik dengan desain kartu yang rapi menggunakan spacing dan custom theme.
</p>
```

---

### C. Buat Grid Card

```html
<div class="mt-8 grid gap-6 md:grid-cols-3">
  <!-- Card 1 -->
  <!-- Card 2 -->
  <!-- Card 3 -->
</div>
```

---

### D. Buat Card Template
  
Mulai dari card paling sederhana:  

```html
<article class="rounded-2xl bg-white p-6 shadow-sm ring-1 ring-slate-200">
  <p class="text-sm font-medium text-primary">
    Produk pilihan
  </p>

  <h3 class="mt-1 text-xl font-semibold text-slate-900">
    Custom PC Akatsuki
  </h3>

  <!-- gambar -->
  <div class="mt-4 overflow-hidden rounded-xl">
    <!-- 📸 Ganti src sesuai gambar kamu -->
    <img
      src="https://i.ytimg.com/vi/dyWJohxjNFk/maxresdefault.jpg"
      alt="PC Akatsuki"
      class="h-40 w-full object-cover"
    />
  </div>

  <p class="mt-4 text-slate-600">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Impedit sint odio fuga delectus consequuntur velit.
  </p>

  <p class="mt-4 text-xl font-semibold text-slate-900">
    Rp. 50.000.000
  </p>

  <div class="mt-6 flex gap-3">
    <button class="rounded-lg bg-primary px-4 py-2 text-white">
      Beli
    </button>

    <button class="rounded-lg border border-slate-300 px-4 py-2 text-slate-700">
      Detail
    </button>
  </div>
</article>
```

### E. Buat 3 Card dengan Warna Berbeda

Card kedua bisa punya background halus:

```html
<article class="rounded-2xl bg-emerald-50 p-6 shadow-sm ring-1 ring-emerald-100">
  ...
  <p class="text-sm font-medium text-secondary">Produk pilihan</p>
  ...
  <button class="rounded-lg bg-secondary px-4 py-2 text-white">Beli</button>
</article>
```

Card ketiga bisa pakai aksen “danger” untuk tombol beli:

```html
<button class="rounded-lg bg-danger px-4 py-2 text-white">
  Beli
</button>
```
  
---

## Tugas

Buat tampilan seperti ini:

1. Saat hover card, card “naik” sedikit dan shadow lebih tebal.  
   (Kamu boleh cari keyword: `hover:`, `transition`, `duration`, `ease`)

2. Tombol “Beli” harus punya efek hover lebih gelap.  
   (Hint: `hover:bg-...` atau gunakan warna custom yang kamu tambahkan)

3. Buat badge kecil di pojok kanan atas card (mis. `-20%`).  
   (Hint: butuh `relative` dan `absolute`)

> Kamu boleh tanya ke Google / dokumentasi Tailwind untuk menyelesaikannya.  
> Ini latihan “real world”: requirement datang duluan, tekniknya kita cari belakangan.

---