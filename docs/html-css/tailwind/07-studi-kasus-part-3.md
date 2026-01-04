# Pertemuan 7 — Studi Kasus: Responsive (Mobile, Tablet, Laptop) + Smooth Scroll Menu

Target pertemuan ini:  
- Landing page **rapi di Mobile / Tablet / Laptop**  
- Menu anchor (klik “Produk/Manfaat/Testimoni/Kontak”) **scroll halus (smooth)**  
- Menu **punya versi mobile** (tombol ☰, lalu dropdown)

> Modul ini berbasis file `index.html` yang sudah kamu punya. Ikuti langkahnya satu per satu (jangan tempel semua sekaligus).

---

## Persiapan: Aktifkan smooth scroll global

### Langkah 0.1 — Tambahkan class `scroll-smooth`
Di tag `<html>` ubah menjadi seperti ini:

```html
<html lang="id" class="scroll-smooth">
```

✅ Cek: saat klik menu anchor, scroll terasa halus (kalau belum, lanjut langkah lain dulu).

---

## 1. Pola Responsive yang akan dipakai (biar konsisten)

Pada file kamu banyak container seperti:

- `w-[1100px] mx-auto`
- `w-275 mx-auto`

Agar responsive, kita ganti menjadi container standar:

```html
<div class="mx-auto max-w-5xl px-4 sm:px-6 lg:px-8">
  ...
</div>
```

Penjelasan singkat:  
- `max-w-5xl` → lebar maksimal di laptop  
- `px-4 sm:px-6 lg:px-8` → padding kiri-kanan mengikuti ukuran layar

> ✅ Catatan: Kamu boleh pakai `max-w-6xl` kalau ingin lebih lebar.

---

## 2. TOP BAR: Jadikan responsive (menu desktop + menu mobile)

Bagian Top Bar kamu sekarang masih “desktop only” dan lebar fixed.

### Langkah 2.1 — Ganti container Top Bar
Cari bagian ini:

```html
<div class="w-[1100px] mx-auto flex items-center justify-between py-3">
```

Ganti menjadi:

```html
<div class="mx-auto max-w-5xl px-4 sm:px-6 lg:px-8 flex items-center justify-between py-3">
```

✅ Cek: di layar kecil (mobile) header tidak “kepotong”.

---

### Langkah 2.2 — Sembunyikan menu link di mobile
Cari wrapper menu:

```html
<div class="flex items-center gap-6 text-sm">
```

Ganti menjadi:

```html
<div class="hidden md:flex items-center gap-6 text-sm">
```

✅ Cek: menu link hilang saat layar kecil.

---

### Langkah 2.3 — Tambahkan tombol menu (☰) khusus mobile
Masih di Top Bar, tepat setelah div menu desktop (yang `hidden md:flex...`), tambahkan:

```html
<button id="btnMenu" class="md:hidden inline-flex items-center justify-center w-10 h-10 rounded-xl bg-white/10 ring-1 ring-white/15">
  ☰
</button>
```

✅ Cek: di mobile muncul tombol ☰.

---

### Langkah 2.4 — Buat dropdown menu versi mobile (panel)
Tambahkan tepat **setelah** container Top Bar (masih di dalam wrapper Top Bar):

```html
<!-- MOBILE MENU PANEL -->
<div id="mobileMenu" class="md:hidden hidden">
  <div class="mx-auto max-w-5xl px-4 sm:px-6 lg:px-8 pb-4">
    <div class="rounded-2xl bg-white/10 ring-1 ring-white/15 p-4 flex flex-col gap-3 text-sm">
      <a class="hover:text-white" href="#produk">Produk</a>
      <a class="hover:text-white" href="#manfaat">Manfaat</a>
      <a class="hover:text-white" href="#testimoni">Testimoni</a>
      <a class="hover:text-white" href="#kontak">Kontak</a>

      <a href="#produk"
        class="mt-2 inline-flex justify-center px-4 py-2 rounded-xl bg-emerald-500 text-emerald-950 font-semibold hover:bg-emerald-400 transition">
        Pesan Sekarang
      </a>
    </div>
  </div>
</div>
```

