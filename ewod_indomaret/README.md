<h1>README.md</h1>


1. **Apa perbedaan utama antara stateless dan stateful widget dalam konteks pengembangan aplikasi Flutter?**
    **Jawaban:**

    Perbedaan utama antara Stateless dan Stateful widget dalam pengembangan aplikasi Flutter adalah bagaimana mereka mengelola perubahan data dan keadaan (state) dalam aplikasi:

    * **Stateless Widget**

        Widget yang tidak memiliki keadaan internal yang dapat berubah. Ini berarti setelah dibuat, kontennya tidak dapat diperbarui atau berubah. Stateless widget cocok digunakan untuk bagian UI yang tidak perlu memperbarui tampilan berdasarkan perubahan data atau interaksi pengguna. Contohnya adalah teks statis, ikon, tombol yang tidak memiliki keadaan, dan lain sebagainya. Kinerjanya lebih efisien dibandingkan dengan Stateful widget karena tidak perlu memperbarui tampilan saat terjadi perubahan.
        
    * **Stateful Widget**

        Widget yang memiliki keadaan internal yang dapat berubah seiring waktu. Ini berarti mereka dapat memperbarui tampilan mereka sesuai dengan perubahan data atau interaksi pengguna. Stateful widget cocok digunakan untuk bagian UI yang harus merespons perubahan, seperti daftar item dinamis, formulir, atau tampilan yang bergantung pada perubahan data. Untuk mengelola keadaan internal, Stateful widget memanfaatkan State object yang terkait dengannya. State object ini dapat diperbarui tanpa mengganti seluruh widget, sehingga mengoptimalkan kinerja.<br><br>

2. **Sebutkan seluruh widget yang kamu gunakan untuk menyelesaikan tugas ini dan jelaskan fungsinya masing-masing.**

    **Jawaban:**

    * **MyApp (StatelessWidget):** widget yang mewakili aplikasi utama, digunakan sebagai root widget dari aplikasi.
    * **MaterialApp (Widget Material):** widget yang mendefinisikan aplikasi Flutter. Ini menentukan judul aplikasi, tema, dan widget beranda.
    * **MyHomePage (StatelessWidget):** widget yang mewakili halaman utama aplikasi
    * **Scaffold (Widget Material):** widget yang menyediakan struktur dasar untuk tampilan halaman, termasuk AppBar dan konten utama.
    * **AppBar (Widget Material):** widget yang menampilkan bilah atas aplikasi dengan judul.
    * **SingleChildScrollView:** widget yang memungkinkan kontennya dapat discrol, digunakan untuk mengatasi konten yang lebih besar dari layar.
    * **Padding:** widget yang menambahkan padding ke kontennya.
    * **Column:** widget yang menampilkan children (widget) secara vertikal.
    * **Text (Widget Material):** widget yang menampilkan teks dengan gaya tertentu.
    * **GridView.count (Widget Material):** widget yang menampilkan grid layout dengan jumlah kolom yang tetap.
    * **ShopCard (StatelessWidget):** widget yang mewakili card untuk tombol Lihat Item, Tambah Item, dan Logout.
    * **Material (Widget Material):** widget yang mengatur warna latar belakang dan tampilan dasar untuk kartu.
    * **InkWell**: widget yang memungkinkan area kartu menjadi responsif terhadap sentuhan pengguna, sehingga dapat mendeteksi ketika kartu ditekan.
    * **Container:** widget yang digunakan untuk mengatur konten dalam kotak dengan padding yang telah ditentukan.
    * **Center:** widget yang digunakan untuk mengatur konten di tengah kartu secara vertikal dan horizontal.
    * **Icon:** widget yang menampilkan ikon dengan parameter seperti ikon, warna, dan ukuran.
    * **SnackBar:** widget yang digunakan untuk menampilkan pesan sementara atau pemberitahuan kepada pengguna.<br><br>

