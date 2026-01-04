# Pertemuan 1 — Pengenalan TypeScript

## Pertanyaan Pemantik
1. Pernahkah kamu mengalami error karena salah tipe data di JavaScript?
2. Kenapa error tersebut sering baru muncul saat program dijalankan?
3. Menurutmu, lebih baik error diketahui di awal atau saat aplikasi sudah berjalan?

---

## Apa itu TypeScript?
TypeScript adalah **JavaScript yang memiliki sistem tipe (type system)**.
Artinya, TypeScript membantu kita mengetahui kesalahan **sebelum program dijalankan**.

TypeScript tetap JavaScript, tetapi:  
- Lebih aman  
- Lebih rapi  
- Lebih mudah dirawat untuk project besar

---

## Kenapa Belajar TypeScript?
- Banyak dipakai di **Front End** dan **Back End**
- Mengurangi bug
- Sangat cocok untuk project tim
- Digunakan oleh framework modern (Angular, NestJS, dll)

---

## Persiapan Lingkungan

Pastikan sudah terinstall:  
- Node.js  
- npm

Cek versi:
```bash
node -v
npm -v
```

---

## Instalasi TypeScript

Buat project baru:
```bash
npm init -y
```

Install TypeScript:
```bash
npm install -D typescript
```

Generate config:
```bash
npx tsc --init
```

File `tsconfig.json` akan otomatis dibuat.

---

## File Pertama TypeScript

Buat file `index.ts`:
```ts
let message: string = "Hello TypeScript";
console.log(message);
```

Compile ke JavaScript:
```bash
npx tsc
```

Hasilnya akan menjadi file `index.js`.

Jalankan:
```bash
node index.js
```

---

## Praktik Terarah 1 — Coba Buat Error Tipe

Ubah kode menjadi seperti ini:

```ts
let total: number = 10000;

// sengaja salah: total harus number, tapi diisi string
total = "sepuluh ribu";

console.log(total);
```

Sekarang compile:
```bash
npx tsc
```

✅ Yang kamu harapkan:
- TypeScript memberi error sebelum dijalankan.

---

## Praktik Terarah 2 — Perbaiki Error
Perbaiki menjadi valid:

```ts
let total: number = 10000;
total = 15000;

console.log(total);
```

Compile dan jalankan lagi.
  
---

## Tantangan Logika (Tidak Persis Sama dengan Contoh)

### Kasus
Kamu membuat program menghitung total bayar.

Aturan:  
- `price` harus number  
- `qty` harus number  
- Total = `price * qty`

Namun, di dunia nyata:  
- `qty` sering berasal dari input user (bisa saja string).  
- `price` bisa saja ikut terbaca sebagai string (misalnya dari API atau file).

### Tugas
Buat file `challenge1.ts`:  

1. Buat variable `price` dan `qty`.  
2. Pastikan tipe mereka **number**.  
3. Jika kamu mencoba mengisi string, TypeScript harus menolak.

> Tujuan tantangan ini: kamu sadar bahwa TypeScript melindungi dari “data kotor”.
  
Kumpulkan:  
1. `index.ts` yang bisa dijalankan.  
2. `challenge1.ts` yang menunjukkan:  
   - versi benar (compile sukses)  
   - versi salah (error saat compile)  
   
---

## Perbedaan Singkat JS vs TS

| JavaScript | TypeScript |
|----------|------------|
| Tidak ada tipe | Ada tipe data |
| Error saat runtime | Error saat development |
| Bebas | Lebih aman |

---

## Refleksi Pembelajaran
Jawab singkat:  
1. Apa keuntungan terbesar TypeScript menurutmu?  
2. Bagian mana yang paling kamu pahami hari ini?  
3. Kenapa TypeScript cocok sebelum belajar Backend?
