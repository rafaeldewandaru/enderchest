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
Membuat folder baru pada lib yaitu screens dan widgets untuk mempermudah manajemen file, kemudian membuat file shoplist_form.dart untuk form yang menerima input user
~~~
import 'package:flutter/material.dart';
import '../../widgets/left_drawer.dart';
import 'package:enderchest/models/item.dart';

class ShopFormPage extends StatefulWidget {
  const ShopFormPage({super.key});

  @override
  State<ShopFormPage> createState() => _ShopFormPageState();
}

List<Item> itemList = [];

class _ShopFormPageState extends State<ShopFormPage> {
  final _formKey = GlobalKey<FormState>();
  String _name = "";
  int _price = 0;
  String _description = "";

// Global list to store products
  void _saveProduct() {
    if (_formKey.currentState!.validate()) {
      // Add product to the global list
      itemList.add(Item(
        name: _name,
        price: _price,
        description: _description,
      ));

      showDialog(
        context: context,
        builder: (context) {
          return AlertDialog(
            title: const Text('Item berhasil tersimpan'),
            content: SingleChildScrollView(
              child: Column(
                crossAxisAlignment: CrossAxisAlignment.start,
                children: [
                  Text('Nama: $_name'),
                  Text('Harga: $_price'),
                  Text('Deskripsi: $_description'),
                ],
              ),
            ),
            actions: [
              TextButton(
                child: const Text('OK'),
                onPressed: () {
                  Navigator.pop(context);
                },
              ),
            ],
          );
        },
      );

      _formKey.currentState!.reset();
    }
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Center(
          child: Text(
            'Form Tambah Item',
          ),
        ),
        backgroundColor: Colors.indigo,
        foregroundColor: Colors.white,
      ),
      body: Form(
        key: _formKey,
        child: SingleChildScrollView(
          child:
              Column(crossAxisAlignment: CrossAxisAlignment.start, children: [
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: TextFormField(
                decoration: InputDecoration(
                  hintText: "Nama Item",
                  labelText: "Nama Item",
                  border: OutlineInputBorder(
                    borderRadius: BorderRadius.circular(5.0),
                  ),
                ),
                onChanged: (String? value) {
                  setState(() {
                    _name = value!;
                  });
                },
                validator: (String? value) {
                  if (value == null || value.isEmpty) {
                    return "Nama tidak boleh kosong!";
                  }
                  return null;
                },
              ),
            ),
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: TextFormField(
                decoration: InputDecoration(
                  hintText: "Harga",
                  labelText: "Harga",
                  border: OutlineInputBorder(
                    borderRadius: BorderRadius.circular(5.0),
                  ),
                ),
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
              ),
            ),
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: TextFormField(
                decoration: InputDecoration(
                  hintText: "Deskripsi",
                  labelText: "Deskripsi",
                  border: OutlineInputBorder(
                    borderRadius: BorderRadius.circular(5.0),
                  ),
                ),
                onChanged: (String? value) {
                  setState(() {
                    // TODO: Tambahkan variabel yang sesuai
                    _description = value!;
                  });
                },
                validator: (String? value) {
                  if (value == null || value.isEmpty) {
                    return "Deskripsi tidak boleh kosong!";
                  }
                  return null;
                },
              ),
            ),
            Align(
              alignment: Alignment.bottomCenter,
              child: Padding(
                padding: const EdgeInsets.all(8.0),
                child: ElevatedButton(
                  style: ButtonStyle(
                    backgroundColor: MaterialStateProperty.all(Colors.indigo),
                  ),
                  onPressed: _saveProduct,
                  child: const Text(
                    "Save",
                    style: TextStyle(color: Colors.white),
                  ),
                ),
              ),
            ),
          ]),
        ),
      ),
    );
  }
}
~~~
Membuat juga kode untuk validasi input dari user dengan ketentuan setiap elemen input tidak boleh kosong dan setiap elemen input harus berisi data dengan tipe data atribut modelnya.
~~~
validator: (String? value) {
  if (value == null || value.isEmpty) {
    return "Nama tidak boleh kosong!";
  }
  return null;
},
~~~
~~~
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
Kemudian saya juga membuat drawer lalu menghubungkan opsi tambah item yang berada pada drawer dan halaman utama ke shoplist_form.dart
~~~
import 'package:flutter/material.dart';
import 'package:enderchest/screens/menu.dart';
import '../screens/shoplist_form.dart';
import '../screens/see_items.dart';

