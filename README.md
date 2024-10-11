# JOBSHEET 7

Nama: Wulan Maulidya P. F

Kelas: TI-3H

No. Absen: 27

NIM: 2241720174

---

## Langkah 1: Buat Project Baru
Buatlah sebuah project flutter baru dengan nama flutter_plugin_pubdev. Lalu jadikan repository di GitHub Anda dengan nama flutter_plugin_pubdev.

## Langkah 2: Menambahkan Plugin
Tambahkan plugin auto_size_text menggunakan perintah berikut di terminal

![Praktikum](/images/p_2.png)

Jika berhasil, maka akan tampil nama plugin beserta versinya di file pubspec.yaml pada bagian dependencies.

* Plugin ini akan membantu untuk menyesuaikan ukuran teks secara otomatis berdasarkan ruang yang tersedia.

## Langkah 3: Buat file red_text_widget.dart
Buat file baru bernama red_text_widget.dart di dalam folder lib lalu isi kode seperti berikut.

![Praktikum](/images/p_3.png)

* File ini digunakan untuk membuat custom widget yang nantinya dapat digunakan di seluruh aplikasi.

## Langkah 4: Tambah Widget AutoSizeText
Masih di file red_text_widget.dart, untuk menggunakan plugin auto_size_text, ubahlah kode return Container() menjadi seperti berikut.

![Praktikum](/images/p_4a.png)

Setelah Anda menambahkan kode di atas, Anda akan mendapatkan info error. Mengapa demikian? Jelaskan dalam laporan praktikum Anda!

* Terjadi error karena belum dilakukan impor package auto_size_text

**Pembetulan:**

![Praktikum](/images/p_4b.png)

* Tetap terjadi error pada text karena belum dilakukan deklarasi variabel text. Deklarasi variabel text dilakukan pada Langkah 5.
* Mengganti kode return Container() dengan kode yang menggunakan widget AutoSizeText untuk membuat teks yang dapat otomatis menyesuaikan ukurannya.

## Langkah 5: Buat Variabel text dan parameter di constructor
Tambahkan variabel text dan parameter di constructor seperti berikut.

![Praktikum](/images/p_5.png)

* Dilakukan deklarasi variabel text untuk mengatasi error yang terjadi pada langkah 4.

## Langkah 6: Tambahkan widget di main.dart
Buka file main.dart lalu tambahkan di dalam children: pada class _MyHomePageState

![Praktikum](/images/p_6.png)

* Dilakukan penambahan kode dengan mengimpor file red_text_widget.dart terlebih dahulu untuk menerapkan auto_size_text yang telah dilakukan pada file red_text_widget.dart pada Container di dalam children class _MyHomePageState.

---

# TUGAS PRAKTIKUM
## 1. Selesaikan Praktikum tersebut, lalu dokumentasikan dan push ke repository Anda berupa screenshot hasil pekerjaan beserta penjelasannya di file README.md!

## 2. Jelaskan maksud dari langkah 2 pada praktikum tersebut!

* Pada langkah 2 dilakukan penambahan plugin AutoSizeText. Plugin ini berfungsi untuk mengubah ukuran teks agar pas dengan batasnya secara otomatis. AutoSizeText berperilaku persis seperti Text. Satu-satunya perbedaan adalah mengubah ukuran teks agar sesuai dengan batasnya.

## 3. Jelaskan maksud dari langkah 5 pada praktikum tersebut!

Pada langkah 5 dilakukan penambahan kode berikut:

**final String text;**

* Deklarasi Variabel: Code ini adalah deklarasi variabel text dengan tipe data String dan menggunakan keyword final. Variabel text bersifat immutable, artinya nilainya tidak bisa diubah setelah diinisialisasi.
* Variabel ini akan menampung teks yang nantinya akan ditampilkan oleh widget AutoSizeText.
* Dengan tipe final, variabel text harus diberi nilai pada saat pembuatan objek, melalui constructor, dan nilainya tidak bisa diubah setelah itu.

**const RedTextWidget({Key? key, required this.text}) : super(key: key);**

* Constructor: Bagian ini mendefinisikan constructor untuk class RedTextWidget. Constructor digunakan untuk menginisialisasi objek baru dari class tersebut.
* Parameter text: Pada constructor ini, variabel text diset sebagai required sehingga setiap kali widget RedTextWidget diinisialisasi, parameter text harus diberikan. Hal ini memastikan bahwa setiap instance dari RedTextWidget memiliki teks yang akan ditampilkan.
* super(key: key): Kode ini digunakan untuk memanggil constructor dari superclass (StatelessWidget) dan meneruskan parameter key ke superclass. Key digunakan untuk menjaga identitas widget jika perlu untuk membandingkan dua widget atau untuk keperluan optimasi lainnya dalam Flutter.

## 4. Pada langkah 6 terdapat dua widget yang ditambahkan, jelaskan fungsi dan perbedaannya!

* Container Pertama (Dengan RedTextWidget) -> Digunakan widget custom bernama RedTextWidget, yang menampilkan teks 'You have pushed the button this many times:'. RedTextWidget menggunakan plugin AutoSizeText, yang secara **otomatis mengubah ukuran teks agar sesuai dengan ruang yang tersedia**, yaitu width: 50. Jadi, teks akan mengecil jika tidak muat dalam ruang yang disediakan.
* Container Kedua (Dengan Text) -> Digunakan widget Flutter bawaan, yaitu Text, untuk menampilkan teks yang sama 'You have pushed the button this many times:'. Widget Text ini **tidak** menyesuaikan ukuran teks secara otomatis berdasarkan ruang yang tersedia. Jika teks terlalu panjang untuk ditampilkan, maka akan tetap ditampilkan dalam satu baris tanpa modifikasi ukuran atau pemotongan.

## 5. Jelaskan maksud dari tiap parameter yang ada di dalam plugin auto_size_text berdasarkan tautan pada dokumentasi ini !

![Praktikum](/images/tgs_5.png)

**text:**

* Parameter ini adalah teks yang akan ditampilkan oleh widget. Pada kode di atas, teks ini diberikan melalui variabel text yang dideklarasikan di constructor RedTextWidget.

**style:**

* Parameter style digunakan untuk menentukan gaya teks, seperti warna, ukuran font, tebal, dan sebagainya. Pada kode di atas, gaya teks diatur menggunakan TextStyle dengan properti:
* color: Colors.red: Warna teks diatur menjadi merah.
* fontSize: 14: Ukuran font ditetapkan menjadi 14.

**maxLines:**

* Parameter maxLines berfungsi seperti yang biasa dilakukan dengan widget Teks. maxLines digunakan untuk menentukan jumlah maksimum baris yang dapat digunakan oleh teks yang ditampilkan. Pada kode tersebut, parameter maxLines: 2 di dalam widget AutoSizeText memiliki fungsi untuk menentukan bahwa teks yang ditampilkan hanya boleh menggunakan maksimal 2 baris.

**overflow:**

* Parameter overflow mengatur bagaimana teks yang terlalu panjang ditampilkan ketika ruang yang tersedia tidak cukup. Di sini, TextOverflow.ellipsis digunakan, yang berarti jika teks melebihi ruang yang disediakan atau batasan maxLines, teks akan dipotong dan digantikan dengan tiga titik (...) di akhir baris terakhir.

## 6. Kumpulkan laporan praktikum Anda berupa link repository GitHub kepada dosen!