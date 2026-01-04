# Pertemuan 6 — Studi Kasus Landing Page “Toko Sabun” (Part 2)
Pada pertemuan ini kamu akan membangun **3 bagian berikutnya** dari landing page menggunakan Tailwind:

1. **Benefits (Manfaat)**
2. **Product Cards (Produk + Mini CTA)**
3. **Testimoni**

> Catatan: Ikuti step-by-step. Jangan copy semua sekaligus.

---

## Persiapan
Pastikan pada `index.html` kamu sudah selesai sampai **About Brand** (Pertemuan 5).  
Sekarang kita lanjut menambah 3 section berikutnya.

---

## 1. BENEFITS (Manfaat)

### Langkah 1 — Buat section + container
Tambahkan setelah About Brand:

```html
<!-- BENEFITS -->
<section id="manfaat" class="w-full bg-white">
  <div class="w-[1100px] mx-auto py-14">
    <!-- NANTI: header + cards -->
  </div>
</section>
```

✅ Cek:
- Ada blok putih baru dengan padding vertikal.

---

### Langkah 2 — Buat header (kiri judul, kanan badge)
Di dalam container, tambahkan:

```html
<div class="flex items-end justify-between">
  <div class="w-[650px]">
    <p class="text-emerald-900 font-bold tracking-wide">MANFAAT</p>
    <h2 class="text-3xl font-extrabold mt-2 text-slate-900">
      3 Manfaat Sabun Buatan Sendiri (MAC)
    </h2>
    <p class="mt-3 text-slate-600 leading-relaxed">
      Dibuat dengan perhatian lebih pada kebutuhan sehari-hari: bersih, hemat, dan nyaman digunakan.
    </p>
  </div>
  <div class="w-[360px] flex justify-end">
    <div class="px-5 py-3 rounded-2xl bg-emerald-50 ring-1 ring-emerald-100 text-emerald-900 font-semibold">
      Kualitas terasa dari pemakaian pertama
    </div>
  </div>
</div>
```

✅ Cek:
- Judul di kiri, badge di kanan.

---

### Langkah 3 — Buat 1 kartu manfaat (template)
Tambahkan di bawah header:

```html
<div class="mt-10 flex gap-6">
  <div class="flex-1 rounded-[26px] p-7 bg-slate-50 ring-1 ring-slate-200 shadow-sm">
    <div class="w-12 h-12 rounded-2xl bg-emerald-900 flex items-center justify-center">
      <!-- ICON (boleh pakai SVG / emoji) -->
      <span class="text-emerald-200 font-black">★</span>
    </div>
    <h3 class="mt-4 text-xl font-extrabold text-slate-900">Daya Bersih Maksimal</h3>
    <p class="mt-2 text-slate-600 leading-relaxed">
      Mengangkat minyak, noda, dan kotoran lebih cepat. Piring kinclong, lantai segar, baju bersih.
    </p>
  </div>

  <!-- Card 2 dan 3 dibuat di langkah berikut -->
</div>
```

✅ Cek:
- Ada 1 card manfaat.

---

### Langkah 4 — Duplikasi jadi 3 kartu manfaat
Duplikasikan card pertama menjadi total 3 card (ubah judul & isi). Contoh:

**Card 2**
- Judul: `Lebih Hemat & Efektif`
- Isi: `Kekentalan pas, busa cukup, tidak boros...`

**Card 3**
- Judul: `Rasa Tenang`
- Isi: `Kamu tidak cuma belanja—kamu ikut mendukung...`

> 📸 **[SISIPKAN SCREENSHOT]**: 3 cards manfaat selesai.

---

### Tantangan
1. Ganti ikon `★` menjadi emoji yang sesuai (mis. ⚡ 💸 ✅).
2. Ubah background card menjadi `bg-white` dan tambahkan `ring-slate-100`.

---

## 2. PRODUCT CARDS (Produk + Mini CTA)

### Langkah 1 — Buat section Produk + header
Tambahkan setelah Benefits:

```html
<!-- PRODUCT CARDS -->
<section id="produk" class="w-full">
  <div class="w-[1100px] mx-auto py-14">
    <!-- HEADER -->
    <div class="flex items-end justify-between">
      <div class="w-[700px]">
        <p class="text-emerald-900 font-bold tracking-wide">PRODUK</p>
        <h2 class="text-3xl font-extrabold mt-2 text-slate-900">
          Pilih Produk MAC yang Kamu Butuhkan
        </h2>
        <p class="mt-3 text-slate-600 leading-relaxed">
          Harga promo hari ini dengan <span class="font-semibold">coret</span> biar makin kelihatan hematnya.
        </p>
      </div>
      <div class="w-[350px] flex justify-end">
        <div class="px-5 py-3 rounded-2xl bg-emerald-950 text-emerald-50">
          <p class="text-sm font-semibold">Order cepat:</p>
          <p class="text-xs text-emerald-200">WA: 08xx-xxxx-xxxx (isi nanti)</p>
        </div>
      </div>
    </div>

    <!-- NANTI: kartu produk -->
  </div>
</section>
```

✅ Cek:
- Header produk muncul, ada kotak “Order cepat” di kanan.

---

### Langkah 2 — Buat 1 kartu produk (template)
Tambahkan setelah header:

```html
<div class="mt-10 flex gap-6">
  <!-- Product 1 -->
  <div class="flex-1 rounded-[28px] bg-white ring-1 ring-slate-200 shadow-sm overflow-hidden">
    <div class="h-44 bg-gradient-to-b from-emerald-950 to-emerald-900 p-6 flex items-start justify-between">
      <div>
        <p class="text-emerald-200 text-sm font-semibold">Best Seller</p>
        <h3 class="text-white text-2xl font-extrabold mt-1">Sabun Cuci Piring</h3>
        <p class="text-emerald-100 text-sm mt-1">Kemasan 1 Liter</p>
      </div>
      <div class="w-14 h-14 rounded-2xl bg-white/10 ring-1 ring-white/20 flex items-center justify-center">
        <span class="text-white font-black">1L</span>
      </div>
    </div>

    <div class="p-6">
      <div class="flex items-center justify-between">
        <div class="flex flex-col">
          <span class="text-slate-500 text-sm line-through">Rp 20.000</span>
          <span class="text-emerald-900 text-3xl font-extrabold">Rp 15.000</span>
        </div>
        <span class="px-4 py-2 rounded-full bg-emerald-50 text-emerald-900 font-bold ring-1 ring-emerald-100">
          Hemat 25%
        </span>
      </div>

      <ul class="mt-5 flex flex-col gap-2 text-slate-600 text-sm">
        <li class="flex items-center gap-2">
          <span class="w-2 h-2 rounded-full bg-emerald-600"></span> Ampuh angkat minyak & bau amis
        </li>
        <li class="flex items-center gap-2">
          <span class="w-2 h-2 rounded-full bg-emerald-600"></span> Busa pas, mudah dibilas
        </li>
        <li class="flex items-center gap-2">
          <span class="w-2 h-2 rounded-full bg-emerald-600"></span> Wangi segar nyaman
        </li>
      </ul>

      <a href="#kontak"
        class="mt-6 inline-flex w-full justify-center px-6 py-3 rounded-2xl bg-emerald-600 text-white font-bold hover:bg-emerald-700 transition">
        Pesan Sabun Cuci Piring
      </a>
    </div>
  </div>

  <!-- Product 2 dan 3 dibuat di langkah berikut -->
</div>
```

✅ Cek:
- Ada 1 kartu produk lengkap.

---

### Langkah 3 — Duplikasi jadi 3 kartu produk
Duplikasikan Product 1 menjadi total 3 produk, lalu ubah isi:

**Product 2**
- Label: `Aroma Segar`
- Nama: `Karbol`
- Harga promo: `Rp 20.000`

**Product 3**
- Label: `Untuk Harian`
- Nama: `Sabun Cuci Baju`
- Harga promo: `Rp 20.000`

> 📸 **[SISIPKAN SCREENSHOT]**: 3 produk sudah tampil.

---

### Langkah 4 — Tambahkan Mini CTA (di bawah kartu produk)
Tambahkan setelah `</div>` container kartu produk:

```html
<!-- Mini CTA -->
<div class="mt-10 rounded-[28px] bg-emerald-950 p-8 text-emerald-50 flex items-center justify-between relative overflow-hidden">
  <div class="absolute -top-14 -right-14 w-56 h-56 rounded-full bg-emerald-500/20 blur-2xl"></div>
  <div class="w-[720px]">
    <h3 class="text-2xl font-extrabold">Mau lebih hemat?</h3>
    <p class="mt-2 text-emerald-100">
      Ambil bundling 3 produk MAC untuk stok 1 bulan. Cocok buat rumah tangga dan warung makan.
    </p>
  </div>
  <a href="#kontak"
    class="px-6 py-3 rounded-2xl bg-emerald-500 text-emerald-950 font-bold hover:bg-emerald-400 transition">
    Konsultasi & Order
  </a>
</div>
```

✅ Cek:
- Ada banner CTA besar di bawah produk.

---

### Tantangan
1. Pada Product 1, ubah label “Best Seller” menjadi “Diskon”.
2. Pada Product 2, tambahkan satu poin bullet baru.
3. Ubah teks tombol CTA mini menjadi “Chat Admin”.

---

## 3. TESTIMONI

### Langkah 1 — Buat section Testimoni + header
Tambahkan setelah Product Cards:

```html
<!-- TESTIMONI -->
<section id="testimoni" class="w-full bg-white">
  <div class="w-[1100px] mx-auto py-14">
    <div class="flex items-end justify-between">
      <div class="w-[720px]">
        <p class="text-emerald-900 font-bold tracking-wide">TESTIMONI</p>
        <h2 class="text-3xl font-extrabold mt-2 text-slate-900">
          Mereka sudah coba MAC, sekarang giliran kamu
        </h2>
        <p class="mt-3 text-slate-600 leading-relaxed">
          Ini contoh 3 testimoni (nanti bisa kamu ganti nama/fotonya).
        </p>
      </div>
      <div class="w-[320px] flex justify-end">
        <div class="px-5 py-3 rounded-2xl bg-emerald-50 ring-1 ring-emerald-100 text-emerald-900 font-semibold">
          Rating pelanggan: ★★★★★
        </div>
      </div>
    </div>

    <!-- NANTI: kartu testimoni -->
  </div>
</section>
```

✅ Cek:
- Header testimoni muncul.

---

### Langkah 2 — Buat 1 kartu testimoni (template)
Tambahkan di bawah header:

```html
<div class="mt-10 flex gap-6">
  <div class="flex-1 rounded-[28px] bg-slate-50 ring-1 ring-slate-200 p-7 shadow-sm">
    <div class="flex items-center gap-4">
      <div class="w-14 h-14 rounded-2xl bg-emerald-950 flex items-center justify-center text-emerald-100 font-black">
        A
      </div>
      <div>
        <p class="font-extrabold text-slate-900">Ayu, Ibu Rumah Tangga</p>
        <p class="text-sm text-slate-500">Bekasi</p>
      </div>
    </div>
    <p class="mt-5 text-slate-700 leading-relaxed">
      “Cuci piringnya enak banget dipakai, minyak cepat hilang dan nggak bikin boros.
      Wanginya juga bersih. Repeat order sih!”
    </p>
    <div class="mt-5 text-emerald-900 font-bold">★★★★★</div>
  </div>

  <!-- Card 2 dan 3 dibuat di langkah berikut -->
</div>
```

✅ Cek:
- Muncul 1 card testimoni.

---

### Langkah 3 — Duplikasi jadi 3 testimoni
Duplikasikan card tadi menjadi total 3, lalu ubah:
- Inisial (A, R, N)
- Nama dan kota
- Isi testimoni

> 📸 **[SISIPKAN SCREENSHOT]**: 3 kartu testimoni selesai.

---

### Tantangan
1. Ubah background card menjadi `bg-white` dan tambahkan `ring-slate-100`.
2. Ubah rating card kedua menjadi `★★★★☆`.

---

## Refleksi Singkat
Jawab 2–3 kalimat:

1. Bagian mana yang paling kamu suka? Kenapa?
2. Jika kamu jadi pembeli, section mana yang paling meyakinkan? (Manfaat/Produk/Testimoni) Kenapa?
