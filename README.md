# Tugas Praktikum 6 (Pertemuan ke 7) 

|Nama|NIM|Kelas|Mata Kuliah|
|----|---|-----|------|
|**Radityatama Nugraha**|**312310644**|**TI.23.A6**|**Pemrograman Orientasi Objek**|

![gambar](Tugas-Pemrograman-Orientasi-Objek-Pert-7/ss1.png)

#  • Dari modul praktikum 3, tambahkan constructor pada masing-masing class dan tambahkan overload dan override constructor tersebut.
#  • Contoh:
```
Programer ("Andi Herlambang")
Programer ("Riko", 6000000")
Programer ("Dina", 5000000, 3000000)
```

##  • Kelas Pegawai
```java
class Pegawai {
    private String nama;
    private double gajiPokok;

    public Pegawai(String nama, double gajiPokok) {
        this.nama = nama;
        this.gajiPokok = gajiPokok;
    }

    public Pegawai(String nama) {
        this.nama = nama;
        this.gajiPokok = 0; 
    }

    public void setNama(String nama) {
        this.nama = nama;
    }

    public String getNama() {
        return nama;
    }

    public void setGajiPokok(double gajiPokok) {
        this.gajiPokok = gajiPokok;
    }

    public double getGajiPokok() {
        return gajiPokok;
    }

    public void cetakInfo() {
        System.out.printf("Nama: %s, Gaji Pokok: %.0f%n", nama, gajiPokok);
    }
}
```

###  • Penjelasan:
```
- Atribut:
  - private String nama: Menyimpan nama pegawai. Atribut ini bersifat private, yang berarti hanya dapat diakses melalui metode dalam kelas ini.
  - private double gajiPokok: Menyimpan gaji pokok pegawai.

- Konstruktor:
  - public Pegawai(String nama, double gajiPokok): Konstruktor ini digunakan untuk menginisialisasi objek Pegawai dengan nama dan gaji pokok yang diberikan.
  - public Pegawai(String nama): Konstruktor ini hanya menginisialisasi nama pegawai dan menetapkan gaji pokok menjadi 0.

- Metode Set dan Get:
  - public void setNama(String nama): Metode ini digunakan untuk mengubah nama pegawai.
  - public String getNama(): Metode ini mengembalikan nama pegawai.
  - public void setGajiPokok(double gajiPokok): Metode ini digunakan untuk mengubah gaji pokok pegawai.
  - public double getGajiPokok(): Metode ini mengembalikan gaji pokok pegawai.

- Metode cetakInfo():
  - Metode ini mencetak informasi pegawai (nama dan gaji pokok) ke layar dengan format tertentu.
```

##  • Kelas  Manager
```java
class Manager extends Pegawai {
    private double tunjangan;

    public Manager(String nama, double gajiPokok, double tunjangan) {
        super(nama, gajiPokok);
        this.tunjangan = tunjangan;
    }

    public Manager(String nama, double gajiPokok) {
        super(nama, gajiPokok);
        this.tunjangan = 0; 
    }

    public void setTunjangan(double tunjangan) {
        this.tunjangan = tunjangan;
    }

    public double getTunjangan() {
        return tunjangan;
    }

    @Override
    public void cetakInfo() {
        super.cetakInfo();
        System.out.printf("Tunjangan: %.0f%n", tunjangan);
    }
}
```
###  • Penjelasan:
```
- Kelas Manager: Kelas ini merupakan subclass dari Pegawai dan menambahkan informasi spesifik untuk manajer.

- Atribut:
  - double tunjangan: Menyimpan tunjangan yang diterima oleh manajer.

- Konstruktor:
  - public Manager(String nama, double gajiPokok, double tunjangan): Menginisialisasi semua atribut (nama, gaji pokok, dan tunjangan).
  - public Manager(String nama, double gajiPokok): Menginisialisasi nama dan gaji pokok, tunjangan diatur ke 0.

- Metode:
  - setTunjangan dan getTunjangan: Untuk mengatur dan mendapatkan tunjangan manajer.
  - @Override cetakInfo: Mengoverride metode dari Pegawai untuk menampilkan informasi tambahan mengenai tunjangan setelah informasi dasar (nama dan gaji pokok).
```

##  • Kelas Programer 
```java
class Programmer extends Pegawai {
    private double bonus;

    public Programmer(String nama, double gajiPokok, double bonus) {
        super(nama, gajiPokok);
        this.bonus = bonus;
    }

    public Programmer(String nama, double gajiPokok) {
        super(nama, gajiPokok);
        this.bonus = 0; 
    }

    public Programmer(String nama) {
        super(nama);
        this.bonus = 0; 
    }

    public void setBonus(double bonus) {
        this.bonus = bonus;
    }

    public double getBonus() {
        return bonus;
    }

    @Override
    public void cetakInfo() {
        super.cetakInfo();
        System.out.printf("Bonus: %.0f%n", bonus);
    }
}
```
###  • Penjelasan:
```
- Kelas Programmer: Kelas ini juga merupakan subclass dari Pegawai, ditujukan untuk merepresentasikan programmer.

- Atribut:
  - double bonus: Menyimpan bonus yang diterima oleh programmer.

- Konstruktor:
  - public Programmer(String nama, double gajiPokok, double bonus): Menginisialisasi nama, gaji pokok, dan bonus.
  - public Programmer(String nama, double gajiPokok): Menginisialisasi nama dan gaji pokok, bonus diatur ke 0.
  - public Programmer(String nama): Menginisialisasi hanya nama, gaji pokok dan bonus diatur ke 0.

Metode:
  - setBonus dan getBonus: Untuk mengatur dan mendapatkan bonus programmer.
  - @Override cetakInfo: Mengoverride metode dari Pegawai untuk menampilkan informasi mengenai bonus setelah informasi dasar.
```

##  • Kelas Main
```java
public class main {
    public static void main(String[] args) {
        Programmer programmer1 = new Programmer("Andi Herlambang");
        Programmer programmer2 = new Programmer("Riko", 6000000);
        Programmer programmer3 = new Programmer("Dina", 5000000, 3000000);

        System.out.println("Info Programmer 1:");
        programmer1.cetakInfo();
        System.out.println("\nInfo Programmer 2:");
        programmer2.cetakInfo();
        System.out.println("\nInfo Programmer 3:");
        programmer3.cetakInfo();
    }
}
```
###  • Penjelasan:
```
- Kelas Main: Kelas ini berfungsi sebagai titik masuk untuk program. Di sinilah semua objek diciptakan dan informasi mereka dicetak.

- Metode main:
  - Membuat tiga objek Programmer dengan berbagai parameter (nama, gaji pokok, bonus) dan mencetak informasi mereka menggunakan metode cetakInfo().
  - Juga menciptakan satu objek Manager dan mencetak informasinya untuk menunjukkan cara penggunaan kelas Manager.





















