# Pertemuan 4 — Responsive Design dengan Tailwind CSS

## Pertanyaan Pemantik

Renungkan dan diskusikan:

1. Kenapa tampilan website di HP dan laptop **tidak bisa disamakan**?
2. Apa masalah yang muncul jika website desktop dipaksa tampil sama di layar kecil?
3. Menurutmu, kapan sebuah elemen perlu disembunyikan di mobile?

---

## Pengantar Singkat

**Responsive design** adalah cara membuat tampilan website **menyesuaikan ukuran layar**.  
Di Tailwind, responsive dibuat dengan **prefix breakpoint**, seperti:

- `sm:` → small (tablet / HP besar)
- `md:` → medium (laptop)
- `lg:` → large (desktop besar)

Prinsip penting:
> **Mobile dulu, lalu diperbesar ke layar lebih besar.**

---

## 1. Breakpoint Dasar (sm, md, lg)

### Contoh Responsive Text

```html
<h1 class="text-xl md:text-2xl lg:text-4xl font-bold">
  Judul Responsive
</h1>
```

Penjelasan:
- HP → `text-xl`
- Laptop → `md:text-2xl`
- Desktop besar → `lg:text-4xl`

---

#### Praktik
1. Ubah ukuran teks di HP, laptop, dan desktop
2. Bandingkan tampilannya saat layar di-resize

---

## 2. Responsive Spacing

```html
<div class="p-4 md:p-8 lg:p-12 bg-slate-100">
  Box dengan padding berbeda tiap ukuran layar
</div>
```

---

### Praktik
1. Ubah padding di tiap breakpoint
2. Tentukan padding yang paling nyaman untuk mobile

---

## 3. Card Section (Mobile → Desktop)

### Struktur Dasar
```html
<section class="bg-slate-100 p-6">
  <div class="mx-auto max-w-5xl">
    <h2 class="text-xl font-bold">Produk Kami</h2>

    <div class="mt-4 flex flex-col gap-4 md:flex-row">
      <div class="flex-1 rounded-xl bg-white p-4 shadow">
        <h3 class="font-semibold">Sabun Herbal</h3>
        <p class="text-slate-600">Aroma segar alami</p>
      </div>

      <div class="flex-1 rounded-xl bg-white p-4 shadow">
        <h3 class="font-semibold">Sabun Kopi</h3>
        <p class="text-slate-600">Mengangkat sel kulit mati</p>
      </div>

      <div class="flex-1 rounded-xl bg-white p-4 shadow">
        <h3 class="font-semibold">Sabun Susu</h3>
        <p class="text-slate-600">Lembut untuk kulit sensitif</p>
      </div>
    </div>
  </div>
</section>
```

Penjelasan:
- Mobile → card tersusun **vertikal**
- `md:flex-row` → card sejajar horizontal di laptop

---

#### Praktik
1. Tambahkan 1 card lagi
2. Atur jarak agar tidak terlalu rapat di mobile
3. Pastikan tampilan rapi di laptop

---

## 4. Menu Responsive (Mobile vs Laptop)

### Struktur Dasar Menu
```html
<nav class="bg-white p-4 shadow">
  <div class="mx-auto flex max-w-5xl items-center justify-between">
    <div class="text-xl font-bold">Toko Sabun</div>

    <ul class="hidden gap-6 md:flex">
      <li>Home</li>
      <li>Produk</li>
      <li>Kontak</li>
    </ul>

    <button class="md:hidden">
      ☰
    </button>
  </div>
</nav>
```

Penjelasan:
- Mobile → tombol menu (☰) tampil
- Laptop → menu list tampil
- `hidden` dan `md:flex` mengatur visibilitas

---

#### Praktik
1. Ubah teks tombol menu menjadi ikon atau teks lain
2. Ubah jarak antar menu di laptop
3. Ganti warna background menu

---
  
## Tugas
  
### Tugas Praktik 1 — Card Responsive

Buat **section card produk** dengan aturan:
- Mobile → card vertikal
- Laptop → card horizontal
- Gunakan `sm`, `md`, atau `lg`

Kriteria:
- Spacing nyaman di mobile
- Tampilan rapi di laptop

---

### Tugas Praktik 2 — Menu Responsive

Buat **menu responsive**:
- Mobile → hanya logo + tombol menu
- Laptop → logo + menu lengkap
- Gunakan `hidden`, `flex`, dan breakpoint

---

### Tugas Praktik 3 — Mini Landing Section

Gabungkan:
- 1 menu responsive
- 1 section card responsive

Pastikan:
- Tidak ada scroll horizontal
- Tampilan rapi di HP & laptop

---

## Ringkasan

- Responsive Tailwind menggunakan prefix `sm`, `md`, `lg`
- Layout mobile disusun terlebih dahulu
- Card dan menu adalah contoh kasus responsive paling umum
- Praktik langsung membantu memahami responsive lebih cepat