✅ Cek: panel belum muncul (karena masih `hidden`). Kita akan buat toggle pakai JS.

---

### Langkah 2.5 — Tambahkan JS toggle menu
Di paling bawah `index.html`, sebelum `</body>`, tambahkan:

```html
<script>
  const btn = document.getElementById("btnMenu");
  const panel = document.getElementById("mobileMenu");

  btn?.addEventListener("click", () => {
    panel.classList.toggle("hidden");
  });

  // auto-close ketika klik link di menu mobile
  panel?.querySelectorAll('a[href^="#"]').forEach(a => {
    a.addEventListener("click", () => panel.classList.add("hidden"));
  });
</script>
```

✅ Cek:
- Klik ☰ → panel muncul/hilang
- Klik link panel → panel otomatis tertutup dan scroll menuju section

> 📸 **[SISIPKAN SCREENSHOT]**: menu mobile terbuka.

---

## 3. Biar anchor tidak “ketutup” Top Bar (opsional tapi bagus)

Karena Top Bar ada di atas, saat klik menu kadang judul section ketutup.  
Solusinya: tambahkan `scroll-mt-*` pada section yang punya id.

### Langkah 3.1 — Tambahkan `scroll-mt-24` pada tiap section id
Contoh, ubah:

```html
<section id="produk" class="w-full">
```

Menjadi:

```html
<section id="produk" class="w-full scroll-mt-24">
```

Lakukan juga untuk:
- `#tentang`
- `#manfaat`
- `#testimoni`
- `#kontak` (footer)

✅ Cek: saat klik menu, judul section tidak ketutup.

---

## 4. JUMBOTRON (Hero): Mobile → Tablet → Laptop

Saat ini hero memakai `w-275`, `w-155`, dan kolom kaku. Kita ubah jadi fleksibel.

### Langkah 4.1 — Ubah container hero menjadi responsive
Cari:

```html
<div class="w-275 mx-auto flex items-center justify-between py-16">
```

Ganti menjadi:

```html
<div class="mx-auto max-w-5xl px-4 sm:px-6 lg:px-8 flex flex-col lg:flex-row items-start lg:items-center gap-10 py-12 lg:py-16">
```

✅ Cek:
- Mobile: konten jadi bertumpuk (atas-bawah)
- Laptop: kembali dua kolom (kiri-kanan)

---

### Langkah 4.2 — Ubah lebar kolom kiri dan kanan
Cari div kolom kiri yang `w-155`, ganti jadi:

```html
<div class="w-full lg:flex-1">
```

Cari div kolom kanan `w-[420px]`, ganti jadi:

```html
<div class="w-full lg:w-[420px]">
```

✅ Cek:
- Mobile: card promo di bawah dan full width
- Laptop: card promo di kanan dengan lebar 420px

---

### Langkah 4.3 — Buat ukuran teks hero responsive
Cari class pada judul hero (contoh kamu `text-5xl`). Ubah jadi:

```html
<h1 class="mt-5 text-3xl sm:text-4xl lg:text-5xl font-extrabold tracking-tight text-white leading-[1.1]">
```

✅ Cek: judul tidak kebesaran di mobile.

---

### Langkah 4.4 — Trust points di mobile jadi wrap
Bagian trust points kamu memakai `flex` sejajar. Ubah wrapper-nya menjadi:

Dari:
```html
<div class="mt-8 flex items-center gap-3">
```

Ke:
```html
<div class="mt-8 flex flex-col sm:flex-row flex-wrap gap-3">
```

✅ Cek: di mobile trust points turun ke bawah dengan rapi.

---

## 5. Section lainnya: ubah pola layout jadi mobile-first

Di file kamu, banyak section memakai:

- `w-[1100px] mx-auto`
- layout 2 kolom `flex ... w-[520px]`

### Pola cepat yang dipakai:
- Container: `mx-auto max-w-5xl px-4 sm:px-6 lg:px-8`
- Layout 2 kolom: `flex flex-col lg:flex-row gap-8 lg:gap-10`

