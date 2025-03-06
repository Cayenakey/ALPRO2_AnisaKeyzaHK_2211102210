# <h1 align="center">Laporan Praktikum Modul 2 <br> Review Pengenalan Pemrograman</h1>

<p align="center">ANISA KEYZA HUSNUL KHATIMAH - 2211102210</p>

  

## Dasar Teori

Bahasa pemrograman Go (Golang) merupakan bahasa pemrograman yang dikembangkan oleh Google dengan tujuan menyediakan bahasa yang efisien, sederhana, dan aman. Program Go selalu dimulai dengan deklarasi package main sebagai penanda bahwa file tersebut adalah program utama. Eksekusi program dilakukan pada fungsi main(), yang berfungsi sebagai entry point dari program. Go mendukung berbagai tipe data seperti integer, float, boolean, dan string. Input pada Go menggunakan fungsi fmt.Scanln() yang membaca data dari pengguna dan menyimpannya ke dalam variabel melalui referensi alamat memori menggunakan simbol &. Program pada contoh melakukan pertukaran nilai antar variabel dengan memanfaatkan variabel sementara (temp). Konsep ini penting dalam algoritma pemrograman karena memperkenalkan operasi penugasan (assignment) dan manipulasi data, yang merupakan dasar dalam pengolahan data dan algoritma.

## Unguided


### Soal 1 - 2A

  Telusuri program berikut dengan cara mengkompilasi dan mengeksekusi program. Silakan masukan data yang sesuai sebanyak yang diminta program. Perhatikan keluaran yang diperoleh. Coba terangkan apa sebenarnya yang dilakukan program tersebut?

```go

package main

import "fmt"

func main() {
    var (
        satu, dua, tiga string
        temp            string
    )
    fmt.Print("Masukan input string: ")
    fmt.Scanln(&satu)
    fmt.Print("Masukan input string: ")
    fmt.Scanln(&dua)
    fmt.Print("Masukan input string: ")
    fmt.Scanln(&tiga)
    fmt.Println("Output awal = " + satu + " " + dua + " " + tiga)
    temp = satu
    satu = dua
    dua = tiga
    tiga = temp
    fmt.Println("Output akhir = " + satu + " " + dua + " " + tiga)

}
```

> Output
> ![](output/gambar.png)


Kode program di atas ditulis dalam bahasa pemrograman Go (Golang) dan berfungsi untuk menerima tiga input string dari pengguna, lalu melakukan pergeseran nilai variabel secara siklis sebelum menampilkan hasil akhir.

1. Import Library :
	- Mengimpor package `fmt`, yang digunakan untuk menampilkan output (`Print` / `Println`) dan menerima input (`Scanln`).
2. Deklarasi Variabel
	- `satu`, `dua`, dan `tiga` adalah variabel untuk menyimpan input dari pengguna.
	- `temp` digunakan sebagai variabel sementara untuk membantu pertukaran nilai. 
3. Mengambil Input dari Pengguna
	- Program meminta pengguna untuk memasukkan tiga string secara berturut-turut.
4. Menampilkan Output Awal
	- Program mencetak nilai awal sebelum dilakukan pertukaran.
5. Melakukan Pergeseran Nilai Secara Skills
	- Nilai `satu` disimpan sementara di `temp`.
	- Nilai `dua` dipindahkan ke `satu`.
	- Nilai `tiga` dipindahkan ke `dua`.
	- Nilai awal `satu` (yang tersimpan di `temp`) dipindahkan ke `tiga`.
6. Menampilkan Output Akhir
	- Program mencetak nilai setelah dilakukan pertukaran.
  

### Soal 2 - 2A

Tahun kabisat adalah tahun yang habis dibagi 400 atau habis dibagi 4 tetapi tidak habis  
dibagi 100. Buatlah sebuah program yang menerima input sebuah bilangan bulat dan  
memeriksa apakah bilangan tersebut merupakan tahun kabisat (true) atau bukan (false).

```go
package main

import (
    "fmt"
)

func isLeapYear(year int) bool {
    // Tahun kabisat adalah yang habis dibagi 400 atau habis dibagi 4 tetapi tidak habis dibagi 100
    if year%400 == 0 {
        return true
    } else if year%100 == 0 {
        return false
    } else if year%4 == 0 {
        return true
    }
    return false
}

func main() {
    var year int
    fmt.Print("Tahun: ")
    fmt.Scanln(&year)

    if isLeapYear(year) {
        fmt.Println("Kabisat: true")
    } else {
        fmt.Println("Kabisat: false")
    }
}
```


> Output
>  ![](output/gambar2.png)![Screenshot bagian x](output/screenshot_soal2A.png)

  
1. **Fungsi `isLeapYear(year int) bool`**
    - Mengembalikan `true` jika `year` adalah tahun kabisat.
    - Tahun kabisat memenuhi kondisi:
        - Habis dibagi 400 **atau**
        - Habis dibagi 4 **tetapi tidak habis dibagi 100**.
