# Pertemuan 5 — Studi Kasus Landing Page “Toko Sabun” (Part 1)
Pada pertemuan ini kamu akan membangun **3 bagian pertama** dari landing page menggunakan Tailwind:

1. **Top Bar (Menu)**
2. **Jumbotron (Hero)**
3. **About Brand (Tentang Brand)**

> Catatan: Modul ini dibuat **step-by-step**. Jangan copy semua kode agar kalian mengerti. Ikuti urutan langkahnya.

---

## Persiapan File  
  
Buka `index.html`. Pastikan `<body>` sudah seperti ini (boleh kamu samakan dulu):  

```html
<body class="bg-slate-50 text-slate-800">
  <!-- NANTI KITA ISI SECTION DI SINI -->
</body>
```

---

## 1. TOP BAR (Menu)

### Langkah 1 — Buat wrapper Top Bar
Tambahkan ini tepat di dalam `<body>`:

```html
<!-- TOP BAR -->
<div class="w-full bg-emerald-950 text-emerald-50">
  <!-- isi di langkah berikutnya -->
</div>
```

✅ Cek:
- Background atas jadi hijau gelap (emerald).

---

### Langkah 2 — Buat container + layout flex
Isi wrapper Top Bar jadi seperti ini:

```html
<!-- TOP BAR -->
<div class="w-full bg-emerald-950 text-emerald-50">
  <div class="w-[1100px] mx-auto flex items-center justify-between py-3">
    <!-- LEFT -->
    <div>LEFT</div>

    <!-- RIGHT -->
    <div>RIGHT</div>
  </div>
</div>
```

✅ Cek:
- Ada jarak atas–bawah (py-3).
- Area tengah lebarnya tetap (1100px) dan rata tengah.

---

### Langkah 3 — Isi bagian LEFT (Logo + Nama Brand)
Ganti `LEFT` menjadi ini:

```html
<div class="flex items-center gap-3">
  <div class="w-10 h-10 rounded-xl bg-emerald-900 flex items-center justify-center ring-1 ring-emerald-700">
    <span class="font-black tracking-wider">MAC</span>
  </div>
  <div class="leading-tight">
    <p class="font-semibold">MAC • Sabun Buatan Santri</p>
    <p class="text-xs text-emerald-200">Bersih maksimal, hati tenang karena mendukung karya santri</p>
  </div>
</div>
```

✅ Cek:
- Ada kotak logo “MAC”.
- Ada 2 baris teks di sampingnya.

---

### Langkah 4 — Isi bagian RIGHT (Link menu)
Sekarang ganti `RIGHT` menjadi menu link sederhana:

```html
<div class="flex items-center gap-6 text-sm">
  <a href="#produk" class="hover:text-white">Produk</a>
  <a href="#manfaat" class="hover:text-white">Manfaat</a>
  <a href="#testimoni" class="hover:text-white">Testimoni</a>
  <a href="#kontak" class="hover:text-white">Kontak</a>
</div>
```

✅ Cek:
- Link muncul di kanan dan sejajar.

---

### Langkah 5 — Tambahkan tombol CTA “Pesan Sekarang”
Tambahkan tombol ini di akhir menu:

```html
<a href="#produk"
  class="px-4 py-2 rounded-xl bg-emerald-500 text-emerald-950 font-semibold hover:bg-emerald-400 transition">
  Pesan Sekarang
</a>
```

✅ Cek:
- Tombol warna hijau terang muncul.
- Hover terasa (warna berubah halus).

---

### Tantangan
1. Ubah teks logo “MAC” menjadi inisial kamu.
2. Ubah link “Kontak” menjadi “Admin”.
3. Ubah warna tombol CTA menjadi `bg-white/10` dan teksnya `text-white`.


---

## 2. JUMBOTRON (Hero)

### Langkah 1 — Buat section Jumbotron + container
Tambahkan setelah Top Bar:

```html
<!-- JUMBOTRON -->
<section class="w-full bg-emerald-950">
  <div class="w-275 mx-auto flex items-center justify-between py-16">
    <!-- LEFT -->
    <div class="w-155">LEFT</div>

    <!-- RIGHT -->
    <div class="w-[420px]">RIGHT</div>
  </div>
</section>
```

✅ Cek:
- Muncul area besar hijau gelap.
- Ada ruang kiri dan kanan (dua kolom).

---

### Langkah 2 — Isi LEFT: Badge info kecil
Ganti `LEFT` menjadi badge + placeholder:

```html
<div class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-white/10 ring-1 ring-white/15">
  <span class="w-2 h-2 rounded-full bg-emerald-400"></span>
  <p class="text-emerald-100 text-sm">
    Sabun buatan santri • Bersih maksimal • Harga ramah
  </p>
</div>

<!-- NANTI: judul, deskripsi, tombol -->
```

✅ Cek:
- Ada badge bulat memanjang.

---

### Langkah 3 — Isi LEFT: Judul + Deskripsi
Tambahkan tepat di bawah badge:

```html
<h1 class="mt-5 text-5xl font-extrabold tracking-tight text-white leading-[1.1]">
  Bersih Maksimal, <br />
  <span class="text-emerald-300">Hemat Setiap Hari.</span>
</h1>

<p class="mt-4 text-emerald-100 text-lg leading-relaxed">
  <span class="font-semibold text-white">MAC</span> menghadirkan sabun kebutuhan rumah tangga yang efektif,
  wangi segar, dan nyaman dipakai—sekaligus mendukung karya santri.
</p>
```

✅ Cek:
- Judul besar putih dengan highlight emerald.

---

### Langkah 4 — Isi LEFT: Tombol CTA
Tambahkan tombol:

```html
<div class="mt-7 flex items-center gap-4">
  <a href="#produk"
    class="px-6 py-3 rounded-2xl bg-emerald-500 text-emerald-950 font-bold hover:bg-emerald-400 transition">
    Lihat Produk
  </a>
  <a href="#kontak"
    class="px-6 py-3 rounded-2xl bg-white/10 text-white font-semibold ring-1 ring-white/15 hover:bg-white/15 transition">
    Hubungi Admin
  </a>
</div>
```

✅ Cek:
- Ada 2 tombol, satu hijau terang satu transparan.

---

### Langkah 5 — Isi LEFT: “Trust points” (3 kotak kecil)
Tambahkan bagian ini:

```html
<div class="mt-8 flex items-center gap-3">
  <div class="px-4 py-3 rounded-2xl bg-white/10 ring-1 ring-white/15">
    <p class="text-white font-semibold text-sm">Tidak boros</p>
    <p class="text-emerald-200 text-xs">Kental pas, busa cukup</p>
  </div>
  <div class="px-4 py-3 rounded-2xl bg-white/10 ring-1 ring-white/15">
    <p class="text-white font-semibold text-sm">Cepat bersih</p>
    <p class="text-emerald-200 text-xs">Angkat minyak & noda</p>
  </div>
  <div class="px-4 py-3 rounded-2xl bg-white/10 ring-1 ring-white/15">
    <p class="text-white font-semibold text-sm">Wangi segar</p>
    <p class="text-emerald-200 text-xs">Bikin rumah nyaman</p>
  </div>
</div>
```

✅ Cek:
- Muncul 3 kotak kecil sejajar.

---

### Langkah 6 — Isi RIGHT: Card “Promo hari ini”
Sekarang ganti `RIGHT` menjadi card promo:

```html
<div class="rounded-[28px] bg-white/10 ring-1 ring-white/15 p-7">
  <p class="text-emerald-200 text-sm font-semibold">Promo hari ini</p>
  <h3 class="mt-2 text-white text-2xl font-extrabold">Paket Hemat MAC</h3>
  <p class="mt-2 text-emerald-100 text-sm leading-relaxed">
    Stok aman untuk kebutuhan harian: cuci piring, karbol, dan cuci baju.
  </p>

  <!-- list item promo akan dibuat step berikutnya -->
</div>
```

