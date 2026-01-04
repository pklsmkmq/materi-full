# Pertemuan 5 — Interface & Type di TypeScript

## Pertanyaan Pemantik
1. Bagaimana jika struktur data di project berubah-ubah?
2. Apa dampaknya jika data tidak konsisten?
3. Kenapa backend sangat membutuhkan struktur data yang jelas?

---

## 1. Masalah Tanpa Interface

Perhatikan contoh berikut:

```ts
let user1 = { name: "Nur", age: 20 };
let user2 = { username: "Ani", umur: 21 };
```

Masalah:  
- Nama properti tidak konsisten  
- Sulit dibaca dan dirawat  
- Mudah terjadi error saat data diproses

---

## 2. Interface: Menentukan Bentuk Data

Interface digunakan untuk **mendefinisikan struktur object**.

```ts
interface User {
  id: number;
  name: string;
  age: number;
}
```

Pemakaian:

```ts
let user: User = {
  id: 1,
  name: "Nur",
  age: 20
};
```

Jika ada properti yang kurang atau salah tipe, TypeScript akan menolak.

---

## 3. Optional Property (`?`)

Gunakan optional jika data **boleh ada atau tidak**.

```ts
interface User {
  id: number;
  name: string;
  email?: string;
}
```

---

## 4. Readonly Property

Property yang tidak boleh diubah setelah dibuat.

```ts
interface Product {
  readonly id: number;
  name: string;
  price: number;
}
```

```ts
product.id = 2; // ❌ error
```

---

## 5. Type Alias

Selain interface, kita bisa menggunakan `type`.

```ts
type Service = {
  id: number;
  name: string;
  price: number;
};
```

---

## 6. Interface vs Type (Praktis)

| Interface | Type |
|---------|------|
| Fokus object | Fleksibel |
| Bisa extend | Bisa union |
| Umum di backend | Umum di frontend |

> Di NestJS, **interface dan type sering dipakai untuk DTO dan model data**.

---

## Latihan

### Latihan 1 — Data Service

Buat file `latihan5-1.ts`.

```ts
interface Service {
  id: number;
  name: string;
  price: number;
}
```

Buat array services:

```ts
let services: Service[] = [
  { id: 1, name: "Cuci Motor", price: 15000 },
  { id: 2, name: "Cuci Mobil", price: 30000 }
];
```

Tugas:  
- Tambahkan 1 service baru  
- Ubah harga salah satu service

---

### Latihan 2 — Optional Property

Perbarui interface:

```ts
interface Service {
  id: number;
  name: string;
  price: number;
  description?: string;
}
```

Tugas:  
- Tambahkan description hanya ke salah satu service

---

## Tantangan Logika

### Tantangan 1 — Perubahan Kebutuhan

Kasus:  
Awalnya data service hanya:
```ts
{ id, name, price }
```

Sekarang perusahaan meminta:  
- Tambah `isActive` (boolean)

Pertanyaan:  
1. Bagian mana yang perlu diubah?  
2. Apa dampaknya ke data lama?  
3. Kenapa interface mempermudah perubahan ini?

---

### Tantangan 2 — Data Tidak Lengkap

Kasus:  
Seseorang mencoba membuat service seperti ini:

```ts
{ id: 3, name: "Cuci AC" }
```

Pertanyaan:  
1. Apakah TypeScript mengizinkan?  
2. Kenapa ini berbahaya jika lolos ke backend?  
3. Solusi apa yang sudah kamu pelajari?

---

## Studi Kasus Mini

Di NestJS:  
- Data request akan dipetakan ke **DTO**  
- DTO biasanya ditulis menggunakan interface atau class

Diskusi:  
1. Apa hubungan interface dengan DTO?  
2. Kenapa backend tidak boleh menerima data “asal”?

---

## Ringkasan

- Interface membuat struktur data konsisten.  
- Type berguna untuk kebutuhan fleksibel.  
- Interface & type adalah fondasi DTO di backend.  
- Perubahan kebutuhan lebih mudah ditangani dengan struktur yang jelas.

---

## Tugas (Output Pertemuan 5)

Kumpulkan:  
1. `latihan5-1.ts`  
2. Versi interface dengan optional property  
3. Jawaban tertulis untuk tantangan logika  

---

## Refleksi Pembelajaran

Jawab singkat:  
1. Kenapa interface penting di backend?  
2. Apa dampak perubahan struktur data tanpa interface?  
3. Menurutmu, bagian mana paling krusial dari interface?