2. **Fungsi `main()`**
    - Menerima input tahun dari pengguna.
    - Memeriksa apakah tahun tersebut kabisat dengan memanggil `isLeapYear(year)`.
    - Menampilkan hasil `true` jika tahun kabisat, dan `false` jika bukan.

Program ini akan membaca tahun dari pengguna, mengecek apakah itu tahun kabisat, lalu menampilkan hasilnya sesuai dengan aturan yang diberikan


### Soal 3 - 2A

Buat program Bola yang menerima input jari-jari suatu bola (bilangan bulat). Tampilkan  
Volume dan Luas kulit bola. 𝑣𝑜𝑙𝑢𝑚𝑒𝑏𝑜𝑙𝑎 = 4/3𝜋𝑟3 dan 𝑙𝑢𝑎𝑠𝑏𝑜𝑙𝑎 = 4𝜋𝑟2 (π ≈  3.1415926535)

```go

package main

import (
    "fmt"
    "math"
)

func main() {
    var r float64

    // Input dari user
    fmt.Print("Jejari = ")
    fmt.Scan(&r)

    // Menghitung volume dan luas permukaan bola
    volume := (4.0 / 3.0) * math.Pi * math.Pow(r, 3)
    luas := 4 * math.Pi * math.Pow(r, 2)

    // Menampilkan hasil
    fmt.Printf("Bola dengan jejari %.0f memiliki volume %.4f dan luas kulit %.4f\n", r, volume, luas)
}
```


>Output
> ![](output/gambar3.png)

#### **Penjelasan:**

Program ini ditulis dalam bahasa **Go (Golang)** untuk menghitung **volume dan luas permukaan bola** berdasarkan input jejari (radius) dari pengguna.

1. Import Paket
	- **`fmt`** → Digunakan untuk **input dan output** (misalnya `fmt.Print`, `fmt.Scan`, `fmt.Printf`).
	- **`math`** → Digunakan untuk **perhitungan matematika**, seperti **π (Pi) dan pemangkatan (pow)**.
2. ### **Fungsi `main()`**
	- Mendeklarasikan **variabel `r`** bertipe **`float64`** untuk menyimpan **jejari bola** (angka desimal).
3. ### **Menerima Input dari Pengguna**
	- **`fmt.Print("Jejari = ")`** → Menampilkan teks untuk meminta input.
	- **`fmt.Scan(&r)`** → Membaca input jejari yang dimasukkan pengguna.
4. ### **Menghitung Volume dan Luas Permukaan Bola**
	- **Volume bola** dihitung dengan rumus:
	    - `math.Pi` → Nilai π (sekitar **3.1415926535**).
	    - `math.Pow(r, 3)` → Pangkat **3 dari `r`**.
	- **Luas permukaan bola** dihitung dengan rumus:
	    - `math.Pow(r, 2)` → Pangkat **2 dari `r`**.
5. ### **5. Menampilkan Hasil**
	- **`fmt.Printf`** digunakan untuk menampilkan output dengan format tertentu:
	    - `%.0f` → Menampilkan **jejari (`r`) tanpa desimal**.
	    - `%.4f` → Menampilkan **volume dan luas dengan 4 angka desimal**.

 - **Program ini digunakan untuk menghitung volume dan luas permukaan bola berdasarkan jejari yang dimasukkan pengguna.**  
-  **Menggunakan fungsi `math.Pow()` untuk pemangkatan dan `math.Pi` untuk nilai π.**  
-  **Output ditampilkan dengan format yang rapi menggunakan `fmt.Printf`**


### Soal 4 - 2A

Dibaca nilai temperatur dalam derajat Celsius. Nyatakan temperatur tersebut dalam  
Fahrenheit  
𝐶𝑒𝑙𝑠𝑖𝑢𝑠 = (𝐹𝑎ℎ𝑟𝑒𝑛ℎ𝑒𝑖𝑡 - 32) × 5/9
𝑅𝑒𝑎𝑚𝑢𝑟 = 𝐶𝑒𝑙𝑐𝑖𝑢𝑠 × 4/5  
𝐾𝑒𝑙𝑣𝑖𝑛 = (𝐹𝑎ℎ𝑟𝑒𝑛ℎ𝑒𝑖𝑡 + 459.67) × 5/9

```go

package main

import (
    "fmt"
)

func main() {
    var celsius float64

    // Input dari pengguna
    fmt.Print("Temperatur Celsius: ")
    fmt.Scan(&celsius)

    // Konversi suhu
    reamur := celsius * 4 / 5
    fahrenheit := (celsius * 9 / 5) + 32
    kelvin := celsius + 273

    // Menampilkan hasil konversi
    fmt.Printf("Derajat Reamur: %.0f\n", reamur)
    fmt.Printf("Derajat Fahrenheit: %.0f\n", fahrenheit)
    fmt.Printf("Derajat Kelvin: %.0f\n", kelvin)
}

```


