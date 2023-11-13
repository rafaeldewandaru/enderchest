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
- Material: digunakan untuk membuat lapisan material desain yang menampilkan konten di dalamnya. Dalam konteks ini, Material digunakan sebagai latar belakang untuk setiap ShopCard.
- InkWell: digunakan untuk menambahkan efek feedback ketika pengguna menyentuh elemen ShopCard (tampilan "splash"). InkWell digunakan sebagai child untuk menangkap sentuhan pengguna.
- ScaffoldMessenger: digunakan untuk berinteraksi dengan objek Scaffold yang terkait. Dalam kode ini, ScaffoldMessenger digunakan untuk menampilkan snackbar saat pengguna menyentuh ShopCard. 
- Snackbars; digunakan untuk menampilkan pesan singkat yang memberikan umpan balik kepada pengguna.
- Container: digunakan untuk mengatur tata letak dan tampilan elemen-elemen di dalamnya (mengelola tata letak ShopCard dan memberikan jarak antar elemen).
- Column: mengatur childnya dalam satu kolom vertikal, yaitu untuk mengatur tata letak di dalam ShopCard, yang terdiri dari ikon dan teks nama item.
- Icon: digunakan untuk menampilkan ikon. Dalam konteks ini, Icon digunakan untuk menampilkan ikon item toko.
- Text: digunakan untuk menampilkan teks nama item toko di setiap ShopCard.
- Scaffold: digunakan untuk membuat tata letak aplikasi dasar dengan appBar, body, dan lainnya. Pada MyHomePage, Scaffold digunakan untuk membuat struktur dasar halaman.
- AppBar: digunakan untuk membuat bilah aplikasi di bagian atas layar, menampilkan judul aplikasi ("EnderChest") dan warna latar belakang, dan menampilkan judul di dalam AppBar.
- GridView: digunakan untuk menampilkan child dalam tata letak grid. Dalam kode ini, GridView digunakan untuk menampilkan ShopCard dalam bentuk grid.
- Padding: digunakan untuk menambahkan jarak (padding) di sekitar elemen-elemen dalam tata letak. Dalam kode ini, Padding digunakan untuk memberikan jarak di sekitar judul dan GridView.
- ListView: digunakan untuk membungkus elemen-elemen di dalam body Scaffold, sehingga pengguna dapat scroll jika kontennya terlalu panjang.

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


<details>
<summary>Tugas 8</summary>

### 4. Jelaskan perbedaan antara Navigator.push() dan Navigator.pushReplacement(), disertai dengan contoh mengenai penggunaan kedua metode tersebut yang tepat!
Navigator.push()
- digunakan untuk menambahkan rute baru ke atas stack navigasi, berarti rute baru ditumpuk di atas rute saat ini.
- membawa user ke halaman baru tanpa menghilangkan histori navigasi sebelumnya, sehingga saat user kembali, user akan kembali ke rute sebelumnya (rute di bawah rute baru).
- Contoh: dalam aplikasi e-commerce, ketika user menekan item untuk melihat detailnya dapat menggunakan Navigator.push() untuk membawa user ke halaman detail. Ketika user menekan tombol kembali, user akan kembali ke halaman daftar produk.
<br />
Navigator.pushReplacement()
- digunakan untuk menggantikan rute saat ini dengan rute baru di stack navigasi.
- mengganti halaman saat ini dengan halaman baru tanpa kemungkinan untuk kembali, sehingga saat user kembali, user tidak akan kembali ke rute sebelumnya karena telah digantikan.
- Contoh: dalam aplikasi yang memiliki proses login, setelah user berhasil masuk akan membawa user ke halaman beranda dan menghapus halaman login dari stack. Hal ini mencegah user kembali ke layar login dengan menekan tombol kembali.