class LeftDrawer extends StatelessWidget {
  const LeftDrawer({super.key});

  @override
  Widget build(BuildContext context) {
    return Drawer(
      child: ListView(
        children: [
          const DrawerHeader(
            decoration: BoxDecoration(
              color: Colors.indigo,
            ),
            child: Column(
              children: [
                Text(
                  'EnderChest',
                  textAlign: TextAlign.center,
                  style: TextStyle(
                    fontSize: 30,
                    fontWeight: FontWeight.bold,
                    color: Colors.white,
                  ),
                ),
                Padding(padding: EdgeInsets.all(10)),
                Text(
                  "Store your Items in a portable chest",
                  textAlign: TextAlign.center, // Align text to center
                  style: TextStyle(
                    fontSize: 15, // Set font size to 15
                    color: Colors.white, // Set text color to white
                    fontWeight: FontWeight.normal, // Set font weight to normal
                  ),
                ),
              ],
            ),
          ),
          ListTile(
            leading: const Icon(Icons.home_outlined),
            title: const Text('Halaman Utama'),
            // Bagian redirection ke MyHomePage
            onTap: () {
              Navigator.pushReplacement(
                  context,
                  MaterialPageRoute(
                    builder: (context) => MyHomePage(),
                  ));
            },
          ),
          ListTile(
            leading: const Icon(Icons.add_shopping_cart),
            title: const Text('Tambah Item'),
            // Bagian redirection ke ShopFormPage
            onTap: () {
              Navigator.push(
                  context,
                  MaterialPageRoute(
                    builder: (context) => ShopFormPage(),
                  ));
            },
          ),
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
        ],
      ),
    );
  }
}
~~~
Menghubungkan pada halaman utama
~~~
if (item.name == "Tambah Item") {
  Navigator.push(
      context,
      MaterialPageRoute(
        builder: (context) => ShopFormPage(),
      ));
}
~~~

Implementasi Bonus
1. Membuat objek model dalam file item.dart untuk Item
~~~
class Item {
  final String name;
  final int price;
  final String description;

  Item({required this.name, required this.price, required this.description});
}
~~~

2. Membuat file baru pada screens yaitu see_items.dart untuk menampilkan semua item yang sudah ditambahkan
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

3. Mengarahkan user ke halaman tersebut jika menekan tombol Lihat Produk pada drawer
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

4. Mengarahkan user ke halaman tersebut jika menekan tombol Lihat Produk pada halaman utama
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


<details>
<summary>Tugas 9</summary>

### 9. Apakah bisa kita melakukan pengambilan data JSON tanpa membuat model terlebih dahulu? Jika iya, apakah hal tersebut lebih baik daripada membuat model sebelum melakukan pengambilan data JSON?
Kita bisa melakukan pengambilan data JSON tanpa membuat model terlebih dahulu dan langsung menggunakan data JSON yang telah di-parse untuk pengembangan dengan cepat, tetapi menggunakan model data adalah praktik yang baik untuk mempermudah pemeliharaan dan meningkatkan kejelasan kode karena data akan lebih terstruktur, terutama untuk aplikasi yang lebih besar dan kompleks.

### 10. Jelaskan fungsi dari CookieRequest dan jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.
Dalam pengembangan aplikasi Flutter, CookieRequest berperan penting dalam mengelola cookies untuk fungsi seperti mengelola session, pengguna, autentikasi, penyimpanan preferensi, dan tracking. Instance perlu dibagikan ke semua komponen di aplikasi flutter agar semua komponen aplikasi menggunakan sesi yang sama untuk berkomunikasi yang bermanfaat untuk memastikan konsistensi data, efisiensi sumber daya, serta keamanan yang lebih baik sehingga memudahkan pengembangan dan pemeliharaan aplikasi. Pendekatan ini juga mendukung konsistensi cookie melintasi siklus hidup berbagai komponen aplikasi, memudahkan debugging, dan menjaga kebijakan keamanan yang konsisten, sesuai dengan kebutuhan spesifik aplikasi dan arsitektur dari backend.