✅ Cek:
- Muncul card transparan kanan.

---

### Langkah 7 — Isi list item promo (3 baris)
Tambahkan tepat di bawah deskripsi:

```html
<div class="mt-5 flex flex-col gap-3">
  <div class="flex items-center justify-between px-4 py-3 rounded-2xl bg-black/20 ring-1 ring-white/10">
    <div>
      <p class="text-white font-semibold text-sm">Cuci Piring 1L</p>
      <p class="text-emerald-200 text-xs">Kuat angkat minyak</p>
    </div>
    <p class="text-white font-extrabold">15K</p>
  </div>

  <div class="flex items-center justify-between px-4 py-3 rounded-2xl bg-black/20 ring-1 ring-white/10">
    <div>
      <p class="text-white font-semibold text-sm">Karbol</p>
      <p class="text-emerald-200 text-xs">Wangi segar</p>
    </div>
    <p class="text-white font-extrabold">20K</p>
  </div>

  <div class="flex items-center justify-between px-4 py-3 rounded-2xl bg-black/20 ring-1 ring-white/10">
    <div>
      <p class="text-white font-semibold text-sm">Cuci Baju 1L</p>
      <p class="text-emerald-200 text-xs">Bersih & nyaman</p>
    </div>
    <p class="text-white font-extrabold">20K</p>
  </div>
</div>
```

---

### Langkah 8 — Tambahkan tombol “Ambil Promonya” + catatan kecil
Tambahkan di bawah list:

```html
<a href="#produk"
  class="mt-6 inline-flex w-full justify-center px-6 py-3 rounded-2xl bg-emerald-500 text-emerald-950 font-bold hover:bg-emerald-400 transition">
  Ambil Promonya
</a>

<p class="mt-3 text-xs text-emerald-200">
  *Harga sesuai list produk (bisa kamu ganti jadi bundling kalau mau).
</p>
```

✅ Cek:
- Tombol full width muncul di bawah.

---

### Tantangan
1. Ubah judul hero menjadi “Sabun Rumah Tangga”.
2. Tambahkan satu trust point ke-4 (mis. “Mudah dibilas”).
3. Di card promo, ubah harga “15K” menjadi “14K” untuk diskon.

> 📸 **[SISIPKAN SCREENSHOT]**: hasil tantangan.

---

## 3. ABOUT BRAND (Tentang Brand)

### Langkah 1 — Buat section + container 2 kolom
Tambahkan setelah Jumbotron:

```html
<!-- ABOUT BRAND -->
<section id="tentang" class="w-full">
  <div class="w-[1100px] mx-auto flex items-center justify-between py-14">
    <div class="w-[520px]">LEFT</div>
    <div class="w-[520px]">RIGHT</div>
  </div>
</section>
```

✅ Cek:
- Ada area baru background putih/abu muda default body.

---

### Langkah 2 — Isi LEFT: judul + deskripsi
Ganti `LEFT` menjadi:

```html
<p class="text-emerald-900 font-bold tracking-wide">TENTANG BRAND</p>
<h2 class="text-3xl font-extrabold mt-2 text-slate-900">
  MAC — Karya Santri untuk Kebersihan Rumah Indonesia
</h2>
<p class="mt-4 text-slate-600 leading-relaxed">
  <span class="font-semibold text-slate-900">MAC</span> adalah brand sabun rumahan yang dibuat langsung oleh santri.
  Fokus kami: <span class="font-semibold">kualitas</span>, <span class="font-semibold">kebersihan</span>, dan
  <span class="font-semibold">harga ramah</span>. Setiap pembelian membantu kegiatan dan kemandirian santri.
</p>

<!-- NANTI: kartu statistik -->
```

---

### Langkah 3 — Tambahkan 3 kartu statistik
Tambahkan di bawah paragraf:

```html
<div class="mt-7 flex gap-4">
  <div class="flex-1 rounded-2xl bg-white p-5 ring-1 ring-slate-200 shadow-sm">
    <p class="text-emerald-900 font-extrabold text-2xl">100%</p>
    <p class="text-slate-600 text-sm mt-1">Dibuat oleh santri</p>
  </div>
  <div class="flex-1 rounded-2xl bg-white p-5 ring-1 ring-slate-200 shadow-sm">
    <p class="text-emerald-900 font-extrabold text-2xl">Hemat</p>
    <p class="text-slate-600 text-sm mt-1">Efektif untuk harian</p>
  </div>
  <div class="flex-1 rounded-2xl bg-white p-5 ring-1 ring-slate-200 shadow-sm">
    <p class="text-emerald-900 font-extrabold text-2xl">Segar</p>
    <p class="text-slate-600 text-sm mt-1">Aroma bersih nyaman</p>
  </div>
</div>
```

✅ Cek:
- 3 kartu kecil sejajar dengan ring dan shadow.

---

### Langkah 4 — Isi RIGHT: Card alasan repeat order
Ganti `RIGHT` menjadi:

```html
<div class="rounded-[28px] bg-emerald-950 p-7 text-emerald-50 relative overflow-hidden">
  <div class="absolute -top-10 -left-10 w-48 h-48 rounded-full bg-emerald-500/25 blur-2xl"></div>
  <div class="absolute -bottom-10 -right-10 w-48 h-48 rounded-full bg-emerald-300/20 blur-2xl"></div>

  <h3 class="text-2xl font-extrabold">Kenapa banyak yang repeat order?</h3>
  <p class="mt-3 text-emerald-100 leading-relaxed">
    Karena sabun MAC dibuat untuk benar-benar dipakai: tidak “encer”, busa pas, mudah dibilas,
    dan wanginya bikin rumah terasa lebih bersih.
  </p>

  <!-- NANTI: list alasan -->
</div>
```

✅ Cek:
- Card kanan warna gelap dengan efek blur (bulat-bulat).

---

### Langkah 5 — Buat list alasan (3 baris)
Tambahkan di bawah paragraf:

```html
<div class="mt-6 flex flex-col gap-3">
  <div class="flex items-center gap-3 px-4 py-3 rounded-2xl bg-white/10 ring-1 ring-white/15">
    <span class="w-9 h-9 rounded-xl bg-emerald-500/20 flex items-center justify-center ring-1 ring-emerald-400/30">✓</span>
    <p class="text-emerald-50"><span class="font-semibold">Standar kebersihan</span> proses produksi</p>
  </div>
  <div class="flex items-center gap-3 px-4 py-3 rounded-2xl bg-white/10 ring-1 ring-white/15">
    <span class="w-9 h-9 rounded-xl bg-emerald-500/20 flex items-center justify-center ring-1 ring-emerald-400/30">✓</span>
    <p class="text-emerald-50"><span class="font-semibold">Aman</span> untuk kebutuhan rumah tangga</p>
  </div>
  <div class="flex items-center gap-3 px-4 py-3 rounded-2xl bg-white/10 ring-1 ring-white/15">
    <span class="w-9 h-9 rounded-xl bg-emerald-500/20 flex items-center justify-center ring-1 ring-emerald-400/30">✓</span>
    <p class="text-emerald-50"><span class="font-semibold">Support santri</span> lewat setiap pembelian</p>
  </div>
</div>
```

---

### Langkah 6 — Tambahkan tombol “Lihat Produk”
Tambahkan di bawah list:

```html
<a href="#produk"
  class="mt-7 inline-flex px-6 py-3 rounded-2xl bg-emerald-500 text-emerald-950 font-bold hover:bg-emerald-400 transition">
  Lihat Produk
</a>
```

---

### Tantangan
1. Ubah salah satu kartu statistik menjadi “Teruji”.
2. Tambahkan satu alasan repeat order ke-4.
3. Ubah button menjadi `bg-white/10 text-white` agar lebih “soft”.

---

## Refleksi Singkat
Jawab 2–3 kalimat:

1. Bagian mana yang paling sulit dibuat? Kenapa?
2. Kalau kamu jadi user, tombol mana yang paling “mengundang klik”? Kenapa?
