# Nama  : Rafael Bismo Dewandaru
# NPM   : 2206824666
# Kelas : PBP - F

<details>
<summary>Tugas 7</summary>

### 1. Apa perbedaan utama antara stateless dan stateful widget dalam konteks pengembangan aplikasi Flutter?
Stateless Widget:
- Jenis widget yang tidak memiliki keadaan (state) internal yang dapat berubah sehingga bersifat statis, artinya tampilan atau kontennya tidak berubah seiring waktu atau berdasarkan perubahan data. Stateless widget juga lebih efisien dalam hal kinerja, karena tidak memerlukan pengelolaan keadaan.
- Cocok digunakan untuk komponen UI yang bersifat statis, seperti teks, ikon, tombol, dan elemen UI yang tidak memerlukan perubahan berdasarkan input atau data dinamis.
- Contoh stateless widget dalam Flutter: Text, Icon, Image

Stateful Widget:
- Jenis widget yang memiliki keadaan (state) internal yang dapat berubah, sehingga digunakan ketika kita perlu merender konten yang dapat berubah seiring waktu, seperti daftar item dinamis, formulir input, atau tampilan yang berinteraksi dengan data eksternal.
- Saat keadaan internal berubah, Flutter akan membangun ulang widget untuk mencerminkan perubahan tersebut, yang memungkinkan kita untuk menyimpan dan memperbarui data sesuai kebutuhan, sehingga sangat berguna untuk mengelola tampilan yang bergantung pada data dinamis.
- Contoh stateful widget dalam Flutter: ListView, TextField, DropdownButton

### 2. Sebutkan seluruh widget yang kamu gunakan untuk menyelesaikan tugas ini dan jelaskan fungsinya masing-masing.
Material: digunakan untuk membuat lapisan material desain yang menampilkan konten di dalamnya. Dalam konteks ini, Material digunakan sebagai latar belakang untuk setiap ShopCard.
InkWell: digunakan untuk menambahkan efek feedback ketika pengguna menyentuh elemen ShopCard (tampilan "splash"). InkWell digunakan sebagai child untuk menangkap sentuhan pengguna.
ScaffoldMessenger: digunakan untuk berinteraksi dengan objek Scaffold yang terkait. Dalam kode ini, ScaffoldMessenger digunakan untuk menampilkan snackbar saat pengguna menyentuh ShopCard. 
Snackbars; digunakan untuk menampilkan pesan singkat yang memberikan umpan balik kepada pengguna.
Container: digunakan untuk mengatur tata letak dan tampilan elemen-elemen di dalamnya (mengelola tata letak ShopCard dan memberikan jarak antar elemen).
Column: mengatur childnya dalam satu kolom vertikal, yaitu untuk mengatur tata letak di dalam ShopCard, yang terdiri dari ikon dan teks nama item.
Icon: digunakan untuk menampilkan ikon. Dalam konteks ini, Icon digunakan untuk menampilkan ikon item toko.
Text: digunakan untuk menampilkan teks nama item toko di setiap ShopCard.
Scaffold: digunakan untuk membuat tata letak aplikasi dasar dengan appBar, body, dan lainnya. Pada MyHomePage, Scaffold digunakan untuk membuat struktur dasar halaman.
AppBar: digunakan untuk membuat bilah aplikasi di bagian atas layar, menampilkan judul aplikasi ("EnderChest") dan warna latar belakang, dan menampilkan judul di dalam AppBar.
GridView: digunakan untuk menampilkan child dalam tata letak grid. Dalam kode ini, GridView digunakan untuk menampilkan ShopCard dalam bentuk grid.
Padding: digunakan untuk menambahkan jarak (padding) di sekitar elemen-elemen dalam tata letak. Dalam kode ini, Padding digunakan untuk memberikan jarak di sekitar judul dan GridView.
ListView: digunakan untuk membungkus elemen-elemen di dalam body Scaffold, sehingga pengguna dapat scroll jika kontennya terlalu panjang.

### 3. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial)
1. Saya generate proyek Flutter baru dengan nama enderchest, kemudian masuk ke dalam direktori proyek tersebut lalu menjalankannya
2. Pada direktori enderchest\lib saya membuat file dart baru bernama menu.dart lalu import 'package:flutter/material.dart';
3. Kemudian saya membuat tiga button sederhana dengan menambahkan beberapa kode kedalam file menu.dart dan membuat stateless widget bernama MyHomePage
4. Saya juga menambahkan kode yang ada di tutorial 6 untuk didalam Widget build, dan mengubah ShopCard menjadi stateless
5. Untuk mendapat bonus dengan mengimplementasikan warna-warna yang berbeda untuk setiap tombol; Lihat Item, Tambah Item, dan Logout, saya menambahkan attibut Color color kedalam class ShopItem, dan menggunakannya di dalam class ShopCard.
~~~
final List<ShopItem> items = [
  ShopItem("Lihat Item", Icons.checklist, Colors.blue), // Specify different colors
  ShopItem("Tambah Item", Icons.add_shopping_cart, Colors.green),
  ShopItem("Logout", Icons.logout, Colors.red),
];
~~~
</details>