### 11. Jelaskan mekanisme pengambilan data dari JSON hingga dapat ditampilkan pada Flutter.
1. membuat lalu mengirim permintaan HTTP ke server atau API yang menyediakan data dalam format JSON, dalam konteks ini berarti web django yang sudah dibuat pada tugas sebelumnya
2. setelah mendapatkan respons JSON dari server, respons tersebut yang biasanya dalam format teks, perlu di-parse menjadi format yang bisa dipahami oleh Dart, yaitu sebagai struktur data Dart 
3. data yang diperoleh dari JSON diubah menjadi objek Dart menggunakan model data yang sudah dibuat untuk membantu dalam manajemen tipe data dan memudahkan pemeliharaan kode
4. setelah data di-parse dan diubah menjadi model, data tersebut dapat digunakan untuk membangun widget di Flutter dan menampilkan informasinya di UI

### 12. Jelaskan mekanisme autentikasi dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.
1. pada form login aplikasi Flutter, kita memasukkan data username dan password
2. data tersebut akan dikirim ke backend django dan menerimanya sebagai request login
3. django menerima data login tersebut untuk mengautentikasi pengguna berdasarkan database lalu akan mengirimkan respons ke aplikasi Flutter
4. kemudian aplikasi Flutter akan mengecek respons yang dikirimkan dari django
5. apabila request login berhasil, maka user akan diarahkan ke Home Page dan tampilkan menu pada Flutter

### 13. Sebutkan seluruh widget yang kamu pakai pada tugas ini dan jelaskan fungsinya masing-masing.

### 14. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial).
1. Menambahkan fungsi untuk login, logout, dan register (bonus) pada web django
2. Membuat halaman login.dart dan register.dart untuk keperluan autentikasi
~~~
import 'package:enderchest/screens/menu.dart';
import 'package:flutter/material.dart';
import 'package:enderchest/screens/register.dart';
import 'package:pbp_django_auth/pbp_django_auth.dart';
import 'package:provider/provider.dart';

void main() {
    runApp(const LoginApp());
}

class LoginApp extends StatelessWidget {
const LoginApp({super.key});

@override
Widget build(BuildContext context) {
    return MaterialApp(
        title: 'Login',
        theme: ThemeData(
            primarySwatch: Colors.blue,
    ),
    home: const LoginPage(),
    );
    }
}

class LoginPage extends StatefulWidget {
    const LoginPage({super.key});

    @override
    _LoginPageState createState() => _LoginPageState();
}

class _LoginPageState extends State<LoginPage> {
    final TextEditingController _usernameController = TextEditingController();
    final TextEditingController _passwordController = TextEditingController();

    @override
    Widget build(BuildContext context) {
        final request = context.watch<CookieRequest>();
        return Scaffold(
            appBar: AppBar(
                title: const Text('Login'),
            ),
            body: Container(
                padding: const EdgeInsets.all(16.0),
                child: Column(
                    mainAxisAlignment: MainAxisAlignment.center,
                    children: [
                        TextField(
                            controller: _usernameController,
                            decoration: const InputDecoration(
                                labelText: 'Username',
                            ),
                        ),
                        const SizedBox(height: 12.0),
                        TextField(
                            controller: _passwordController,
                            decoration: const InputDecoration(
                                labelText: 'Password',
                            ),
                            obscureText: true,
                        ),
                        const SizedBox(height: 24.0),
                        ElevatedButton(
                            onPressed: () async {
                                String username = _usernameController.text;
                                String password = _passwordController.text;

                                // Cek kredensial
                                // TODO: Ganti URL dan jangan lupa tambahkan trailing slash (/) di akhir URL!
                                // Untuk menyambungkan Android emulator dengan Django pada localhost,
                                // gunakan URL http://10.0.2.2/
                                final response = await request.login("http://127.0.0.1:8000/auth/login/", {
                                'username': username,
                                'password': password,
                                });
                    
                                if (request.loggedIn) {
                                    String message = response['message'];
                                    String uname = response['username'];
                                    Navigator.pushReplacement(
                                        context,
                                        MaterialPageRoute(builder: (context) => MyHomePage()),
                                    );
                                    ScaffoldMessenger.of(context)
                                        ..hideCurrentSnackBar()
                                        ..showSnackBar(
                                            SnackBar(content: Text("$message Selamat datang, $uname.")));
                                    } else {
                                    showDialog(
                                        context: context,
                                        builder: (context) => AlertDialog(
                                            title: const Text('Login Gagal'),
                                            content:
                                                Text(response['message']),
                                            actions: [
                                                TextButton(
                                                    child: const Text('OK'),
                                                    onPressed: () {
                                                        Navigator.pop(context);
                                                    },
                                                ),
                                            ],
                                        ),
                                    );
                                }
                            },
                            child: const Text('Login'),
                        ),
                        ElevatedButton(
                          onPressed:() {
                            Navigator.pushReplacement(
                              context,
                              MaterialPageRoute(builder: (context) => RegisterPage()),
                            );
                          }, 
                          child: Text("Register"))
                    ],
                ),
            ),
        );
    }
}
~~~