> Output
> ![](output/gambar4.png)

  Program ini bertujuan untuk mengubah suhu yang diberikan dalam **derajat Celsius** ke dalam tiga satuan suhu lainnya, yaitu **Reamur, Fahrenheit, dan Kelvin**. Berikut adalah rincian penjelasan program:

1. ### **1. Import Package**
	- Program mengimpor package **fmt** yang digunakan untuk menangani input dan output standar di Golang.
2. ### **. Deklarasi Fungsi `main`**
	- Fungsi `main()` adalah titik awal eksekusi program.
	- Variabel `celsius` bertipe `float64` digunakan untuk menyimpan nilai suhu dalam Celsius.
3. ### **. Menerima Input dari Pengguna**
	- `fmt.Print("Temperatur Celsius: ")` menampilkan pesan agar pengguna memasukkan suhu dalam derajat Celsius.
	- `fmt.Scan(&celsius)` membaca input dari pengguna dan menyimpannya dalam variabel `celsius`.
4. ### **Konversi Suhu**
	Setelah pengguna memasukkan nilai suhu dalam Celsius, program akan mengonversinya ke tiga satuan lain:
	- **Rumus Reamur:** `Reamur = Celsius × 4/5`
		- Contoh: Jika `Celsius = 50`, maka `Reamur = 50 × 4/5 = 40`
	- **Rumus Fahrenheit:** `Fahrenheit = (Celsius × 9/5) + 32`
		- Contoh: Jika `Celsius = 50`, maka `Fahrenheit = (50 × 9/5) + 32 = 122`
	- **Rumus Kelvin:** `Kelvin = Celsius + 273`
		- Contoh: Jika `Celsius = 50`, maka `Kelvin = 50 + 273 = 323`
5. ### **Menampilkan Hasil Konversi**
	- `fmt.Printf("%.0f", value)` digunakan untuk menampilkan angka tanpa desimal.
	- Hasil konversi suhu ditampilkan dalam tiga satuan yang telah dihitung.


### Soal 5 - 2A

Tipe karakter sebenarnya hanya apa yang tampak dalam tampilan. Di dalamnya  
tersimpan dalam bentuk biner 8 bit (byte) atau 32 bit (rune) saja.
Buat program ASCII yang akan membaca 5 buat data integer dan mencetaknya dalam  
format karakter. Kemudian membaca 3 buah data karakter dan mencetak 3 buah karakter  
setelah karakter tersebut (menurut tabel ASCII).
**Masukan** terdiri dari dua baris. Baris pertama berisi 5 buah data integer. Data integer  
mempunyai nilai antara 32 s.d. 127. Baris kedua berisi 3 buah karakter yang  
berdampingan satu dengan yang lain (tanpa dipisahkan spasi).  
**Keluaran** juga terdiri dari dua baris. Baris pertama berisi 5 buah representasi karakter dari  
data yang diberikan, yang berdampingan satu dengan lain, tanpa dipisahkan spasi. Baris  
kedua berisi 3 buah karakter (juga tidak dipisahkan oleh spasi).

| No. |          Masukan           |    Keluaran    |
| :-: | :------------------------: | :------------: |
| 1.  | 66 97 103 117 115  <br>SNO | Bagus  <br>TOP |
**Catatan:** Gunakan fmt.Scanf(“%c”, &var) untuk pembacaan satu karakter dan  
fmt.Printf(“%c”, var) untuk penulisan satu karakter.

```go

```

>Output
>![]()


### Soal 1 - 2B

Siswa kelas IPA di salah satu sekolah menengah atas di Indonesia sedang mengadakan  
praktikum kimia. Di setiap percobaan akan menggunakan 4 tabung reaksi, yang mana  
susunan warna cairan di setiap tabung akan menentukan hasil percobaan. Siswa diminta  
untuk mencatat hasil percobaan tersebut. Percobaan dikatakan berhasil apabila susunan  
warna zat cair pada gelas 1 hingga gelas 4 secara berturutan adalah ‘merah’, ‘kuning’,  
‘hijau’, dan ‘ungu’ selama 5 kali percobaan berulang.  
Buatlah sebuah program yang menerima input berupa warna dari ke 4 gelas reaksi  
sebanyak 5 kali percobaan. Kemudian program akan menampilkan true apabila urutan  
warna sesuai dengan informasi yang diberikan pada paragraf sebelumnya, dan false  
untuk urutan warna lainnya.