### 5. Jelaskan masing-masing layout widget pada Flutter dan konteks penggunaannya masing-masing!
- Column & Row: Column mengatur elemen secara vertikal, sedangkan Row mengatur elemen secara horizontal.
- Container: Wadah untuk mengatur tata letak dan memberi styling pada elemen, misalnya padding, margin, alignment, etc.
- Stack: Digunakan untuk menumpuk widget/elemen satu di atas yang lain.
- GridView: Menampilkan elemen dalam grid yang teratur dengan bentuk tabel.
- ListView: Menampilkan elemen yang dapat di-scroll secara vertikal.
- Expanded & Flexible: Mengontrol bagian dari ruang yang tersedia yang digunakan. Expanded mengisi ruang tersedia, sedangkan Flexible memberikan lebih banyak kontrol atas faktor fleksibilitas.
- Padding: Memberikan padding di sekeliling elemen child.
- Transform: digunakan untuk mengubah ukuran dan posisi elemen child
- Align: Mengatur posisi elemen child sesuai dengan alignment yang ditentukan.
- Wrap: Membuat row atau column dan secara otomatis beralih ke row atau column berikutnya setelah ruang di row atau column saat ini habis.
- Scaffold: Memberikan struktur dasar material design seperti AppBar, Drawer, dan FloatingActionButton.
- ConstrainedBox, SizedBox, & AspectRatio: Mengontrol ukuran atau aspek rasio dari elemen childnya.



### 6. Sebutkan apa saja elemen input pada form yang kamu pakai pada tugas kali ini dan jelaskan mengapa kamu menggunakan elemen input tersebut!
1. TextFormField untuk Nama Item (_name): Digunakan untuk user input nama item. TextField adalah elemen input dasar dalam Flutter yang digunakan untuk memasukkan teks.
2. TextFormField untuk Harga Item (_price): Digunakan untuk user input harga item. Dapat menggunakan TextField karena nanti harga yang diinput akan di parse dan di validasi input berupa angka menggunakan kode
~~~
onChanged: (String? value) {
    setState(() {
      _price = int.parse(value!);
    });
  },
  validator: (String? value) {
    if (value == null || value.isEmpty) {
      return "Harga tidak boleh kosong!";
    }
    if (int.tryParse(value) == null) {
      return "Harga harus berupa angka!";
    }
    return null;
},
~~~
3. TextFormField untuk Deskripsi Item (_description): user dapat menulis deskripsi tentang item menggunakan TextField.

 
### 7. Bagaimana penerapan clean architecture pada aplikasi Flutter?
Penerapan Clean Architecture pada aplikasi Flutter mengarah pada organisasi struktural yang lebih rapi dan pembagian fokus yang terorganisir, dengan tujuan untuk mencapai modularitas dan kemudahan dalam pengujian. Sebagai contoh, dalam praktik Clean Architecture, kita dapat menciptakan direktori terpisah untuk memisahkan file .dart yang berbeda, seperti untuk screen, widget, dan lain-lain, memastikan bahwa setiap komponen memiliki lokasi khusus, yang juga memudahkan dalam manajemen dan pemeliharaan kode. Pendekatan ini membantu dalam menjaga struktur kode yang bersih dan terorganisir, sekaligus mempermudah pencarian dan perbaikan bagian tertentu dari aplikasi ketika diperlukan.


### 8. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial)
Implementasi Bonus
Membuat objek model dalam file item.dart untuk Item
~~~
class Item {
  final String name;
  final int price;
  final String description;

  Item({required this.name, required this.price, required this.description});
}
~~~
<br />
Membuat file baru pada screens yaitu see_items.dart untuk menampilkan semua item yang sudah ditambahkan
~~~
import 'package:flutter/material.dart';
import 'package:enderchest/models/item.dart'; 

class ProductListPage extends StatelessWidget {
  final List<Item> items;

  ProductListPage({Key? key, required this.items}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Daftar Item'),
      ),
      body: ListView.builder(
        itemCount: items.length,
        itemBuilder: (context, index) {
          return Card(
            child: ListTile(
              title: Text(items[index].name),
              subtitle: Text('Harga: ${items[index].price}\nDeskripsi: ${items[index].description}'),
            ),
          );
        },
      ),
    );
  }
}
~~~
<br />
Mengarahkan user ke halaman tersebut jika menekan tombol Lihat Produk pada drawer
~~~
ListTile(
  leading: const Icon(Icons.movie),
  title: const Text('Lihat Item'),
  onTap: () {
    Navigator.push(
      context,
      MaterialPageRoute(
          builder: (context) =>
              ProductListPage(items: itemList)),
    );
  },
),
~~~
<br />
Mengarahkan user ke halaman tersebut jika menekan tombol Lihat Produk pada drawer
~~~
if (item.name == "Lihat Item") {
    Navigator.push(
      context,
      MaterialPageRoute(
          builder: (context) => ProductListPage(items: itemList)),
    );
  }
~~~

</details>