<h1>README.md</h1>


1. **Jelaskan perbedaan antara Navigator.push() dan Navigator.pushReplacement(), disertai dengan contoh mengenai penggunaan kedua metode tersebut yang tepat!**

    **Jawaban:**

    * **Navigator.push():**
        * Metode ini digunakan untuk menambahkan halaman baru di atas tumpukan navigasi.
        * Halaman sebelumnya tetap ada dalam tumpukan navigasi.
        * Cocok digunakan ketika Anda ingin menumpuk halaman baru di atas halaman saat ini.
    * **Navigator.pushReplacement():**
        * Metode ini juga menambahkan halaman baru ke tumpukan navigasi, tetapi sekaligus menggantikan halaman saat ini dengan halaman baru.
        * Halaman sebelumnya dihapus dari tumpukan navigasi.
        * Cocok digunakan ketika Anda ingin menggantikan halaman saat ini dengan halaman baru, misalnya setelah pengguna melakukan tindakan tertentu.

        Sebagai contoh, jika memiliki halaman login dan ingin beralih ke dashboard setelah pengguna berhasil login, gunakan Navigator.pushReplacement() untuk menggantikan halaman login dengan dashboard agar pengguna tidak dapat kembali ke halaman login menggunakan tombol "back". Jika ingin menunjukkan halaman tambahan di atas halaman saat ini, gunakan Navigator.push().<br><br>

2. **Jelaskan masing-masing layout widget pada Flutter dan konteks penggunaannya masing-masing!**

    **Jawaban:**

    * **Container:**
        * Digunakan untuk mengelompokkan dan menata widget lain.
        * Mengatur ukuran, margin, padding, dan dekorasi suatu widget.
    * **Row dan Column:**
        * **Row:** Merepresentasikan baris horizontal dari widget.
        * **Column:** Merepresentasikan kolom vertikal dari widget.
        * Digunakan untuk menyusun widget secara berdampingan (Row) atau bertumpuk (Column).
    * **ListView:**
        * Digunakan untuk menampilkan daftar item yang dapat di-scroll.
        * Efisien untuk menangani daftar item yang panjang.
    * **GridView:**
        * Digunakan untuk menampilkan daftar item dalam susunan grid.
        * Berguna untuk menampilkan data dalam format yang terstruktur.
    * **Stack dan Positioned:**
        * **Stack:** Memposisikan widget di atas satu sama lain.
        * **Positioned:** Menentukan posisi suatu widget dalam tumpukan.
    * **Expanded dan Flexible:**
        * **Expanded:** Digunakan untuk mengisi ruang yang tersedia dalam parent widget.
        * **Flexible:** Memberikan kontrol lebih lanjut atas seberapa banyak ruang dapat diambil oleh widget.
    * **SizedBox:**
        * Digunakan untuk menentukan ukuran widget dalam hal lebar, tinggi, atau kedua-duanya.
    * **Card:**
        * Menyediakan bingkai untuk menampilkan informasi terkait dalam antarmuka pengguna.
    * **Wrap:**
        * Membungkus widget secara horizontal atau vertikal sesuai kebutuhan.
        * Berguna ketika jumlah item dalam baris atau kolom tidak diketahui secara pasti.
    * **Align:**
        * Menyusun widget ke posisi yang diinginkan dalam parent widget.<br><br>
        
3. **Sebutkan apa saja elemen input pada form yang kamu pakai pada tugas kali ini dan jelaskan mengapa kamu menggunakan elemen input tersebut!**

    **Jawaban:**

    * **TextFormField untuk name:**
        * **Input:** Teks (String)
        * **Validator:** Memastikan bahwa nama tidak boleh kosong.
    * **TextFormField untuk amount:**
        * **Input:** Angka (int)
        * **Validator:** Memastikan bahwa jumlah tidak boleh kosong dan harus berupa angka.
    * **TextFormField untuk description:**
        * **Input:** Teks (String)
        * **Validator:** Memastikan bahwa deskripsi tidak boleh kosong.
    * **ElevatedButton untuk Menyimpan (Save):**
        * Menggunakan _formKey untuk memvalidasi formulir sebelum menyimpan data.<br><br>