```go
package main

import (
    "bufio"
    "fmt"
    "os"
    "strings"
)

func main() {
    // Urutan warna yang diharapkan
    expected := []string{"merah", "kuning", "hijau", "ungu"}

    // Membuat scanner untuk membaca input dari user
    scanner := bufio.NewScanner(os.Stdin)

    // Variabel untuk menampung hasil validasi
    berhasil := true

    // Loop untuk membaca 5 kali percobaan
    for i := 1; i <= 5; i++ {
        fmt.Printf("Percobaan %d: ", i)
        scanner.Scan()
        input := scanner.Text()
        warna := strings.Fields(input) // Memisahkan input berdasarkan spasi

        // Validasi apakah input sesuai dengan urutan yang diharapkan
        if len(warna) != 4 || !equalSlices(warna, expected) {
            berhasil = false
        }
    }

    // Menampilkan hasil akhir
    fmt.Println("BERHASIL:", berhasil)
}

// Fungsi untuk membandingkan dua slice string
func equalSlices(a, b []string) bool {
    if len(a) != len(b) {
        return false
    }
    for i := range a {
        if a[i] != b[i] {
            return false
        }
    }
    return true
}

```

>Output
>![](output/gambar6.png)

#### **Penjelasan:**

1. **Mendefinisikan urutan warna yang diharapkan**: `["merah", "kuning", "hijau", "ungu"]`
2. **Menggunakan `bufio.Scanner` untuk membaca input** agar lebih fleksibel.
3. **Melakukan iterasi sebanyak 5 kali** untuk membaca setiap percobaan.
4. **Memeriksa apakah urutan warna sesuai** dengan menggunakan fungsi `equalSlices()`.
5. **Jika ada satu saja percobaan yang tidak sesuai, hasilnya akan `false`**, jika semuanya benar, hasilnya `true`.
6. **Hasil akhir dicetak sebagai `BERHASIL: true/false`**.


### Soal 2 - 2B

Suatu pita (string) berisi kumpulan nama-nama bunga yang dipisahkan oleh spasi dan ‘– ‘, contoh pita diilustrasikan seperti berikut ini.
**Pita: mawar – melati – tulip – teratai – kamboja – anggrek**
Buatlah sebuah program yang menerima input sebuah bilangan bulat positif (dan tidak nol) N, kemudian program akan meminta input berupa nama bunga secara berulang sebanyak N kali dan nama tersebut disimpan ke dalam pita.
(Petunjuk: gunakan operasi penggabungan string dengan operator “+” ).
Tampilkan isi pita setelah proses input selesai.
Modifikasi program sebelumnya, proses input akan berhenti apabila user mengetikkan  
‘SELESAI’. Kemudian tampilkan isi pita beserta banyaknya bunga yang ada di dalam pita.

#### Versi 1 - Menggunakan N Sebagai Input

```go
package main

import (
    "fmt"
    "strings"
)

func main() {
    var N int
    fmt.Print("N: ")
    _, err := fmt.Scan(&N)

    if err != nil || N <= 0 {
        fmt.Println("Pita :")
        return
    }

    var pita []string
    for i := 1; i <= N; i++ {
        var bunga string
        fmt.Printf("Bunga %d: ", i)
        fmt.Scan(&bunga)
        pita = append(pita, bunga)
    }

    // Gabungkan pita dengan format " - "
    fmt.Println("Pita:", strings.Join(pita, " - ")+" -")
}
```

>Output
>![](output/gambar7.png)

#### **Penjelasan Program Versi 1

Program ini dibuat untuk **menerima input sejumlah nama bunga** dan kemudian menampilkannya dalam **format pita** dengan pemisah `" - "`.

1. Input jumlah bunga (N)
	- Program meminta input angka `N`, yang menunjukkan jumlah bunga yang akan dimasukkan.
	- Menggunakan `fmt.Scan(&N)` untuk membaca input.
	- `_, err := fmt.Scan(&N)` digunakan untuk menangani kemungkinan **kesalahan input** (misalnya jika pengguna memasukkan teks bukan angka).
2. Validasi Input N
	- Jika pengguna memasukkan **angka 0 atau angka negatif**, program langsung menampilkan `"Pita :"` dan berhenti.
	- Jika pengguna memasukkan **bukan angka**, program juga akan langsung berhenti.
3. Memasukkan Nama Bunga ke dalam List
	- Program menggunakan **slice (array dinamis)** `pita` untuk menyimpan nama bunga.
	- `fmt.Scan(&bunga)` membaca input nama bunga.
	- `pita = append(pita, bunga)` menambahkan bunga ke dalam list.
4. Menampilkan Hasil dalam Format Pita
	- `strings.Join(pita, " - ")` menggabungkan elemen dalam list `pita` dengan pemisah `" - "`.
	- Ditambahkan `+" -"` di akhir agar format sesuai dengan contoh.

