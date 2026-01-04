# Pertemuan 8 — Mini Project TypeScript (Persiapan Backend)

## Pertanyaan Pemantik
1. Bagaimana menyatukan semua materi menjadi satu program?
2. Apa tantangan terbesar saat membuat project kecil?
3. Apakah kamu merasa lebih siap masuk backend sekarang?

---

## Gambaran Mini Project

### Tema
**Sistem Manajemen Layanan Jasa**

Contoh jasa:  
- Cuci Motor  
- Cuci Mobil  
- Service AC  
- Jasa Desain  
- Jasa Fotografi
  
Project ini **TIDAK memakai UI**.  
Fokus ke **logika & struktur data**, seperti di backend.

---

## Ketentuan Wajib (Review Materi 1–7)

Project harus menggunakan:  
- `type` atau `interface`  
- `array of object`  
- `function`  
- `conditional`  
- `looping`  
- `class`  
- ❌ tidak menggunakan `any`

---

## Spesifikasi Teknis

### 1. Interface Service

Buat file `service.ts`.

```ts
export interface Service {
  id: number;
  name: string;
  price: number;
  isActive: boolean;
}
```

---

### 2. Class ServiceManager

Buat file `service-manager.ts`.

```ts
import { Service } from "./service";

export class ServiceManager {
  private services: Service[] = [];

  add(service: Service): void {
    this.services.push(service);
  }

  getAll(): Service[] {
    return this.services;
  }
}
```

---

## Latihan Terarah

### Latihan 1 — Tambah Data

Buat file `index.ts`.

```ts
import { ServiceManager } from "./service-manager";

const manager = new ServiceManager();

manager.add({
  id: 1,
  name: "Cuci Motor",
  price: 15000,
  isActive: true
});

manager.add({
  id: 2,
  name: "Cuci Mobil",
  price: 30000,
  isActive: true
});

console.log(manager.getAll());
```

---

### Latihan 2 — Aturan Bisnis Sederhana

Tambahkan aturan:
- Harga **tidak boleh <= 0**
- Jika melanggar, data **tidak boleh ditambahkan**

Petunjuk:
- Gunakan `if` di dalam method `add()`

---

## Tantangan Utama
  
### Tantangan 1 — ID Duplikat

Kasus:  
- Ada service baru dengan `id` yang sudah ada

Tugas:  
- Cegah penambahan data duplikat  
- Tampilkan pesan yang jelas

Pertanyaan:  
1. Di mana sebaiknya logika ini ditaruh?  
2. Kenapa tidak di `index.ts`?

---

### Tantangan 2 — Filter Data

Tambahkan method:
```ts
getActiveServices(): Service[]
```

Aturan:  
- Hanya mengembalikan service dengan `isActive === true`  

Petunjuk:  
- Gunakan looping  
- Jangan ubah data asli
  
---

### Tantangan 3 — Update Status

Tambahkan method:
```ts
deactivateService(id: number): void
```

Aturan:  
- Jika id tidak ditemukan → tampilkan pesan  
- Jika ditemukan → ubah `isActive` menjadi `false`

---

## Tantangan Refleksi (Paling Penting)

Jawab secara tertulis:  

1. Masalah apa yang paling sulit kamu selesaikan?  
2. Materi pertemuan mana yang paling sering kamu pakai?  
3. Kalau project ini lebih besar, bagian mana yang perlu dipecah lagi?  
4. Menurutmu, kenapa struktur seperti ini cocok untuk backend?  

---

## Studi Kasus Mini (Arah NestJS)

Di NestJS nanti:  
- `ServiceManager` → akan menjadi **Service**  
- `Service` interface → akan jadi **DTO / Entity**  
- Method → akan dipanggil oleh **Controller**  

Diskusi:  
1. Apakah struktur ini sudah mirip backend sungguhan?  
2. Bagian mana yang paling terasa manfaat TypeScript?  

---

## Ringkasan Akhir Modul TypeScript

- TypeScript membantu menjaga struktur dan logika  
- Error bisa dicegah lebih awal  
- Class & interface adalah fondasi backend  
- Mini project melatih cara berpikir, bukan sekadar ngetik kode

---

## Output Akhir (Wajib Dikumpulkan)

Kumpulkan:  
1. `service.ts`  
2. `service-manager.ts`  
3. `index.ts`  
4. Screenshot hasil compile & output  

---

## Penutup

Jika kamu bisa menyelesaikan mini project ini dengan rapi,
berarti kamu **siap masuk ke materi Backend menggunakan NestJS** 🚀