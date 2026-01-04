# Pertemuan 7 — Class & OOP Dasar di TypeScript

## Pertanyaan Pemantik
1. Kenapa data dan function sering digabung dalam satu struktur?
2. Apa masalah jika semua data ditaruh di variable biasa?
3. Kenapa backend modern banyak menggunakan class?

---

## 1. Apa itu Class?

Class adalah **cetakan (blueprint)** untuk membuat object.  
Class menggabungkan:  
- **data** (property)  
- **perilaku** (method)
  
Di backend, hampir semua fitur dibungkus dalam class.

---

## 2. Class Dasar

```ts
class User {
  name: string;
  age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }
}

const user1 = new User("Nur", 20);
console.log(user1.name);
```

---

## 3. Constructor dengan Shortcut

TypeScript menyediakan cara singkat:

```ts
class User {
  constructor(
    public name: string,
    public age: number
  ) {}
}
```

---

## 4. Method di Dalam Class

```ts
class User {
  constructor(
    public name: string,
    public age: number
  ) {}

  greet(): void {
    console.log("Halo, saya", this.name);
  }
}

const user = new User("Nur", 20);
user.greet();
```

---

## 5. Access Modifier

### `public`  
- Bisa diakses dari mana saja

### `private`  
- Hanya bisa diakses dari dalam class

```ts
class Account {
  constructor(
    public username: string,
    private password: string
  ) {}

  login(input: string): boolean {
    return input === this.password;
  }
}
```

Coba:
```ts
account.password; // ❌ error
```

---

## 6. `protected` (Sekilas)

- Bisa diakses oleh class turunan  
- Umum dipakai di backend besar

---

## Latihan Terarah

### Latihan 1 — Class Service

Buat file `latihan7-1.ts`.

```ts
class Service {
  constructor(
    public name: string,
    public price: number
  ) {}

  show(): void {
    console.log(this.name, "-", this.price);
  }
}

const s = new Service("Cuci Motor", 15000);
s.show();
```

---

### Latihan 2 — Class dengan Logika

Buat file `latihan7-2.ts`.

Tambahkan method:  
- `getPriceAfterDiscount(discount: number)`

Aturan:  
- Diskon tidak boleh negatif  
- Diskon tidak boleh lebih besar dari harga

---

## Tantangan Logika

### Tantangan 1 — Data Sensitif

Kasus:  
- Password **tidak boleh** bisa dibaca langsung  
- Tapi sistem perlu memeriksa login

Pertanyaan:  
1. Kenapa `password` harus `private`?  
2. Kenapa tidak boleh diakses langsung?  
3. Method apa yang tepat untuk memeriksa password?

---

### Tantangan 2 — Aturan Bisnis di Class

Kasus:  
- Service tidak boleh memiliki harga <= 0

Tugas:  
- Tambahkan validasi di constructor  
- Jika harga tidak valid, tampilkan pesan error

---

### Tantangan 3 — Struktur Backend (Diskusi)

Di NestJS:  
- Controller → menerima request  
- Service → menyimpan logika bisnis  

Pertanyaan:  
1. Kenapa logika tidak ditaruh di controller?  
2. Apa risiko jika semua logika bercampur?  

---

# Studi Kasus Mini

Class di NestJS:  
- Hampir semua file adalah class  
- Dependency Injection bekerja dengan class
  
Diskusi:  
1. Apa keuntungan arsitektur berbasis class?  
2. Kenapa class memudahkan testing?  

---

## Ringkasan

- Class menggabungkan data dan logika  
- Access modifier melindungi data penting  
- Class adalah fondasi arsitektur backend  
- Tanpa class, backend sulit dirawat

---

## Tugas (Output Pertemuan 7)

Kumpulkan:  
1. `latihan7-1.ts`  
2. `latihan7-2.ts`  
3. Jawaban tertulis untuk tantangan logika

---

## Refleksi Pembelajaran

Jawab singkat:  
1. Kenapa class penting di backend?  
2. Apa risiko jika semua property dibuat public?  
3. Bagian mana dari class yang paling sering dipakai?