-  Program ini **meminta pengguna memasukkan sejumlah nama bunga** berdasarkan angka `N`.  
-  Program **menyimpan nama-nama bunga dalam list** dan kemudian **menampilkan hasilnya dalam format pita**.  
-  **Menggunakan validasi** untuk memastikan input `N` tidak negatif atau bukan angka.

#### Versi 2 - Menggunakan 'SELESAI' sebagai Penghenti Input

```go
package main

import (
    "fmt"
    "strings"
)

func main() {
    var pita []string
    var bunga string

    i := 1
    for {
        fmt.Printf("Bunga %d: ", i)
        fmt.Scan(&bunga)
  
        if bunga == "SELESAI" {
            break
        }

        pita = append(pita, bunga)
        i++
    }

    // Menampilkan hasil pita
    if len(pita) > 0 {
        fmt.Println("Pita:", strings.Join(pita, " - ")+" -")
    } else {
        fmt.Println("Pita :")
    }

    // Menampilkan jumlah bunga dalam pita
    fmt.Println("Bunga:", len(pita))
}
```

>Output
>![](gambar8.png)

#### **Penjelasan Program Versi 2

Program ini merupakan pengembangan dari versi sebelumnya. Perbedaannya adalah:
1. **Input bisa dihentikan dengan mengetikkan "SELESAI"**, sehingga pengguna tidak perlu memasukkan jumlah N di awal.
2. Setelah selesai, program akan menampilkan **jumlah bunga yang dimasukkan**.

##### **Struktur Program**
1. Inisialisasi dan Input Nama Bunga**
	- `pita` adalah **slice (array dinamis)** untuk menyimpan nama-nama bunga.
	- `bunga` digunakan untuk menyimpan input sementara dari pengguna.
2. Loop untuk Memasukkan Nama Bunga**
	- Program akan **terus meminta input bunga** sampai pengguna mengetik `"SELESAI"`.
	- Jika input adalah `"SELESAI"`, maka program akan **keluar dari loop**.
	- Jika bukan `"SELESAI"`, maka input bunga akan ditambahkan ke dalam `pita` menggunakan `append()`.
3. Menampilkan Pita dan Jumlah Bunga**
	- `strings.Join(pita, " - ")+" -"` akan menampilkan bunga dalam format pita seperti pada contoh.
	- `len(pita)` akan mencetak jumlah bunga yang dimasukkan sebelum `"SELESAI"`.

- Versi 2 **tidak perlu memasukkan jumlah bunga di awal** seperti versi 1.  
- **Loop berjalan terus sampai pengguna mengetik "SELESAI"**.  
- Setelah selesai, program menampilkan **jumlah bunga yang dimasukkan**.


### Soal 3 - 2B

Setiap hari Pak Andi membawa banyak barang belanjaan dari pasar dengan mengendarai  
sepeda motor. Barang belanjaan tersebut dibawa dalam kantong terpal di kiri-kanan  
motor. Sepeda motor tidak akan oleng jika selisih berat barang di kedua kantong sisi tidak  
lebih dari 9 kg.  
Buatlah program Pak Andi yang menerima input dua buah bilangan real positif yang  
menyatakan berat total masing-masing isi kantong terpal. Program akan terus meminta  
input bilangan tersebut hingga salah satu kantong terpal berisi 9 kg atau lebih.
Pada modifikasi program tersebut, program akan menampilkan true jika selisih kedua isi  
kantong lebih dari atau sama dengan 9 kg. Program berhenti memproses apabila total  
berat isi kedua kantong melebihi 150 kg atau salah satu kantong beratnya negatif.


```go
package main

import (
    "fmt"
)

func main() {
    var kantongKiri, kantongKanan float64

    for {
        fmt.Print("Masukan berat belanjaan di kedua kantong: ")
        _, err := fmt.Scan(&kantongKiri, &kantongKanan)
        if err != nil {
            fmt.Println("Input tidak valid, coba lagi.")
            continue
        }

        // Jika salah satu kantong mencapai atau melebihi 9 kg, hentikan program
        if kantongKiri >= 9 || kantongKanan >= 9 {
            break
        }
    }

    fmt.Println("Proses selesai.")
}
```

>Output
>![](gambar9.png)

#### **Penjelasan Program**

Program **Versi 1** berfungsi untuk menerima input berupa berat barang di dua kantong terpal (kiri dan kanan) yang dibawa oleh Pak Andi di atas sepeda motor. Program ini akan terus meminta input dari pengguna sampai salah satu kantong memiliki berat **9 kg atau lebih**, setelah itu program berhenti.
##### **Langkah Kerja Program**