---

## 6. ABOUT BRAND (#tentang) — buat 2 kolom jadi stack di mobile

### Langkah 6.1 — Container About Brand
Cari:
```html
<div class="w-[1100px] mx-auto flex items-center justify-between py-14">
```

Ganti menjadi:
```html
<div class="mx-auto max-w-5xl px-4 sm:px-6 lg:px-8 flex flex-col lg:flex-row items-start lg:items-center gap-10 py-12 lg:py-14">
```

### Langkah 6.2 — Lebar kolom kiri/kanan
Ganti kedua kolom `w-[520px]` menjadi:
```html
<div class="w-full lg:w-[520px]">
```

✅ Cek: About jadi 1 kolom di mobile.

---

## 7. BENEFITS (#manfaat) — dari 3 card sejajar jadi grid responsive

Di benefits kamu pakai `flex gap-6` untuk 3 card.  
Kita ubah ke grid agar responsif.

### Langkah 7.1 — Ganti wrapper cards ke grid
Cari wrapper card benefits:
```html
<div class="mt-10 flex gap-6">
```

Ganti menjadi:
```html
<div class="mt-10 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
```

✅ Cek:
- Mobile: 1 kolom
- Tablet: 2 kolom
- Laptop: 3 kolom

---

## 8. PRODUCT CARDS (#produk) — grid responsive + CTA tetap rapi

### Langkah 8.1 — Ganti wrapper produk jadi grid
Cari:
```html
<div class="mt-10 flex gap-6">
```

Ganti menjadi:
```html
<div class="mt-10 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
```

✅ Cek: kartu produk otomatis menyesuaikan layar.

### Langkah 8.2 — Mini CTA: jadi stack di mobile
Cari mini CTA wrapper:
```html
<div class="mt-10 rounded-[28px] ... flex items-center justify-between ...">
```

Ubah flex-nya menjadi:
```html
<div class="mt-10 rounded-[28px] bg-emerald-950 p-8 text-emerald-50 flex flex-col lg:flex-row items-start lg:items-center gap-6 justify-between relative overflow-hidden">
```

✅ Cek: tombol CTA turun ke bawah di mobile.

---

## 9. TESTIMONI (#testimoni) — grid responsive

Cari wrapper testimoni yang `flex gap-6`, ganti menjadi grid:

```html
<div class="mt-10 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
```

✅ Cek: mobile 1 kolom, tablet 2, laptop 3.

---

## 10. FOOTER (#kontak) — jadi stack di mobile

Footer kamu ada `flex ... justify-between`.  
Ubah ke mobile-first:

Cari wrapper footer:
```html
<div class="flex items-start justify-between gap-10">
```

Ganti menjadi:
```html
<div class="flex flex-col lg:flex-row items-start justify-between gap-10">
```

Dan container footer:
```html
<div class="w-[1100px] mx-auto py-14">
```
Ganti:
```html
<div class="mx-auto max-w-5xl px-4 sm:px-6 lg:px-8 py-12 lg:py-14">
```

✅ Cek: footer rapih di mobile.

---

## TUGAS PRAKTIK (Wajib)

### Praktik 1 — Screenshot 3 device
Buktikan page sudah responsive:
1. Mobile (lebar ~375px)
2. Tablet (lebar ~768px)
3. Laptop (lebar ≥1024px)

---

### Praktik 2 — Menu Mobile berfungsi
1. Klik ☰ → panel muncul
2. Klik “Produk” → scroll halus ke section produk dan panel menutup

---

### Praktik 3 — Layout card tidak rusak
Pastikan di mobile:
- tidak ada scroll horizontal
- card tidak kepotong
- teks tidak keluar container

---

## Refleksi Singkat
Jawab 2–3 kalimat:

1. Perubahan apa yang paling terasa saat mengubah fixed width menjadi `max-w + px-*`?
2. Bagian mana yang paling sulit dibuat responsive? Kenapa?
3. Apa manfaat `scroll-smooth` dan `scroll-mt-*` bagi pengalaman pengguna?
