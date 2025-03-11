# <p align="center">LAPORAN PRAKTIKUM PBO</p>
## <p align="center">MODUL 1</p>
### <p align="center">(CLASS, OBJECT & METHOD)</p>

<p align="center">Laporan ini disusun untuk memenuhi Tugas Mata Kuliah</p>
<p align="center"><b>Praktikum Pemrograman Berbasis Objek</b></p>

<br>

<p align="center">
  <img src="images/Logo TEL-U.png" alt="Cover Laporan" width="300"/>
</p>

<br>
<br>

### <p align="center">Disusun Oleh:</p>  
<p align="center"><b>Nama:</b> Fauzan Arrizal</p>  
<p align="center"><b>NIM:</b> 2311110021</p>

<br>

<p align="center"><b>PROGRAM STUDI S1 SAINS DATA</b></p>  
<p align="center"><b>FAKULTAS INFORMATIKA</b></p>  
<p align="center"><b>TELKOM UNIVERSITY PURWOKERTO</b></p>  
<p align="center"><b>2025</b></p>  

<div style="page-break-after: always;"></div>

---

## **1. Dasar Teori**  
Tuliskan dasar teori tentang **Class, Object**, dan **Method** dalam pemrograman berbasis objek (OOP).  

- **Class**: adalah rancangan atau template yang digunakan untuk membuat objek. Di dalamnya terdapat variabel dan metode yang menentukan bagaimana suatu objek berfungsi. Class berperan sebagai wadah yang menyimpan atribut dan perilaku objek, seperti Person, Vehicle, Tree, atau Fruit.
- **Object**: adalah sesuatu yang dibuat dari kelas dan memiliki data serta fungsi untuk menjalankan tugasnya. Misalnya, jika ada kelas Fruit, maka objeknya bisa berupa Mangga, Pisang, atau Apel, yang masing-masing punya warna, rasa, dan berat.  
- **Method**: adalah sekumpulan instruksi dalam program yang memiliki nama dan digunakan untuk menjalankan tugas tertentu. Method membantu memecah program menjadi bagian kecil yang bisa digunakan berulang kali. Method didefinisikan dalam class tetapi dipanggil melalui objek. Contohnya, pada objek Mangga, bisa ada method seperti `ambilRasa()` atau `kupasKulit()`.

---

## **2. Tugas Guided**  
Buat program Java untuk **manajemen akun bank** menggunakan **kelas, objek, metode**, dan **konstruktor**.  

### **Guided Class :**
```java
package latihanguided;

/**
 *
 * @author ASUS
 */
public class BankAccount {
    // Deklarasi variabel
    String namaPemilik;
    double Saldo;

    // Konstruktor akun bank (inisialisasi)
    BankAccount(String nama, double saldoAwal) {
        namaPemilik = nama;
        Saldo = saldoAwal;
    }

    // Metode untuk menyetor uang
    void deposit(double jumlah) {
        Saldo += jumlah;
        System.out.println("");
        System.out.println(namaPemilik + " menyetor " + jumlah);
        System.out.println("Saldo sekarang: " + Saldo);
    }

    // Metode untuk menarik uang
    void tariktunai(double jumlah) {
        System.out.println("");
        if (Saldo >= jumlah) {
            Saldo -= jumlah;
            System.out.println(namaPemilik + " menarik " + jumlah);
            System.out.println("Saldo sekarang: " + Saldo);
        } else {
            System.out.println(namaPemilik + " gagal menarik " + jumlah);
            System.out.println("Saldo tidak mencukupi: " + Saldo);
        }
    }

    // Metode untuk menampilkan saldo
    void tampilsaldo() {
        System.out.println("");
        System.out.println("Saldo " + namaPemilik + ": " + Saldo);
    }
}
```

### **Guided Main Class :**
```java
package latihanguided;

/**
 *
 * @author ASUS
 */
public class Latihanguided {
    public static void main(String[] args) {
        BankAccount akun1 = new BankAccount("Alice", 1000);
        BankAccount akun2 = new BankAccount("Abdul", 500);

        System.out.println("< TRANSAKSI BANK >");

        // Transaksi
        akun1.deposit(200); // Alice setor 200
        akun2.tariktunai(300); // Abdul tarik tunai 300
        akun1.tariktunai(500); // Alice tarik tunai 500
        akun2.deposit(100); // Abdul menyetor 100

        // Menampilkan saldo akhir
        System.out.println("\n< SALDO AKHIR >");
        akun1.tampilsaldo();
        akun2.tampilsaldo();
    }
}
```
### **Output :**
```
< TRANSAKSI BANK >

Alice menyetor 200.0
Saldo sekarang: 1200.0

Abdul menarik 300.0
Saldo sekarang: 200.0

Alice menarik 500.0
Saldo sekarang: 700.0

Abdul menyetor 100.0
Saldo sekarang: 300.0

< SALDO AKHIR >

Saldo Alice: 700.0

Saldo Abdul: 300.0
```

### **Penjelasan :**
#### **Penjelasan class (BankAccount)**
Kelas `BankAccount` digunakan untuk membuat akun bank dengan nama pemilik dan saldo awal. Fungsi utama:

- `deposit()`, untuk menambah saldo saat pengguna menyetor uang.
- `tariktunai()`, untuk menarik uang jika saldo mencukupi, atau menampilkan pesan jika saldo kurang.
- `tampilsaldo()`, untuk menampilkan saldo terbaru.