1. **Menerima input** dari pengguna berupa dua angka (berat kantong kiri dan kanan).
2. **Melakukan pengecekan kondisi:**
    - Jika salah satu kantong memiliki berat **≥ 9 kg**, program akan berhenti dengan menampilkan pesan **"Proses selesai."**
    - Jika tidak, program akan meminta input baru dari pengguna.

- **Program terus berjalan** selama berat kedua kantong masih di bawah 9 kg.
- **Program berhenti** jika **salah satu kantong mencapai atau melebihi 9 kg**.
- Tidak ada validasi tambahan untuk input negatif atau batas maksimum berat total dalam versi ini.


### Soal 4 - 2B

Diberikan sebuah persamaan sebagai berikut ini.  
𝑓(𝑘) =  (4𝑘 + 2)^2 / (4𝑘 + 1)(4𝑘 + 3)  
Buatlah sebuah program yang menerima input sebuah bilangan sebagai K, kemudian  
menghitung dan menampilkan nilai f(K) sesuai persamaan di atas.
Modifikasi program sebelumnya yang menerima input integer 𝐾 dan menghitung √2  
untuk 𝐾 tersebut. Hampiran √2 dituliskan dalam ketelitian 10 angka di belakang koma.

#### Versi 1 : Menghitung f(K)

```go
package main

import (
    "fmt"
)

func calculateF(k float64) float64 {
    numerator := (4*k + 2) * (4*k + 2)
    denominator := (4*k + 1) * (4*k + 3)
    return numerator / denominator
}

func main() {
    var k float64

    // Input nilai K
    fmt.Print("Nilai K = ")
    fmt.Scan(&k)

    // Hitung f(K)
    fk := calculateF(k)

    // Cetak hasil dengan 10 angka di belakang koma
    fmt.Printf("Nilai f(K) = %.10f\n", fk)
}
```

>Output
>![](gambar11.png)

Program ini dibuat untuk menerima input bilangan KKK, lalu menghitung nilai fungsi dan menampilkan hasilnya dengan 10 angka di belakang koma.

1. **Import Package**
    - Kita menggunakan **fmt** untuk menangani input dan output pada terminal.
2. **Fungsi `calculateF`**
    - Fungsi ini menerima parameter **k** dengan tipe **float64**.
    - Menghitung pembilang: (4k+2)2(4k + 2)^2(4k+2)2.
    - Menghitung penyebut: (4k+1)(4k+3)(4k + 1)(4k + 3)(4k+1)(4k+3).
    - Mengembalikan hasil pembagian **numerator / denominator**.
3.  **Fungsi `main` (Program Utama)**
    - Mendeklarasikan variabel `k` dengan tipe **float64** untuk menerima input dari pengguna.
4. **Menerima Input dari Pengguna**
    - Menampilkan teks **"Nilai K ="** dan membaca input dari pengguna.
5. **Menghitung dan Menampilkan Hasil**
    - Memanggil fungsi `calculateF(k)` untuk menghitung nilai fungsi f(K)f(K)f(K).
    - Menggunakan `fmt.Printf` untuk menampilkan hasil dengan **10 angka desimal**.

#### Versi 2

```go
package main

import (
    "fmt"
)

func calculateApproximation(k int) float64 {
    product := 1.0

    for i := 0; i < k; i++ {
        numerator := (4*float64(i) + 2) * (4*float64(i) + 2)
        denominator := (4*float64(i) + 1) * (4*float64(i) + 3)
        product *= numerator / denominator
    }

    return product
}

func main() {
    var k int

    // Input nilai K
    fmt.Print("Nilai K = ")
    fmt.Scan(&k)

    // Hitung hampiran akar 2
    approxRoot2 := calculateApproximation(k)
  
    // Cetak hasil dengan 10 angka di belakang koma
    fmt.Printf("Nilai akar 2 = %.10f\n", approxRoot2)
}
```

>Output
>![](gambar12.png)


### Soal 1 - 2C

PT POS membutuhkan aplikasi perhitungan biaya kirim berdasarkan berat parsel. Maka,  
buatlah program BiayaPos untuk menghitung biaya pengiriman tersebut dengan  
ketentuan sebagai berikut!  
Dari berat parsel (dalam gram), harus dihitung total berat dalam kg dan sisanya (dalam  
gram). Biaya jasa pengiriman adalah Rp. 10.000,- per kg. Jika sisa berat tidak kurang dari  
500 gram, maka tambahan biaya kirim hanya Rp. 5,- per gram saja. Tetapi jika kurang dari  
500 gram, maka tambahan biaya akan dibebankan sebesar Rp. 15,- per gram. Sisa berat  
(yang kurang dari 1kg) digratiskan biayanya apabila total berat ternyata lebih dari 10kg.