4. **Bagaimana penerapan clean architecture pada aplikasi Flutter?**

    **Jawaban:**


    Penerapan Clean Architecture dapat membantu membangun aplikasi yang lebih modular, mudah diuji, dan mudah diubah.Penting untuk dicatat bahwa penerapan Clean Architecture dapat bervariasi tergantung pada kebutuhan spesifik proyek dan preferensi tim pengembangan. Berikut langkah-langkah umum untuk menerapkan Clean Architecture pada aplikasi Flutter:

    * **Pemisahan Struktur Proyek:**
        * Pisahkan proyek menjadi modul-modul yang berbeda, biasanya:
            * **domain:** Berisi logika bisnis dan entitas domain.
            * **data:** Menangani sumber daya data seperti API atau database.
            * **presentation:** Berisi kode UI dan logika presentasi.
            * **external:** Menangani eksternal dependencies.
    * **Domain Layer:**
        * **Entities:** Definisikan entitas domain yang mewakili objek-objek inti dalam aplikasi.
        * **Use Cases (Interactors):** Implementasikan aturan bisnis dalam use case atau interaktor yang terletak di lapisan domain.
    * **Data Layer:**
        * **Repositories:** Tentukan antarmuka repositori di lapisan domain dan implementasinya di lapisan data. Repositori bertanggung jawab untuk mendapatkan data dari berbagai sumber seperti API atau database.
        * **Data Sources:** Buat kelas-kelas yang bertanggung jawab untuk berkomunikasi dengan sumber daya data, seperti API clients atau local database.
    * **Presentation Layer:**
        * **Screens dan Widgets:** Tempatkan UI dan logika presentasi di lapisan ini.
        * **ViewModels atau Blocs:** Gunakan ViewModel atau BLoC untuk mengelola state dan logika presentasi. Mereka berkomunikasi dengan use case dari lapisan domain.
    * **Dependency Injection:**
        * Gunakan teknik injeksi dependensi untuk menyediakan dependensi pada kelas-kelas yang membutuhkannya. Flutter memiliki paket seperti get_it atau provider yang dapat membantu mengimplementasikan injeksi dependensi.
    * **Unit Testing dan Mocking:**
        * Uji unit pada komponen-komponen seperti use cases di lapisan domain.
        * Gunakan mocking untuk mengisolasi unit tes dari dependensi eksternal.<br><br>

