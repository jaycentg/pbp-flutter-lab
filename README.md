# Penjelasan Tugas 7 PBP

## Identitas
Nama    : Jaycent Gunawan Ongris<br>
NPM     : 2106750231<br>
Kelas   : F

## Jawaban dari Pertanyaan
### Stateless dan Stateful Widget
*Stateless widget* merupakan *widget* yang statis atau tidak dapat diubah *state*-nya sekali di-*built*,
sedangkan *stateful widget* merupakan *widget* yang dinamis atau dapat berubah-ubah *state*-nya dalam
sekali *built*. *Widget* yang termasuk ke *stateless widget* seperti `Text`, `Icon`, dan lainnya
bersifat *immutable* atau tidak dapat berubah. Sementara itu, *widget* yang termasuk ke *stateful widget*
seperti `CheckBox`, `RadioButton`, `TextField`, dan lainnya bersifat *mutable* atau dapat berubah. Selain
itu, perbedaan dari *stateless widget* dan *stateful widget* terdapat pada *method* yang di-*override* dan 
apa yang di-*return*. Untuk membuat *stateless widget*, perlu dilakukan *override method* `build()` yang
akan me-*return* `Widget`, sedangkan untuk membuat *stateful widget*, perlu dilakukan *override method* 
`CreateState()` yang akan me-*return* `State`.

### Widget yang Digunakan
Pada proyek ini, berikut *widget* yang saya gunakan dan fungsinya:
1. `Scaffold`: *widget* utama yang menjadi struktur *layout* halaman aplikasi dan sebagai 
wadah untuk menampung semua *widget* lainnya pada halaman aplikasi
2. `AppBar`: *widget* yang berfungsi untuk menampilkan *app bar* sebuah halaman aplikasi, umumnya
diletakkan pada bagian paling atas dari sebuah halaman aplikasi dan dapat berisi *widget* lain
3. `Text`: *widget* yang berfungsi untuk menampilkan teks pada halaman aplikasi
4. `Center`: *widget* yang berfungsi untuk menampilkan *child widget*-nya menjadi di tengah
5. `Column`: *widget* yang berfungsi untuk menampilkan *children widget*-nya secara vertikal
6. `Row`: *widget* yang berfungsi untuk menampilkan *children widget*-nya secara horizontal
7. `FloatingActionButton`: *widget* yang berfungsi untuk menampilkan tombol yang dapat mengeksekusi suatu
fungsi tertentu ketika ditekan oleh pengguna
8. `Icon`: *widget* yang berfungsi untuk menampilkan *icon* tertentu yang sudah *predefined*
9. `MaterialApp`: *widget* yang dijalankan pertama kali ketika eksekusi fungsi `main()` dan berfungsi 
untuk *wrapping* *widget* lain yang diimplementasikan dengan `Material Design` pada halaman aplikasi

### setState()
`setState()` berfungsi untuk menginformasikan *widget* bahwa terdapat perubahan pada *state* aplikasi sehingga
*widget* akan dimuat ulang berdasarkan *state* yang baru. Fungsi ini hanya dapat digunakan pada *stateful
widget*. Secara umum, variabel yang akan terdampak akibat fungsi ini adalah variabel yang ingin diubah 
nilainya agar *state*-nya berbeda. Pada aplikasi ini, variabel yang terdampak akibat fungsi ini adalah 
`_counter`, karena kita akan menaikkan dan menurunkan *counter* tersebut.

### Const dan Final
*Keyword* `final` berfungsi untuk menandai bahwa nilai dari suatu variabel tidak akan pernah berubah selama
jalannya aplikasi dan tidak ada operasi yang dapat mengubah nilai tersebut. Dengan menggunakan *keyword* `final`,
proses assignment untuk suatu variabel terjadi pada masa *run-time*. Sementara itu, konsep dari *keyword* `const`
mirip dengan `final`, hanya saja `const` akan membuat variabel menjadi *compile-time constant*, atau proses
*assignment* pada variabel tersebut akan terjadi pada masa *compile-time*.