~~~
import 'package:flutter/material.dart';
import 'package:http/http.dart' as http;
import 'dart:convert';
import 'package:enderchest/screens/login.dart'; 

class RegisterPage extends StatefulWidget {
  const RegisterPage({Key? key}) : super(key: key);

  @override
  State<RegisterPage> createState() => _RegisterPageState();
}

class _RegisterPageState extends State<RegisterPage> {
  final TextEditingController _usernameController = TextEditingController();
  final TextEditingController _passwordController = TextEditingController();

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text("Register")),
      body: Container(
        padding: const EdgeInsets.all(16),
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            TextField(
              controller: _usernameController,
              decoration: const InputDecoration(labelText: "Username"),
            ),
            const SizedBox(height: 12),
            TextField(
              controller: _passwordController,
              decoration: const InputDecoration(labelText: "Password"),
              obscureText: true,
            ),
            const SizedBox(height: 24),
            ElevatedButton(
              onPressed: () async {
                String username = _usernameController.text;
                String password = _passwordController.text;
                try {
                  final response = await http.post(
                    Uri.parse("http://127.0.0.1:8000/auth/register/"),
                    body: {
                      'username': username,
                      'password': password,
                    },
                  );

                  final responseData = json.decode(response.body);

                  if (response.statusCode == 201) {
                    // Registration successful
                    showDialog(
                      context: context,
                      builder: (context) => AlertDialog(
                        title: const Text('Registration Successful'),
                        content: Text(responseData['message']),
                        actions: [
                          TextButton(
                            child: const Text('OK'),
                            onPressed: () {
                              Navigator.pop(context);
                              Navigator.pushReplacement(
                                context,
                                MaterialPageRoute(builder: (context) => LoginPage()), // Replace with your login page widget
                              );
                            },
                          ),
                        ],
                      ),
                    );
                  } else {
                    // Registration failed
                    showDialog(
                      context: context,
                      builder: (context) => AlertDialog(
                        title: const Text('Registration Failed'),
                        content: Text(responseData['message']),
                        actions: [
                          TextButton(
                            child: const Text('OK'),
                            onPressed: () => Navigator.pop(context),
                          ),
                        ],
                      ),
                    );
                  }
                } catch (e) {
                  // Handle any errors here
                  showDialog(
                    context: context,
                    builder: (context) => AlertDialog(
                      title: const Text('Error'),
                      content: Text(e.toString()),
                      actions: [
                        TextButton(
                          child: const Text('OK'),
                          onPressed: () => Navigator.pop(context),
                        ),
                      ],
                    ),
                  );
                }
              },
              child: const Text("Register"),
            ),
          ],
        ),
      ),
    );
  }
}
~~~

2. Membuat file item.dart untuk model yang akan saya gunakan
~~~
// To parse this JSON data, do
//
//     final item = itemFromJson(jsonString);

import 'dart:convert';

List<Item> itemFromJson(String str) => List<Item>.from(json.decode(str).map((x) => Item.fromJson(x)));

String itemToJson(List<Item> data) => json.encode(List<dynamic>.from(data.map((x) => x.toJson())));

class Item {
    String model;
    int pk;
    Fields fields;

    Item({
        required this.model,
        required this.pk,
        required this.fields,
    });

    factory Item.fromJson(Map<String, dynamic> json) => Item(
        model: json["model"],
        pk: json["pk"],
        fields: Fields.fromJson(json["fields"]),
    );

    Map<String, dynamic> toJson() => {
        "model": model,
        "pk": pk,
        "fields": fields.toJson(),
    };
}

class Fields {
    int user;
    String name;
    int amount;
    String description;
    String imageUrl;

    Fields({
        required this.user,
        required this.name,
        required this.amount,
        required this.description,
        required this.imageUrl,
    });

    factory Fields.fromJson(Map<String, dynamic> json) => Fields(
        user: json["user"],
        name: json["name"],
        amount: json["amount"],
        description: json["description"],
        imageUrl: json["image_url"],
    );