5. **Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step!**

    **Jawaban:**

    * **Membuat minimal satu halaman baru pada aplikasi, yaitu halaman formulir tambah item baru dengan ketentuan sebagai berikut:**
        * **Memakai minimal tiga elemen input, yaitu name, amount, description. Tambahkan elemen input sesuai dengan model pada aplikasi tugas Django yang telah kamu buat.**

        * **Memiliki sebuah tombol Save.**

        * **Setiap elemen input di formulir juga harus divalidasi dengan ketentuan sebagai berikut:**

            1. **Setiap elemen input tidak boleh kosong.**
            2. **Setiap elemen input harus berisi data dengan tipe data atribut modelnya.**
        1. Saya telah membuat sebuah berkas baru bernama shoplist_form.dart di dalam direktori lib. Di dalam berkas ini, saya menambahkan kode yang diperlukan untuk membuat sebuah form sederhana.
        
        2. Untuk mengelola state form, validasi input, dan penyimpanan data form, saya membuat sebuah variabel baru yang saya namakan _formKey. Kemudian, saya mengintegrasikan _formKey ini ke dalam atribut key milik widget Form.

        3. Kemudian, saya mulai mengisi widget Form dengan field-field yang diperlukan. Saya membuat variabel String _name, int _amount, dan String _description untuk menyimpan input dari masing-masing field yang akan dibuat. Setiap field ini diwakili oleh widget TextFormField yang juga dibungkus dalam widget Padding dan ditempatkan sebagai salah satu children dari widget Column. Selain itu, saya mengatur atribut crossAxisAlignment untuk mengatur alignment children dari Column agar tampilan terlihat rapi.

        4. Selanjutnya, saya menambahkan kode validator untuk setiap TextFormField. Validator ini bertugas untuk melakukan validasi isi dari TextFormField dan akan mengembalikan pesan error dalam bentuk String jika terdapat error. Implementasi validator ini mengikuti prinsip null-safety dan harus sesuai dengan tipe data atribut model yang digunakan.

        5. Selanjutnya, saya memasukkan tombol "Save" sebagai child widget di dalam Column. Tombol ini ditempatkan dalam sebuah wrapper widget Padding dan Align, sehingga akan memunculkan sebuah pop-up saat tombol tersebut ditekan.

    * **Mengarahkan pengguna ke halaman form tambah item baru ketika menekan tombol Tambah Item pada halaman utama.**
        1. Pada widget ShopItem dalam berkas menu.dart yang telah saya buat, saya telah mengatur kode yang terdapat pada atribut onTap dari InkWell agar dapat melakukan navigasi ke route lain. Untuk melakukan navigasi ini, saya menggunakan metode Navigator.push, yang memungkinkan pengguna untuk berpindah dari halaman utama ke halaman tambah item dengan menekan tombol Tambah Item.
    * **Memunculkan data sesuai isi dari formulir yang diisi dalam sebuah pop-up setelah menekan tombol Save pada halaman formulir tambah item baru.**
        1. Untuk mengatur tindakan yang diambil saat tombol "Save" ditekan, saya menambahkan fungsi showDialog() pada atribut onPressed() tombol tersebut. Pada fungsi showDialog(), saya menampilkan widget AlertDialog yang akan muncul ketika tombol "Save" ditekan. Selain itu, saya juga menambahkan sebuah fungsi untuk mereset form setelah data disimpan.
    * **Membuat sebuah drawer pada aplikasi dengan ketentuan sebagai berikut:**
        * **Drawer minimal memiliki dua buah opsi, yaitu Halaman Utama dan Tambah Item.**
        * **Ketika memiih opsi Halaman Utama, maka aplikasi akan mengarahkan pengguna ke halaman utama.**
        * **Ketika memiih opsi (Tambah Item), maka aplikasi akan mengarahkan pengguna ke halaman form tambah item baru.**

            1. Saya membuat sebuah berkas baru bernama left_drawer.dart di dalam direktori widgets yang baru saya buat. Di dalam berkas ini, saya menambahkan kode untuk membuat komponen yang disebut LeftDrawer.

            2. Selanjutnya, saya melakukan impor untuk halaman-halaman yang ingin saya tambahkan ke dalam menu Drawer. Ini mencakup pengaturan navigasi untuk kembali ke halaman utama dan menambahkan item baru.

            3. Setelah berhasil melakukan impor, saya mengkonfigurasi routing untuk halaman-halaman yang telah saya impor menggunakan metode Navigator.pushReplacement().

            4. Selanjutnya, saya menghias drawer dengan menambahkan kode untuk membuat drawer header yang sesuai dengan tampilan yang diinginkan.

            5. Terakhir, saya melakukan refactoring dengan membuat sebuah berkas baru yang saya beri nama shop_card.dart, dan berkas ini saya tempatkan di dalam direktori widgets. Di dalam berkas shop_card.dart, saya memindahkan seluruh konten dari widget ShopItem yang sebelumnya berada dalam berkas menu.dart. Selanjutnya, saya mengimpor halaman shoplist_form.dart ke dalam berkas shop_card.dart untuk memastikan dependensi yang dibutuhkan tersedia. Selain itu, saya juga mengimpor berkas shop_card.dart ke dalam berkas menu.dart, sehingga dapat menggunakan widget ShopItem yang telah dikeluarkan dari berkas menu.dart. Sebagai tahap terakhir, saya melakukan pemindahan berkas menu.dart dan shoplist_form.dart ke dalam folder screens yang baru saya buat, untuk menjaga struktur direktori yang lebih terorganisir.