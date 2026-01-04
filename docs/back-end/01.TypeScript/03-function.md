# Pertemuan 3 — Function di TypeScript

## Pertanyaan Pemantik
1. Pernahkah function kamu menghasilkan output yang tidak sesuai?
2. Apa yang terjadi jika parameter function diisi tipe yang salah?
3. Apakah semua function harus mengembalikan nilai?

---

## 1. Function Dasar dengan TypeScript

Function di TypeScript bisa (dan sebaiknya) memiliki:
- tipe parameter
- tipe return value

```ts
function add(a: number, b: number): number {
  return a + b;
}

console.log(add(5, 3)); // 8
```

Jika kamu mencoba:
```ts
add("5", 3);
```

TypeScript akan **menolak sebelum program dijalankan**.

---

## 2. Function Tanpa Return (`void`)

Jika function hanya melakukan aksi, gunakan `void`.

```ts
function logMessage(message: string): void {
  console.log(message);
}

logMessage("Belajar TypeScript");
```

---

## 3. Optional Parameter (`?`)

Optional parameter dipakai jika data **boleh ada atau tidak**.

```ts
function greet(name?: string): void {
  if (name) {
    console.log("Halo", name);
  } else {
    console.log("Halo User");
  }
}
```

Pemanggilan:
```ts
greet("Nur");
greet();
```

---

## 4. Default Parameter

Default parameter memberi nilai awal jika parameter tidak dikirim.

```ts
function welcome(name: string = "User"): void {
  console.log("Welcome", name);
}
```

---

## 5. Arrow Function

Arrow function sering dipakai di industri karena lebih ringkas.

```ts
const multiply = (a: number, b: number): number => {
  return a * b;
};
```

Versi singkat:
```ts
const double = (n: number): number => n * 2;
```

---

## Latihan

### Latihan 1 — Hitung Total Harga

Buat file `latihan3-1.ts`.

```ts
function calculateTotal(price: number, qty: number): number {
  return price * qty;
}

console.log(calculateTotal(5000, 3));
```

Tugas:
- Ubah nilai `price` dan `qty`
- Pastikan hasilnya sesuai

---

### Latihan 2 — Tambah Diskon

Buat file `latihan3-2.ts`.

Aturan:  
- `discount` bersifat optional  
- Jika ada diskon → total dikurangi  
- Jika tidak ada diskon → total normal

```ts
function calculatePrice(
  price: number,
  qty: number,
  discount?: number
): number {
  let total = price * qty;

  if (discount) {
    total = total - discount;
  }

  return total;
}
```

Coba:
```ts
console.log(calculatePrice(5000, 2));
console.log(calculatePrice(5000, 2, 2000));
```

---

## Tantangan Logika
  
### Tantangan 1 — Validasi Diskon (Logika Bisnis)

Kasus:  
- Diskon **tidak boleh negatif**  
- Diskon **tidak boleh lebih besar dari total harga**

Tugas:  
Perbaiki function agar:  
- jika diskon < 0 → abaikan  
- jika diskon > total → abaikan

Petunjuk:  
- Gunakan `if`  
- Tidak perlu fitur baru

---

### Tantangan 2 — Pajak

Tambahkan parameter:
```ts
taxPercent?: number
```

Aturan:  
- Pajak dihitung dari total akhir  
- Jika tidak ada pajak → abaikan

Pertanyaan:  
1. Di bagian mana pajak sebaiknya dihitung?  
2. Apakah urutan diskon dan pajak berpengaruh?

---

# Studi Kasus Mini (Arah Industri)

Di dunia kerja:  
- Perhitungan harga harus **akurat**  
- Kesalahan kecil bisa berdampak besar

Diskusi:  
1. Apakah TypeScript cukup untuk mencegah salah hitung?  
2. Bagian mana yang harus diuji (testing)?  
3. Kenapa logika bisnis sering dipisahkan ke service (di NestJS)?

---

## Ringkasan

- Function harus jelas input dan output-nya.  
- Return type membantu mencegah kesalahan.  
- Optional & default parameter membuat function fleksibel.  
- Tantangan logika lebih penting daripada sekadar sintaks.

---

## Tugas (Output Pertemuan 3)

Kumpulkan:  
1. `latihan3-1.ts`  
2. `latihan3-2.ts`  
3. Versi function yang sudah diperbaiki sesuai tantangan

---

## Refleksi Pembelajaran

Jawab singkat:  
1. Kesalahan apa yang paling mudah terjadi saat membuat function?  
2. Kenapa logika bisnis tidak boleh asal?  
3. Menurutmu, bagian mana dari function yang paling krusial?
