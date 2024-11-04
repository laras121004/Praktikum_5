# Praktikum_5

| keterangan | Data |
| ---- | ---- |
| Nama | Laras Sakti |
| Kelas | TI.23.A6 |
| Nim | 312310627 |
| Mata Kuliah | Pemograman Orientasi Objek |

# Latihan

## Class Pegawai

~~~
package pegawai;

public class Pegawai {
    private String nama;
    private double gajiPokok;

    // Konstruktor
    public Pegawai() {
    }

    public Pegawai(String nama, double gajiPokok) {
        this.nama = nama;
        this.gajiPokok = gajiPokok;
    }

    // Setter dan getter nama
    public String getNama() {
        return nama;
    }
    public void setNama(String nama) {
        this.nama = nama;
    }

    // Setter dan getter gajiPokok
    public double getGajiPokok() {
        return gajiPokok;
    }
    public void setGajiPokok(double gajiPokok) {
        this.gajiPokok = gajiPokok;
    }

    // Mencetak informasi Pegawai
    public void cetakInfo() {
        System.out.println("Nama: " + nama);
        System.out.println("Gaji Pokok: " + gajiPokok);
    }
}

~~~

## Class Manager

~~~

package pegawai;

public class Manager extends Pegawai {
    private double tunjangan;

    // Konstruktor 
    public Manager() {
    }
    public Manager(String nama, double gajiPokok, double tunjangan) {
        super(nama, gajiPokok); // Memanggil konstruktor kelas induk
        this.tunjangan = tunjangan;
    }

    // Setter dan getter tunjangan
    public double getTunjangan() {
        return tunjangan;
    }
    public void setTunjangan(double tunjangan) {
        this.tunjangan = tunjangan;
    }

    @Override
    public void cetakInfo() {
        super.cetakInfo();
        System.out.println("Tunjangan: " + tunjangan);
    }
}

~~~

## Class Programmer

~~~

package pegawai;

public class Programmer extends Pegawai {
    private double bonus;

    // Konstruktor
    public Programmer() {
    }
    // Overloading konstruktor  Programmer
    public Programmer(String nama) {
        super(nama, 0); // Mengatur gajiPokok default 0
    }

    public Programmer(String nama, double gajiPokok) {
        super(nama, gajiPokok);
    }

    public Programmer(String nama, double gajiPokok, double bonus) {
        super(nama, gajiPokok); // Memanggil konstruktor kelas induk
        this.bonus = bonus;
    }

    // Setter dan getter bonus
    public double getBonus() {
        return bonus;
    }
    public void setBonus(double bonus) {
        this.bonus = bonus;
    }

    @Override
    public void cetakInfo() {
        super.cetakInfo();
        System.out.println("Bonus: " + bonus);
    }
}

~~~

## Class Main

~~~

package pegawai;

public class PegawaiBeraksi {
    public static void main(String[] args) {
        // Menggunakan overloaded konstruktor membuat objek manager dan programmer
        Manager manager = new Manager("Anton", 9000000, 2000000);
        System.out.println("Data Manager:");
        manager.cetakInfo();

        Programmer programmer1 = new Programmer("Andi Herlambang");
        System.out.println("\nData Programmer 1:");
        programmer1.cetakInfo();

        Programmer programmer2 = new Programmer("Riko", 6000000);
        System.out.println("\nData Programmer 2:");
        programmer2.cetakInfo();

        Programmer programmer3 = new Programmer("Dina", 5000000, 3000000);
        System.out.println("\nData Programmer 3:");
        programmer3.cetakInfo();
    }
}

~~~

## Output

![](Output5_1.png)

<p></p>
