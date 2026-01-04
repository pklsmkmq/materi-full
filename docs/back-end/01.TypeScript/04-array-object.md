# Pertemuan 4 — Array & Object di TypeScript

## Pertanyaan Pemantik
1. Bagaimana cara menyimpan banyak data dengan rapi?
2. Apa yang terjadi jika isi array tidak konsisten tipenya?
3. Kenapa backend hampir selalu memakai object?

---

## 1. Array Bertipe

Array di TypeScript bisa ditentukan tipenya agar isinya konsisten.

```ts
let scores: number[] = [80, 90, 100];
```

Jika kamu mencoba:
```ts
scores.push("A");
```

TypeScript akan langsung memberi error.

---

## 2. Generic Array (Alternatif)

```ts
let names: Array<string> = ["Ani", "Budi", "Citra"];
```

Fungsinya sama, hanya beda gaya penulisan.

---

## 3. Object Bertipe

Object biasanya mewakili satu entitas (user, produk, jasa).

```ts
let user: { name: string; age: number } = {
  name: "Nur",
  age: 20
};
```

Jika properti kurang atau salah tipe, TypeScript akan menolak.

---

## 4. Array of Object (Pola Industri)

Ini adalah pola **paling sering dipakai** di backend.

```ts
let services: { name: string; price: number }[] = [
  { name: "Cuci Motor", price: 15000 },
  { name: "Cuci Mobil", price: 30000 }
];
```

---

## 5. Mengakses & Mengubah Data

```ts
console.log(services[0].name);

services[1].price = 35000;
```

---

## Latihan
  
### Latihan 1 — Daftar Produk

Buat file `latihan4-1.ts`.

```ts
let products: { name: string; price: number }[] = [
  { name: "Sabun", price: 5000 },
  { name: "Sampo", price: 7000 }
];

console.log(products);
```

Tugas:  
- Tambahkan 1 produk baru  
- Ubah harga salah satu produk

---

### Latihan 2 — Data User

Buat file `latihan4-2.ts`.

Buat array user:
```ts
let users: { username: string; isActive: boolean }[] = [
  { username: "admin", isActive: true },
  { username: "guest", isActive: false }
];
```

Tugas:  
- Tambahkan user baru  
- Ubah status user tertentu

---

## Tantangan Logika

### Tantangan 1 — Data Tidak Lengkap

Kasus:
Seseorang mencoba menambahkan data service seperti ini:
```ts
{ name: "Cuci AC" }
```

Pertanyaan:  
1. Apakah TypeScript mengizinkan data ini?  
2. Kenapa ini berbahaya jika lolos ke backend?  
3. Apa solusi paling sederhana yang sudah kamu pelajari?

---

### Tantangan 2 — Data Tidak Masuk Akal

Kasus:
```ts
{ name: "Cuci Motor", price: -5000 }
```

Pertanyaan:  
1. Apakah TypeScript otomatis menolak harga negatif?  
2. Kalau tidak, di bagian mana seharusnya logika pengecekan dibuat?  
3. Kenapa ini penting di dunia kerja?

---

### Tantangan 3 — Cari Data (Logika Dasar)

Buat fungsi:
```ts
function findServiceByName(
  services: { name: string; price: number }[],
  name: string
) {
  // TODO
}
```

Tugas:  
- Cari service berdasarkan nama  
- Jika tidak ditemukan, tampilkan pesan yang sesuai

Petunjuk:  
- Gunakan loop `for...of`  
- Tidak perlu fitur baru

---

## Studi Kasus Mini (Arah Industri / Backend)

Di backend:
- Data sering disimpan sebagai array of object (sementara, cache, atau hasil query)
- Satu data rusak bisa merusak proses berikutnya

Diskusi:  
1. Apakah TypeScript cukup untuk menjaga data tetap “bersih”?  
2. Kapan kita perlu validasi tambahan?  
3. Kenapa backend sering memisahkan “data” dan “logika”?

---

## Ringkasan

- Array bertipe menjaga konsistensi data.  
- Object bertipe memastikan struktur jelas.  
- Array of object adalah pola inti backend.  
- TypeScript membantu, tapi logika tetap penting.

---

## Tugas (Output Pertemuan 4)

Kumpulkan:  
1. `latihan4-1.ts`  
2. `latihan4-2.ts`  
3. Jawaban tertulis untuk tantangan logika

---

## Refleksi Pembelajaran

Jawab singkat:  
1. Masalah apa yang paling sering muncul saat mengelola banyak data?  
2. Apakah TypeScript cukup untuk menjaga data tetap valid?  
3. Menurutmu, apa peran developer backend dalam menjaga kualitas data?