    Map<String, dynamic> toJson() => {
        "user": user,
        "name": name,
        "amount": amount,
        "description": description,
        "image_url": imageUrl,
    };
}

~~~

3. File shoplist_form.dart yang akan digunakan untuk menambahkan Item baru sudah saya implementasikan pada tugas sebelumnya sehingga dapat digunakan kembali

4. Pada folder screens sudah membuat file bernama see_items.dart yang akan menampilkan daftar semua item, namun saya lakukan perubahan dengan menambahkan GestureDetector sehingga onTap maka akan menunjukan details dari setiap item yang saya buat pada file item_details.dart
~~~
import 'package:flutter/material.dart';
import 'package:http/http.dart' as http;
import 'dart:convert';
import 'package:enderchest/models/item.dart';
import 'package:enderchest/screens/item_details.dart';
import 'package:enderchest/widgets/left_drawer.dart';

class ProductPage extends StatefulWidget {
    const ProductPage({Key? key}) : super(key: key);

    @override
    _ProductPageState createState() => _ProductPageState();
}

class _ProductPageState extends State<ProductPage> {
Future<List<Item>> fetchProduct() async {
    // TODO: Ganti URL dan jangan lupa tambahkan trailing slash (/) di akhir URL!
    var url = Uri.parse(
      'http://127.0.0.1:8000/json/');
    var response = await http.get(
        url,
        headers: {"Content-Type": "application/json"},
    );

    // melakukan decode response menjadi bentuk json
    var data = jsonDecode(utf8.decode(response.bodyBytes));

    // melakukan konversi data json menjadi object Product
    List<Item> list_product = [];
    for (var d in data) {
        if (d != null) {
            list_product.add(Item.fromJson(d));
        }
    }
    return list_product;
}

@override
Widget build(BuildContext context) {
    return Scaffold(
        appBar: AppBar(
        title: const Text('Item'),
        ),
        drawer: const LeftDrawer(),
        body: FutureBuilder(
            future: fetchProduct(),
            builder: (context, AsyncSnapshot snapshot) {
                if (snapshot.data == null) {
                    return const Center(child: CircularProgressIndicator());
                } else {
                    if (!snapshot.hasData) {
                    return const Column(
                        children: [
                        Text(
                            "Tidak ada data produk.",
                            style:
                                TextStyle(color: Color(0xff59A5D8), fontSize: 20),
                        ),
                        SizedBox(height: 8),
                        ],
                    );
                } else {
                    return ListView.builder(
                      itemCount: snapshot.data!.length,
                      itemBuilder: (_, index) {
                        return GestureDetector(
                          onTap: () {
                            Navigator.push(
                              context,
                              MaterialPageRoute(
                                builder: (context) => ItemDetailPage(item: snapshot.data![index]),
                              ),
                            );
                          },
                          child: Container(
                            margin: const EdgeInsets.symmetric(horizontal: 16, vertical: 12),
                            padding: const EdgeInsets.all(20.0),
                            child: Column(
                              mainAxisAlignment: MainAxisAlignment.start,
                              crossAxisAlignment: CrossAxisAlignment.start,
                              children: [
                                Text(
                                  "${snapshot.data![index].fields.name}",
                                  style: const TextStyle(fontSize: 18.0, fontWeight: FontWeight.bold),
                                ),
                              ],
                            ),
                          ),
                        );
                      },
                    );

                  }
                }
            }));
    }
}

~~~

5. File item_details.dart yang saya buat pada folder screens berisi kode berikut
~~~
import 'package:flutter/material.dart';
import 'package:enderchest/models/item.dart';
class ItemDetailPage extends StatelessWidget {
  final Item item;
  const ItemDetailPage({Key? key, required this.item}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Center(
        child:Padding(
          padding: EdgeInsets.all(16),
          child:Column(
            
            children: [
              Text('Name: ${item.fields.name}', style: TextStyle(fontSize: 20)),
              Text('Amount: ${item.fields.amount}', style: TextStyle(fontSize: 18)),
              Text('Description: ${item.fields.description}', style: TextStyle(fontSize: 16)),
              Image.network('${item.fields.imageUrl}'),
              SizedBox(height: 20),
              ElevatedButton(
                onPressed: () => Navigator.pop(context),
                child: Text('Back to List'),
              ),
            ],
          )

        )
      ),
    );
  }
}
~~~

</details>