#### **Penjelasan main class (Latihanguided)**
Dibuat dua akun bank untuk Alice dan Abdul.
Kemudian, dilakukan beberapa transaksi:

- Alice menyetor 200, saldo menjadi 1200.
- Abdul menarik 300, saldo menjadi 200.
- Alice menarik 500, saldo menjadi 700.
- Abdul menyetor 100, saldo menjadi 300.

---

## **2. Tugas Unguided**
Modifikasi program sebelumnya agar memiliki fitur transfer saldo antar akun bank. Buatlah metode tambahan dalam kelas BankAccount

### **Unguided Class :**
```java
package latihanguided;

/**
 *
 * @author ASUS
 */
public class BankAccount {
    // Deklarasi variabel
    String namaPemilik;
    double Saldo;

    // Konstruktor akun bank (inisialisasi)
    BankAccount(String nama, double saldoAwal) {
        namaPemilik = nama;
        Saldo = saldoAwal;
    }

    // Metode untuk menyetor uang
    void deposit(double jumlah) {
        Saldo += jumlah;
        System.out.println("");
        System.out.println(namaPemilik + " menyetor " + jumlah);
        System.out.println("Saldo sekarang: " + Saldo);
    }

    // Metode untuk menarik uang
    void tariktunai(double jumlah) {
        System.out.println("");
        if (Saldo >= jumlah) {
            Saldo -= jumlah;
            System.out.println(namaPemilik + " menarik " + jumlah);
            System.out.println("Saldo sekarang: " + Saldo);
        } else {
            System.out.println(namaPemilik + " gagal menarik " + jumlah);
            System.out.println("Saldo tidak mencukupi: " + Saldo);
        }
    }

    // Metode untuk transfer saldo ke akun lain
    void transferSaldo(BankAccount tujuan, double jumlah) {
        System.out.println("");
        if (Saldo >= jumlah) {
            Saldo -= jumlah;
            tujuan.Saldo += jumlah;
            System.out.println(namaPemilik + " mentransfer " + jumlah + " ke " + tujuan.namaPemilik);
            System.out.println("Saldo " + namaPemilik + " sekarang: " + Saldo);
            System.out.println("Saldo " + tujuan.namaPemilik + " sekarang: " + tujuan.Saldo);
        } else {
            System.out.println(namaPemilik + " gagal mentransfer " + jumlah + " ke " + tujuan.namaPemilik);
            System.out.println("Saldo tidak mencukupi.");
        }
    }

    // Metode untuk menampilkan saldo
    void tampilsaldo() {
        System.out.println("");
        System.out.println("Saldo " + namaPemilik + ": " + Saldo);
    }
}
```

### **Unguided Main Class :**
```java
package latihanguided;

/**
 *
 * @author ASUS
 */
public class Latihanguided {
    public static void main(String[] args) {
        BankAccount akun1 = new BankAccount("Alice", 1000);
        BankAccount akun2 = new BankAccount("Abdul", 500);

        System.out.println("< TRANSAKSI BANK >");

        // Transaksi
        akun1.deposit(200); // Alice setor 200
        akun2.tariktunai(300); // Abdul tarik tunai 300
        akun1.tariktunai(500); // Alice tarik tunai 500
        akun2.deposit(100); // Abdul menyetor 100

        // Transfer saldo
        akun1.transferSaldo(akun2, 400); // Alice transfer 400 ke Abdul
        akun2.transferSaldo(akun1, 200); // Abdul transfer 200 ke Alice

        // Menampilkan saldo akhir
        System.out.println("\n< SALDO AKHIR >");
        akun1.tampilsaldo();
        akun2.tampilsaldo();
    }
}
```

### **Output :**
```
< TRANSAKSI BANK >

Alice menyetor 200.0
Saldo sekarang: 1200.0

Abdul menarik 300.0
Saldo sekarang: 200.0

Alice menarik 500.0
Saldo sekarang: 700.0

Abdul menyetor 100.0
Saldo sekarang: 300.0

Alice mentransfer 400.0 ke Abdul
Saldo Alice sekarang: 300.0
Saldo Abdul sekarang: 700.0

Abdul mentransfer 200.0 ke Alice
Saldo Abdul sekarang: 500.0
Saldo Alice sekarang: 500.0

< SALDO AKHIR >

Saldo Alice: 500.0

Saldo Abdul: 500.0
```

### **Penjelasan :**
#### **Penjelasan class (BankAccount)**
Ditambahkan metode transferSaldo() agar saldo bisa dipindahkan ke akun lain. Jika saldo cukup, jumlahnya akan berkurang dari pengirim dan bertambah di penerima. Jika tidak, muncul pesan gagal.

#### **Penjelasan main class (Latihanguided)**
Dibuat dua akun bank untuk Alice dan Abdul.
Kemudian, dilakukan beberapa transaksi:

- Alice menyetor 200, saldo menjadi 1200.
- Abdul menarik 300, saldo menjadi 200.
- Alice menarik 500, saldo menjadi 700.
- Abdul menyetor 100, saldo menjadi 300.
- Alice mentransfer 400 ke Abdul, saldo Alice menjadi 300 dan saldo Abdul menjadi 700.
- Abdul mentransfer 200 ke Alice, saldo Abdul menjadi 500 dan saldo Alice kembali menjadi 500.