```go
package main

import (
    "fmt"
)

func main() {
    var berat int

    // Input berat paket dalam gram
    fmt.Print("Berat parsel (gram): ")
    fmt.Scan(&berat)

    // Menghitung berat dalam kg dan sisa gram
    kg := berat / 1000
    sisaGram := berat % 1000

    // Menghitung biaya berdasarkan ketentuan
    biayaKg := kg * 10000
    biayaSisa := 0

    if sisaGram > 0 {
        if sisaGram >= 500 {
            biayaSisa = sisaGram * 5
        } else {
            biayaSisa = sisaGram * 15
        }
    }

    // Jika total berat lebih dari 10 kg, biaya sisa gram digratiskan
    if kg >= 10 {
        biayaSisa = 0
    }

    totalBiaya := biayaKg + biayaSisa  

    // Menampilkan hasil perhitungan
    fmt.Printf("Detail berat: %d kg + %d gr\n", kg, sisaGram)
    fmt.Printf("Detail biaya: Rp. %d + Rp. %d\n", biayaKg, biayaSisa)
    fmt.Printf("Total biaya: Rp. %d\n", totalBiaya)
}
```

>Output
>![](gambar13.png)

#### **Penjelasan Program**

1. **Input Berat Parsel**  
    Program meminta pengguna memasukkan berat parsel dalam gram.
2. **Menghitung Berat dalam KG dan Gram**
    - Berat dalam kg dihitung dengan `berat / 1000`.
    - Sisa gram dihitung dengan `berat % 1000`.
3. **Menghitung Biaya**
    - Biaya utama dihitung dengan `kg * 10000` (Rp. 10.000 per kg).
    - Biaya sisa berat:
        - Jika sisa ≥ 500 gram → Rp. 5 per gram.
        - Jika sisa < 500 gram → Rp. 15 per gram.
    - Jika berat total ≥ 10 kg, biaya sisa **digratiskan**.
4. **Menampilkan Hasil**  
    Program menampilkan detail berat, rincian biaya, dan total biaya.

- **Program berjalan sesuai aturan soal.**  
- **Menghitung biaya pengiriman berdasarkan berat secara otomatis.**  
- **Menampilkan hasil dengan format yang rapi dan mudah dibaca.**


### Soal 2 - 2C

Diberikan sebuah nilai akhir mata kuliah (NAM) [0..100] dan standar penilaian nilai mata  
kuliah (NMK) sebagai berikut:

|       NAM        | NMR |
| :--------------: | :-: |
|      NAM>80      |  A  |
| 72.5 < NAM <= 80 | AB  |
| 65 < NAM <= 72.5 |  B  |
| 57.5 < NAM <= 65 | BC  |
| 50 < NAM <= 57.5 |  C  |
|  40 < NAM <= 50  |  D  |
|    NAM <= 40     |  E  |

Program berikut menerima input sebuah bilangan riil yang menyatakan NAM. Program  
menghitung NMK dan menampilkannya

```go
package main

import (
    "fmt"
)

func main() {
    var nam float64
    var nmk string
    fmt.Print("Nilai akhir mata kuliah: ")
    fmt.Scan(&nam)

    if nam > 80 {
        nmk = "A"
    } else if nam > 72.5 {
        nmk = "AB"
    } else if nam > 65 {
        nmk = "B"
    } else if nam > 57.5 {
        nmk = "BC"
    } else if nam > 50 {
        nmk = "C"
    } else if nam > 40 {
        nmk = "D"
    } else {
        nmk = "E"
    }

    fmt.Println("Nilai mata kuliah:", nmk)
}
```

>Output
>![](gambar14.png)

##### A. Jika nam diberikan adalah 80.1, apa keluaran dari program tersebut? Apakah eksekusi program tersebut sesuai spesifikasi soal?
**Tidak, program tersebut tidak berjalan sesuai spesifikasi soal.**  
Seharusnya `nam = 80.1` menghasilkan `NMK = "A"`, tetapi karena kesalahan dalam logika `if`, nilai akhirnya menjadi `"D"`.

##### B. Apa saja kesalahan dari program tersebut? Mengapa demikian? Jelaskan alur program  seharusnya!
Program memiliki beberapa kesalahan logika yang menyebabkan hasilnya tidak sesuai dengan spesifikasi soal. Berikut adalah kesalahan-kesalahan yang ditemukan:

1. **Setiap kondisi `if` berdiri sendiri**
    - Program menggunakan **banyak `if` tanpa `else if`**, sehingga setiap kondisi diperiksa secara **terpisah** dan dapat menimpa nilai variabel `nmk`.
    - Akibatnya, meskipun nilai `nam` memenuhi beberapa kondisi, hanya kondisi terakhir yang dieksekusi yang akan menentukan nilai `nmk`.
