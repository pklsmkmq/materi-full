# Pertemuan 2 — Variable, Type, dan Union Type

## Pertanyaan Pemantik
1. Pernahkah kamu menyimpan data yang berbeda dalam satu variable?
2. Apa yang terjadi jika tipe data berubah tanpa disadari?
3. Apakah semua variable perlu ditentukan tipenya?

----

## 1. Variable: `let` vs `const`

### `const`
Dipakai untuk nilai yang **tidak berubah**.

```ts
const appName: string = "Belajar TypeScript";
```

### `let`
Dipakai untuk nilai yang **bisa berubah**.

```ts
let total: number = 0;
total = 10000;
```

---

## 2. Type Annotation (Menentukan Tipe Secara Jelas)

```ts
let name: string = "Nur";
let age: number = 20;
let isActive: boolean = true;
```

**Kelebihan:**  
- Kode lebih jelas  
- Error lebih cepat ketahuan  
- Cocok untuk teamwork

---

## 3. Type Inference (TypeScript Menebak Tipe)

```ts
let city = "Jakarta";  // string
let year = 2026;       // number
```

Selama nilai tidak berubah tipe, ini aman.

> Di industri, inference sering dipakai. Tapi untuk data penting (seperti DTO di NestJS), kita biasanya lebih tegas dengan tipe.

---

## 4. Union Type (Satu Variable, Beberapa Tipe)

Union type berguna ketika data bisa datang dalam dua bentuk.

Contoh: `id` dari database biasanya number, tapi dari route param sering string.

```ts
let id: number | string;

id = 1;
id = "1";
```

❌ Ini tidak boleh:
```ts
id = true;
```

---

## 5. Literal Union (Union untuk Pilihan yang Dibatasi)

Ini bagus untuk status.

```ts
type OrderStatus = "pending" | "success" | "failed";

let status: OrderStatus = "pending";
status = "success";
```

❌ Tidak boleh:
```ts
status = "done";
```

---

## 6. `any` — Cepat, Tapi Berbahaya

```ts
let payload: any;
payload = 123;
payload = "abc";
payload = { ok: true };
```

Masalahnya:
- TypeScript jadi “mati”
- Error mudah lolos
- Kode jadi susah dirawat

> Di industri, `any` biasanya dilarang kecuali sangat terpaksa dan diberi alasan.

---

## Latihan Terarah

### Latihan 1 — Buat Profil User yang Benar
Buat file `latihan1.ts`.

Buat variable:  
- `username` (string)  
- `age` (number)  
- `isVerified` (boolean)

Contoh hasil yang diharapkan:

```ts
let username: string = "nur";
let age: number = 20;
let isVerified: boolean = false;

console.log(username, age, isVerified);
```

---

### Latihan 2 — ID Bisa Number atau String
Buat file `latihan2.ts`.

Buat variable:  
- `userId` bertipe `number | string`

Lalu:  
1) isi `userId = 10`    
2) isi `userId = "10"`  
3) coba isi `userId = true` dan lihat error compile

```ts
let userId: number | string;

userId = 10;
userId = "10";
// userId = true; // sengaja salah

console.log(userId);
```

---

## Tantangan Logika

### Tantangan 1 — Normalisasi ID
Kamu menerima `id` dari luar yang bisa:
- number
- string angka seperti `"12"`

Tugas: buat `normalizeId()` yang mengembalikan **number**.

Nama filenya `challenge2.ts`

### Tantangan tambahan
Coba input:
```ts
console.log(normalizeId("abc"));
```

Pertanyaan:  
1. Apa hasilnya?  
2. Kenapa itu bisa terjadi?  
3. Di industri, apa yang harus dilakukan kalau input tidak valid?

---

### Tantangan 2 — Status Harus Valid
Buat type status:

```ts
type PaymentStatus = "unpaid" | "paid" | "expired";
```

Tugas:  
1) buat variable `paymentStatus` bertipe `PaymentStatus`    
2) isi dengan salah satu nilai yang valid  
3) coba isi nilai yang tidak ada (mis. `"done"`) dan lihat error

> Tujuan: kamu membatasi “pilihan” agar tidak liar.

---

## Studi Kasus Mini

Di NestJS, data dari:  
- query string  
- param URL  
- body request

Sering datang sebagai string.

Contoh:  
- `qty = "3"` (string)  
- `price = "5000"` (string)  

**TypeScript membantu di kode, tapi tidak otomatis mengubah data input.**  
Di backend nanti, kita akan pakai DTO + validation untuk ini.

### Pertanyaan Diskusi
1. Jika `qty` datang sebagai `"3"`, apakah TypeScript otomatis menjadikannya number?
2. Menurutmu, siapa yang bertugas mengubah dan memvalidasi data input di server?

---

## Ringkasan
- Type annotation membuat tipe jelas.
- Type inference membuat kode ringkas.
- Union type menangani data yang bervariasi.
- Literal union membatasi pilihan (status).
- `any` sebaiknya dihindari.

---

## Tugas (Output Pertemuan 2)
Kumpulkan:  
1. `latihan1.ts`  
2. `latihan2.ts`  
3. `challenge2.ts`

---

## Refleksi Pembelajaran
Jawab singkat:  
1. Apa bedanya union type dan literal union?  
2. Kapan kamu butuh union type di dunia nyata?  
3. Apa risiko terbesar dari `any`?