### Tahap-Tahap Implementasi Checklist
Tahapan yang saya lakukan dalam mengimplementasikan checklist:
1. Membuat suatu proyek Flutter dengan nama `counter_7`.
2. Mengubah `title` pada `MaterialApp` dan parameter `title` pada `MyHomePage` dengan string "Program Counter".
3. Menambahkan fungsi `_decrementCounter()` pada `_MyHomePageState` yang berfungsi untuk mengurangi
*counter*. Dalam fungsi tersebut, dilakukan pemanggilan fungsi `setState()` yang didalamnya diterapkan
pengecekan nilai *counter*, di mana jika *counter* tidak bernilai 0, variabel `_counter` akan dikurangi 1.
4. Membuat *floating action button* tambahan untuk mengurangi *counter*. Hal ini dilakukan dengan mengganti
nilai dari parameter `floatingActionButton` dengan sebuah `Container` yang memiliki *child* berupa `Row`
yang terdiri dari dua buah *floating action button* yang tersusun berdasarkan `spaceBetween`.
5. Melakukan modifikasi pada `FloatingActionButton` tersebut dengan mengatur `onPressed` dengan fungsi
yang sesuai, entah itu untuk menaikkan atau menurunkan counter, serta mengubah `tooltip` dan `Icon` dari
*floating action button* tersebut.
6. Melakukan modifikasi pada `Container` untuk `floatingActionButton` dengan menambahkan *padding*. Setelah
itu, menambahkan `floatingActionButtonLocation: FloatingActionButtonLocation.centerFloat,` sebagai
parameter untuk `Scaffold` untuk mengatur posisi dari *floating action button*.
7. Melakukan modifikasi pada `children` dari `Column` dengan memanfaatkan *ternary operator* pada Dart
untuk membedakan `Text` yang muncul jika *counter* bernilai ganjil ataupun genap. Jika *counter* bernilai
ganjil, akan ditambahkan parameter `style` pada *widget* `Text` dengan nilai `TextStyle(color: Colors.blue)`
untuk menyetel tulisan "GANJIL" menjadi warna biru. Sebaliknya, jika *counter* bernilai genap, akan 
ditambahkan parameter `style` pada *widget* `Text` dengan nilai `TextStyle(color: Colors.red)`untuk menyetel 
tulisan "GENAP" menjadi warna merah.
8. [BONUS] Melakukan modifikasi `children` dari `Row` pada `floatingActionButton` untuk menghilangkan tombol
*decrement counter* jika *counter* bernilai 0. Hal ini diimplementasikan dengan menambahkan potongan kode 
`if (_counter != 0)` sebelum `FloatingActionButton` untuk *decrement counter*. Artinya, `FloatingActionButton`
untuk *decrement counter* akan hilang dari layar jika *counter* bernilai 0.
9. [BONUS] Menambahkan parameter `textDirection` dengan nilai `TextDirection.rtl` untuk *reverse* 
urutan tampilan tombol, agar ketika tombol *decrement* hilang, tombol *increment* tidak berubah tempat.
10. Melakukan `add`, `commit`, dan `push` ke GitHub.

### Referensi
https://www.geeksforgeeks.org/flutter-stateful-vs-stateless-widgets/<br>
https://belajarflutter.com/perbedaan-stateful-dan-stateless-widget-di-flutter/<br>
https://medium.com/flutter-developer-indonesia/belajar-widget-widget-pada-flutter-flutter-starter-pack-part-1-7f386a02fbb6<br>
https://belajarflutter.com/struktur-widget-pada-aplikasi-flutter/<br>
https://docs.flutter.dev/development/ui/widgets<br>
https://www.depotkode.com/perbedaan-stateless-dan-stateful-pada-flutter/<br>
https://belajarflutter.com/perbedaan-final-dan-const-pada-dart-dan-flutter/<br>

# Penjelasan Tugas 8 PBP

## Identitas
Nama    : Jaycent Gunawan Ongris<br>
NPM     : 2106750231<br>
Kelas   : F

## Jawaban dari Pertanyaan
### Perbedaan `Navigator.push` dan `Navigator.pushReplacement`
Pada `Navigator.push`, halaman baru yang ingin ditampilkan kepada pengguna di-*push* secara biasa ke dalam *stack*
tanpa mengganti posisi halaman sebelumnya pada *stack*, sehingga ketika pengguna memanggil `Navigator.pop`, *top of stack*
akan di-*pop* dan halaman dapat berpindah ke halaman sebelumnya. Sementara itu, pada `Navigator.pushReplacement`, halaman
baru yang ingin ditampilkan kepada pengguna di-*push* ke *stack* dengan me-*replace* posisi halaman sebelumnya. Dengan demikian,
halaman tidak dapat berpindah ke halaman sebelumnya.

### Widget yang Digunakan
Pada proyek ini, berikut *widget* yang saya gunakan dan fungsinya:
1. `Scaffold`: *widget* utama yang menjadi struktur *layout* halaman aplikasi dan sebagai
   wadah untuk menampung semua *widget* lainnya pada halaman aplikasi
2. `AppBar`: *widget* yang berfungsi untuk menampilkan *app bar* sebuah halaman aplikasi, umumnya
   diletakkan pada bagian paling atas dari sebuah halaman aplikasi dan dapat berisi *widget* lain
