# Pertemuan 6 — Conditional & Looping di TypeScript

## Pertanyaan Pemantik
1. Bagaimana program menentukan suatu kondisi benar atau salah?
2. Apa yang terjadi jika logika kondisi salah?
3. Kapan kita perlu melakukan perulangan data?

---

## 1. Conditional: `if` dan `else`

Conditional dipakai untuk **mengambil keputusan**.

```ts
let age: number = 18;

if (age >= 18) {
  console.log("Dewasa");
} else {
  console.log("Belum Dewasa");
}
```

---

## 2. `else if` — Banyak Kondisi

```ts
let score: number = 85;

if (score >= 90) {
  console.log("A");
} else if (score >= 80) {
  console.log("B");
} else {
  console.log("C");
}
```

---

## 3. `switch case`

Cocok untuk kondisi berbasis nilai tertentu.

```ts
let role: string = "admin";

switch (role) {
  case "admin":
    console.log("Akses penuh");
    break;
  case "user":
    console.log("Akses terbatas");
    break;
  default:
    console.log("Role tidak dikenal");
}
```

---

## 4. Looping dengan `for`

```ts
for (let i = 1; i <= 5; i++) {
  console.log(i);
}
```

---

## 5. Looping dengan `for...of`

Sangat cocok untuk **array of object**.

```ts
let services = ["Cuci Motor", "Cuci Mobil", "Service AC"];

for (let service of services) {
  console.log(service);
}
```

---

## 6. Looping dengan `forEach`

```ts
services.forEach((service) => {
  console.log(service);
});
```

---

## Latihan

### Latihan 1 — Status User

Buat file `latihan6-1.ts`.

```ts
let isLogin: boolean = true;

if (isLogin) {
  console.log("User sudah login");
} else {
  console.log("User belum login");
}
```

Tugas:  
- Ubah nilai `isLogin`  
- Perhatikan output

---

### Latihan 2 — Penilaian Sederhana

Buat file `latihan6-2.ts`.

```ts
function getGrade(score: number): string {
  if (score >= 90) {
    return "A";
  } else if (score >= 80) {
    return "B";
  } else {
    return "C";
  }
}

console.log(getGrade(85));
```

---

## Latihan 3 — Loop Data Service

Buat file `latihan6-3.ts`.

```ts
let services = [
  { name: "Cuci Motor", price: 15000 },
  { name: "Cuci Mobil", price: 30000 },
  { name: "Service AC", price: 50000 }
];

for (let s of services) {
  console.log(s.name, s.price);
}
```

---

## Tantangan Logika

### Tantangan 1 — Filter Data

Kasus:  
- Tampilkan hanya service dengan harga di bawah 30000

Petunjuk:  
- Gunakan `if` di dalam loop

---

### Tantangan 2 — Aturan Bisnis

Kasus:  
- Service dengan harga >= 50000 mendapat label “Premium”

Tugas:  
- Tambahkan kondisi di loop  
- Tampilkan label sesuai aturan

---

### Tantangan 3 — Kondisi Kompleks

Kasus:  
- Jika user adalah `admin` dan status login = true → akses penuh  
- Selain itu → akses terbatas

Pertanyaan:  
1. Bagaimana menyusun conditional yang rapi?  
2. Kenapa logika ini sering muncul di backend?

---

## Studi Kasus Mini

Di NestJS:  
- Conditional sering ada di **service**  
- Contoh: validasi, role checking, business rule

Diskusi:  
1. Kenapa logika tidak langsung ditaruh di controller?  
2. Apa risiko logika yang berantakan?  

---

## Ringkasan

- Conditional = pengambil keputusan  
- Looping = memproses banyak data  
- Logika bisnis sering gabungan keduanya  
- Backend sangat bergantung pada conditional & looping  

---

## Tugas (Output Pertemuan 6)

Kumpulkan:  
1. `latihan6-1.ts`  
2. `latihan6-2.ts`  
3. `latihan6-3.ts`  
4. Hasil tantangan logika

---

## Refleksi Pembelajaran

Jawab singkat:  
1. Kesalahan logika apa yang paling sering terjadi?  
2. Kenapa conditional harus jelas dan rapi?  
3. Bagian mana dari backend yang paling sering memakai conditional?