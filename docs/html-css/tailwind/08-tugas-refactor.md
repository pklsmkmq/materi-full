# Pertemuan 8 — Proyek Akhir: Landing Page Produk JASA (Tailwind CSS)

## Gambaran Umum
Pada pertemuan ini kamu **membuat landing page sendiri** dengan tema **Produk JASA**  
(contoh: Jasa Pembuatan Web/Aplikasi, Jasa Desain, Jasa Prompting, Jasa Joki, dll).

Semua yang kamu buat **HARUS menerapkan materi dari Pertemuan 1–7**.  
Tidak ada materi baru, fokus ke **implementasi & kerapian**.

---

## Tujuan Pembelajaran
Setelah pertemuan ini, kamu diharapkan mampu:  
- Mengubah ide jasa menjadi tampilan website yang rapi  
- Menyusun layout menggunakan **Flexbox**  
- Mengatur jarak, warna, dan teks dengan Tailwind  
- Membuat website **responsive (mobile–tablet–laptop)**  
- Menggunakan **menu + smooth scroll**

---

## Struktur WAJIB Landing Page
Landing page kamu **WAJIB memiliki minimal 6 section** berikut:
  
1. **Top Bar / Navbar**  
2. **Hero Section**  
3. **Layanan / Service**  
4. **Keunggulan / Benefit**  
5. **Testimoni**  
6. **Kontak / CTA**

---

## KETENTUAN TEKNIS (WAJIB)

### 1. HTML + Tailwind
- Gunakan **Tailwind CSS (Vite / CLI)** seperti pertemuan sebelumnya
- Tidak boleh pakai Bootstrap atau framework lain
- Class Tailwind **ditulis langsung di HTML**

---

### 2. Navbar & Smooth Scroll
Navbar wajib memiliki:  
- Logo / nama jasa  
- Menu anchor (href ke `#id-section`)  
- **Smooth scroll aktif**  
- **Responsive:**  
    > Mobile → tombol ☰  
    > Laptop → menu biasa  

Contoh menu:
```html
<a href="#layanan">Layanan</a>
<a href="#testimoni">Testimoni</a>
<a href="#kontak">Kontak</a>
```

---

### 3. Hero Section
Hero harus berisi:  
- Judul jasa (jelas & besar)  
- Deskripsi singkat  
- Tombol CTA (contoh: “Hubungi Kami”, “Pesan Sekarang”)

Ketentuan:  
- Mobile → konten stack (atas–bawah)  
- Laptop → 2 kolom (teks & gambar/placeholder)  

---

### 4. Section Layanan (Wajib Flexbox)
Buat **minimal 3 layanan**, contoh:  
- Cuci Motor Reguler  
- Cuci Motor Premium  
- Paket Langganan

Ketentuan:  
- Gunakan **Flexbox**  
- Mobile → 1 kolom  
- Tablet → 2 kolom  
- Laptop → 3 kolom

---

### 5. Section Benefit / Keunggulan
Isi dengan **alasan kenapa jasa kamu layak dipilih**.

Ketentuan:  
- Minimal 3 benefit  
- Gunakan spacing rapi (padding & margin)  
- Gunakan warna **primary / secondary** (custom di `tailwind.config.js`)

---

### 6. Section Testimoni
Ketentuan:  
- Minimal 2 testimoni  
- Nama + peran (misal: “Andi – Pelanggan”)  
- Layout card rapi  
- Responsive

---

### 7. Section Kontak / CTA
Harus ada:   
- Tombol CTA besar (WhatsApp / Form / Telepon)  
- Kalimat ajakan yang jelas  
- Tidak boleh hanya teks biasa  

Contoh:
```html
<a href="#" class="bg-primary text-white px-6 py-3 rounded-xl">
  Hubungi Sekarang
</a>
```

---

## KETENTUAN RESPONSIVE (WAJIB)

Website harus:  
- ✔️ Tidak ada scroll horizontal  
- ✔️ Rapi di mobile (≤ 375px)  
- ✔️ Rapi di tablet (≥ 768px)  
- ✔️ Rapi di laptop (≥ 1024px)

Gunakan:  
- `flex`, `flex-col`, `flex-row`  
- `sm:`, `md:`, `lg:`  
- `max-w-*` + `px-*`

---

## KETENTUAN DESAIN (WAJIB)
  
- Gunakan **maksimal 2–3 warna utama**  
- Gunakan **custom color** di `tailwind.config.js`  
- Spacing konsisten  
- Teks mudah dibaca  
- Tidak boleh asal tempel class

---

## CONTOH STRUKTUR FILE
```
project/
├─ index.html
├─ tailwind.config.js
├─ src/
│  └─ style.css
```

---

## RUBRIK PENILAIAN

| Aspek | Bobot |
|-----|------|
| Struktur section lengkap | 20% |
| Penggunaan Tailwind (spacing, color, text) | 20% |
| Flexbox & layout | 20% |
| Responsive | 20% |
| Kerapian & konsistensi | 20% |

---

## TUGAS PENGUMPULAN

Kumpulkan:  
1. Link Github & Vercel  
2. Screenshot:  
   - Tampilan Mobile  
   - Tampilan Tablet  
   - Tampilan Laptop  
3. Tema jasa yang dipilih  

---

## Refleksi Akhir
Jawab singkat:  
1. Bagian mana yang paling sulit kamu buat?  
2. Materi pertemuan mana yang paling sering kamu pakai?  
3. Kalau punya waktu lebih, bagian mana yang ingin kamu perbaiki?

---

## Penutup
Jika kamu bisa menyelesaikan proyek ini dengan rapi dan responsive,  
berarti kamu **SUDAH SIAP membuat landing page Tailwind secara mandiri** 🚀