3. `Text`: *widget* yang berfungsi untuk menampilkan teks pada halaman aplikasi
4. `Center`: *widget* yang berfungsi untuk menampilkan *child widget*-nya menjadi di tengah
5. `Column`: *widget* yang berfungsi untuk menampilkan *children widget*-nya secara vertikal
6. `Row`: *widget* yang berfungsi untuk menampilkan *children widget*-nya secara horizontal
7. `MaterialApp`: *widget* yang dijalankan pertama kali ketika eksekusi fungsi `main()` dan berfungsi
   untuk *wrapping* *widget* lain yang diimplementasikan dengan `Material Design` pada halaman aplikasi
8. `Expanded`: *widget* yang digunakan untuk memperluas *children widget* dari `Row`, `Column`, atau `Flex` sedemikian
    sehingga *child* tersebut mengisi tempat kosong yang tersedia
9. `Form`: *widget* yang bermanfaat dalam membungkus beberapa *form field widget* agar menjadi satu kesatuan
10. `TextFormField`: *widget* `TextField` yang terintegrasi dengan `Form`, berfungsi untuk menyediakan *field*
     bagi pengguna untuk memasukkan teks
11. `SizedBox`: *widget* berupa *box* yang bisa ditentukan ukurannya dan biasa digunakan untuk memberi jarak
     antara satu *widget* dengan *widget* lain
12. `DropdownButton`: *widget* tombol yang ketika ditekan oleh pengguna akan menampilkan *dropdown* yang dapat dipilih
13. `Align`: *widget* untuk mengatur posisi *widget* yang menjadi *child*-nya
14. `Padding`: *widget* untuk memberikan *padding* pada *widget* yang menjadi *child*-nya
15. `ListTile`: *widget* yang bersifat *single fixed-height row* yang umumnya digunakan sebagai *children* dari `ListView` atau
*column* untuk `Drawer`
16. `ListView`: *widget* *scrollable* untuk menampilkan *widget-widget* lain yang menjadi *children*-nya
17. `Dialog`: *widget* untuk menampilkan *pop up window* pada halaman aplikasi

### Jenis-Jenis Event yang Ada pada Flutter
Berikut adalah jenis-jenis *event* yang ada pada Flutter:
1. onEnter
2. onExit
3. onHover
4. onFocusChange
5. onTap
6. onPressed
7. onSaved
8. onChanged

### Cara Kerja Navigator Mengganti Halaman pada Flutter
Implementasi navigasi halaman pada Flutter memanfaatkan struktur data *stack*. *Stack* memiliki dua operasi utama,
yaitu *push* dan *pop*. Hal ini sama dengan konsep yang diterapkan pada Flutter. Halaman yang ditampilkan kepada pengguna
pada satu waktu berada pada *top of stack*. Ketika pengguna ingin berpindah ke halaman baru, dapat diterapkan
operasi *push* agar ditambahkan halaman baru pada *top of stack*. Halaman inilah yang kemudian ditampilkan kepada pengguna.
Jika pengguna ingin berpindah ke halaman sebelumnya, dapat diterapkan operasi *pop* agar halaman yang pada saat itu
berada di *top of stack* dapat dikeluarkan, sehingga halaman yang menjadi *top of stack* selanjutnya adalah halaman sebelum
halaman tersebut. Dengan demikian, pengguna dapat berpindah pada halaman sebelumnya dengan operasi ini.