2. **Penulisan logika tidak sesuai dengan aturan pada tabel**
    - Dalam tabel spesifikasi soal, `NAM = 80.1` seharusnya dikategorikan sebagai **"A"**.
    - Namun, karena semua kondisi dieksekusi secara independen, nilai `nmk` terus berubah hingga akhirnya menjadi **"D"** karena kondisi `if nam > 40 { nmk = "D" }` adalah yang terakhir dieksekusi.

Kesalahan terjadi karena **tidak menggunakan `else if`**, sehingga program terus menimpa nilai `nmk`. Dalam pemrosesan kategori nilai, **hanya satu kondisi yang seharusnya dipilih**, bukan semuanya dieksekusi berurutan.
##### **Alur Program Seharusnya**
1. **Gunakan `else if` agar hanya satu kondisi yang dieksekusi.**
    - Jika nilai `NAM` lebih besar dari 80, langsung beri nilai `"A"` dan **hentikan pengecekan lebih lanjut**.
    - Jika nilai **tidak** lebih dari 80, cek apakah lebih dari 72.5, lalu beri `"AB"`, dan seterusnya.
    - Gunakan **`else` di akhir** untuk menangani kasus `NAM <= 40`.
2. **Alur yang benar untuk pengecekan `NAM`:**
    - Jika `NAM > 80` → `NMK = "A"` (berhenti di sini)
    - Jika `72.5 < NAM <= 80` → `NMK = "AB"` (berhenti di sini)
    - Jika `65 < NAM <= 72.5` → `NMK = "B"`
    - Jika `57.5 < NAM <= 65` → `NMK = "BC"`
    - Jika `50 < NAM <= 57.5` → `NMK = "C"`
    - Jika `40 < NAM <= 50` → `NMK = "D"`
    - Jika `NAM <= 40` → `NMK = "E"`

##### Perbaiki program tersebut! Ujilah dengan masukan: 93.5; 70.6; dan 49.5. Seharusnya keluaran yang diperoleh adalah ‘A’, ‘B’, dan ‘D’

```go
package main

import "fmt"

func main() {
    var nam float64
    var nmk string
    fmt.Print("Nilai akhir mata kuliah: ")
    fmt.Scanln(&nam)

    if nam > 80 {
        nmk = "A"
    } else if nam > 72.5 {
        nmk = "AB"
    } else if nam > 65 {
        nmk = "B"
    } else if nam > 57.5 {
        nmk = "BC"
    } else if nam > 50 {
        nmk = "C"
    } else if nam > 40 {
        nmk = "D"
    } else {
        nmk = "E"
    }

    fmt.Println("Nilai mata kuliah:", nmk)
}
```

>Output
>![](gambar15.png)

##### **Pengujian dengan Masukan:**

| **Input (NAM)** | **Output (NMK)** |
| --------------- | ---------------- |
| 93.5            | A                |
| 70.6            | B                |
| 49.5            | D                |

**Penjelasan Hasil:**
- **93.5** > 80 → Output **"A"**
- **70.6** di antara (65, 72.5] → Output **"B"**
- **49.5** di antara (40, 50] → Output **"D"**

- **Program sudah benar dan sesuai spesifikasi soal.**  
- **Hanya satu kondisi yang dieksekusi karena menggunakan `else if`.**

```go

package main

import (
    "fmt"
)

func main() {
    var b int
    fmt.Print("Bilangan: ")
    fmt.Scanln(&b)

    // Validasi input agar lebih dari 1
    if b <= 0 {
        fmt.Println("Bilangan harus lebih dari 0")
        return
    }

    // Mencari faktor bilangan
    fmt.Print("Faktor: ")
    count := 0
    for i := 1; i <= b; i++ {
        if b%i == 0 {
            fmt.Print(i, " ")
            count++ // Menghitung jumlah faktor
        }
    }
    fmt.Println()

    // Menentukan apakah bilangan prima
    isPrima := count == 2
    fmt.Println("Prima:", isPrima)
}
```

>Output
>![](gambar16.png)

##### **Pengujian dengan Contoh Input**

| **Input (b)** | **Output Faktor** | **Output Prima** |
| ------------- | ----------------- | ---------------- |
| 12            | 1 2 3 4 6 12      | false            |
| 7             | 1 7               | true             |

##### **Penjelasan Program**

1. **Menerima input bilangan `b`**.
2. **Memeriksa apakah `b > 0`**, jika tidak, program akan menampilkan pesan error.
3. **Mencari semua faktor bilangan** dengan iterasi dari `1` hingga `b` dan mencetaknya.
4. **Menentukan apakah `b` adalah bilangan prima** dengan memeriksa jumlah faktornya.
    - Jika jumlah faktor **tepat 2** (yaitu `1` dan `b` sendiri), maka **bilangan tersebut prima** (`true`).
    - Jika faktor lebih dari 2, maka **bukan bilangan prima** (`false`).

 - **Program sesuai dengan spesifikasi soal!**