3. **Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step**

    **Jawaban:**

    1. **Membuat sebuah program Flutter baru dengan tema inventory seperti tugas-tugas sebelumnya.**
        1. Pertama, saya masuk ke direktori "ewod_indomaret" di mana saya ingin menyimpan proyek Flutter tugas ini. Kemudian, saya menghasilkan proyek Flutter baru dengan nama "ewod_indomaret" menggunakan perintah "flutter create ewod_indomaret."

        2. Selanjutnya, untuk memudahkan pengorganisasian kode proyek, saya membuat file baru bernama "menu.dart" dalam direktori "ewod_indomaret/lib" untuk memisahkan bagian kode tertentu. Pada baris pertama dari file "menu.dart," saya menambahkan pernyataan "import 'package:flutter/material.dart'" untuk mengimpor pustaka Flutter yang diperlukan.

        3. Dari file "main.dart," saya memindahkan kedua class, yaitu "MyHomePage" dan "_MyHomePageState," ke dalam file "menu.dart." Setelah memindahkan class tersebut, saya menambahkan pernyataan "import 'package:ewod_indomaret/menu.dart'" ke dalam file "main.dart" sehingga file tersebut dapat mengenali class "MyHomePage" yang telah saya pindahkan ke "menu.dart."<br><br>

    2. **Membuat tiga tombol sederhana dengan ikon dan teks**

        4. Pertama-tama, saya mengubah warna tema aplikasi menjadi warna indigo dengan menambahkan kode colorScheme: ColorScheme.fromSeed(seedColor: Colors.indigo), pada file "main.dart."

        5. Selanjutnya, saya mengubah sifat widget halaman menu dari stateful menjadi stateless. Pada file "main.dart," saya mengubah MyHomePage(title: 'Flutter Demo Home Page') menjadi MyHomePage() saja.

        6. Di dalam file "menu.dart," saya melakukan perubahan serupa dengan mengubah sifat widget halaman dari stateful menjadi stateless dengan pernyataan class MyHomePage extends StatelessWidget. Saya juga memperbarui konstruktor menjadi ({Key? key}) : super(key: key); dan menghapus deklarasi final String title serta fungsi State yang ada di bawah bagian stateless.

        7. Setelah mengubah sifat widget halaman menu menjadi stateless, saya menambahkan elemen-elemen UI seperti teks dan kartu (card) untuk menampilkan tombol sederhana. Saya mulai dengan mendefinisikan tipe data dalam list, yaitu class ShopItem dengan atribut nama (name), ikon (icon), dan warna (color).

        8. Kemudian, di bawah kode MyHomePage({Key? key}) : super(key: key);, saya menambahkan tombol-tombol seperti "Lihat Item," "Tambah Item," dan "Logout."

        9. Selanjutnya, saya menambahkan kode dalam metode build pada widget Scaffold di dalam class MyHomePage untuk menampilkan AppBar, tombol-tombol yang telah ditambahkan, serta melakukan peningkatan tampilan halaman dengan menggunakan widget seperti Text, Padding, Grid, SingleChildScrollView, dan sebagainya.<br><br>
        
    3. **Memunculkan Snackbar dengan tulisan**
    
        10. Saya membuat sebuah widget Stateless baru yang bertugas untuk menampilkan kartu (card), dan selanjutnya menambahkan kode yang diperlukan untuk menampilkan Snackbar ketika kartu tersebut diklik. Di dalam widget kartu, saya menambahkan kode seperti berikut:

                `child: InkWell(
                onTap: () {
                    ScaffoldMessenger.of(context)
                    ..hideCurrentSnackBar()
                    ..showSnackBar(SnackBar(
                        content: Text("Kamu telah menekan tombol ${item.name}!")));
                },`

        11. Di sini, dengan mengatur content dalam SnackBar, saya memastikan bahwa pesan Snackbar akan menampilkan teks yang sesuai dengan soal. Selanjutnya, saya juga menambahkan widget Container untuk mengelola tata letak dari ikon dan teks di dalam kartu. Saya menggunakan properti color: item.color dalam widget Material untuk memberikan warna yang berbeda pada setiap tombol sesuai dengan item yang ditekan.