### Tahap-Tahap Implementasi Checklist
Tahapan yang saya lakukan dalam mengimplementasikan checklist:
1. [BONUS] Membuat file `drawer.dart` yang berisi widget `Drawer` yang akan digunakan pada aplikasi. Drawer ini memiliki child
berupa tiga buah `ListTile` yang ketika diklik dapat memindahkan halaman saat ini ke halaman lain. Widget Drawer ini
diimplementasikan menggunakan *stateless widget*.
2. Membuat file `form.dart` yang berisi implementasi halaman form. Pada halaman ini, dibuat suatu *stateless widget* berupa
*card* budget yang akan ditampilkan pada halaman `Data Budget`. Implementasi *card* ini menggunakan `Container` yang
sudah dimodifikasi untuk menampilkan data budget sebagaimana yang telah di-*pass* pada parameter class widget ini.
3. Selanjutnya, dibuat suatu *stateful widget* untuk menyediakan form yang akan diisi oleh pengguna terkait detail
budget. Untuk implementasi form ini, widget `Form` digunakan untuk *wrap* tiga field yang diperlukan bagi pengguna
untuk menginput data, yaitu 'Judul', 'Nominal', dan 'Jenis'. Sementara itu, tombol `Simpan` diimplementasikan di luar
widget `Form` agar posisinya bisa diatur menjadi di bawah page dengan memanfaatkan widget `Expanded` dan `Align`, di mana
alignment akan diatur menjadi `bottomCenter`. Widget yang digunakan untuk memasukkan data 'Judul' dan 'Nominal' adalah 
`TextFormField`, sedangkan widget yang digunakan untuk memilih jenis budget adalah `DropdownButton`. Selanjutnya, untuk
tiap event yang terjadi pada widget tersebut, diterapkan `setState()` untuk meng-*assign* nilai yang dimasukkan pengguna
pada field ke variabel yang telah diinisialisasi.
4. Untuk implementasi tombol `Simpan`, menggunakan `TextButton`, di mana ketika tombol tersebut ditekan, akan dilakukan
validasi input pengguna pada field yang bersesuaian. Jika sudah divalidasi, input dari pengguna akan dijadikan sebagai parameter
widget `BudgetCard` seperti yang diimplementasikan pada langkah (2), untuk kemudian dimasukkan ke suatu list. Selanjutnya,
untuk memberitahu pengguna bahwa datanya sudah masuk, ditampilkan widget `Dialog` yang berisi teks 'Data telah dimasukkan'.
5. Membuat file `data.dart` untuk menampilkan `BudgetCard` yang sudah dimasukkan ke list seperti yang telah dijelaskan pada
langkah (4). Implementasi untuk menampilkan kumpulan `BudgetCard` ini memanfaatkan widget `ListView`.
6. Melakukan `add`, `commit`, dan `push` ke GitHub.

# Penjelasan Tugas 9 PBP

## Identitas
Nama    : Jaycent Gunawan Ongris<br>
NPM     : 2106750231<br>
Kelas   : F

## Jawaban dari Pertanyaan
### Pengambilan Data JSON tanpa Model
[jawab]

### Widget yang Digunakan
Pada proyek ini, berikut *widget* yang saya gunakan dan fungsinya:
1. `Scaffold`: *widget* utama yang menjadi struktur *layout* halaman aplikasi dan sebagai
   wadah untuk menampung semua *widget* lainnya pada halaman aplikasi
2. `AppBar`: *widget* yang berfungsi untuk menampilkan *app bar* sebuah halaman aplikasi, umumnya
   diletakkan pada bagian paling atas dari sebuah halaman aplikasi dan dapat berisi *widget* lain
3. `Text`: *widget* yang berfungsi untuk menampilkan teks pada halaman aplikasi
4. `Center`: *widget* yang berfungsi untuk menampilkan *child widget*-nya menjadi di tengah
5. `Column`: *widget* yang berfungsi untuk menampilkan *children widget*-nya secara vertikal
6. `Row`: *widget* yang berfungsi untuk menampilkan *children widget*-nya secara horizontal
7. `MaterialApp`: *widget* yang dijalankan pertama kali ketika eksekusi fungsi `main()` dan berfungsi
   untuk *wrapping* *widget* lain yang diimplementasikan dengan `Material Design` pada halaman aplikasi
8. `Expanded`: *widget* yang digunakan untuk memperluas *children widget* dari `Row`, `Column`, atau `Flex` sedemikian
   sehingga *child* tersebut mengisi tempat kosong yang tersedia
9. `Form`: *widget* yang bermanfaat dalam membungkus beberapa *form field widget* agar menjadi satu kesatuan
10. `TextFormField`: *widget* `TextField` yang terintegrasi dengan `Form`, berfungsi untuk menyediakan *field*
    bagi pengguna untuk memasukkan teks
11. `SizedBox`: *widget* berupa *box* yang bisa ditentukan ukurannya dan biasa digunakan untuk memberi jarak
    antara satu *widget* dengan *widget* lain
12. `DropdownButton`: *widget* tombol yang ketika ditekan oleh pengguna akan menampilkan *dropdown* yang dapat dipilih
13. `Align`: *widget* untuk mengatur posisi *widget* yang menjadi *child*-nya
14. `Padding`: *widget* untuk memberikan *padding* pada *widget* yang menjadi *child*-nya
15. `ListTile`: *widget* yang bersifat *single fixed-height row* yang umumnya digunakan sebagai *children* dari `ListView` atau
    *column* untuk `Drawer`
16. `ListView`: *widget* *scrollable* untuk menampilkan *widget-widget* lain yang menjadi *children*-nya
17. `Dialog`: *widget* untuk menampilkan *pop up window* pada halaman aplikasi

### Mekanisme Pengambilan Data hingga Ditampilkan
[jawab]

### Tahap-Tahap Implementasi Checklist
Tahapan yang saya lakukan dalam mengimplementasikan checklist:
1. 