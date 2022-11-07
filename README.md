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
jika *counter* bernilai 0. Hal ini diimplementasikan dengan menambahkan potongan kode `if (_counter != 0)`
sebelum `FloatingActionButton`. Artinya, `FloatingActionButton` akan *visible* jika `_counter != 0`.
9. [BONUS] Agar tombol dapat muncul pertama kali ketika aplikasi di-*run*, *initial value* untuk *counter*
akan diatur menjadi bernilai 1.
10. Melakukan `add`, `commit`, dan `push` ke GitHub.

### Referensi
https://www.geeksforgeeks.org/flutter-stateful-vs-stateless-widgets/
https://belajarflutter.com/perbedaan-stateful-dan-stateless-widget-di-flutter/
https://medium.com/flutter-developer-indonesia/belajar-widget-widget-pada-flutter-flutter-starter-pack-part-1-7f386a02fbb6
https://belajarflutter.com/struktur-widget-pada-aplikasi-flutter/
https://docs.flutter.dev/development/ui/widgets
https://www.depotkode.com/perbedaan-stateless-dan-stateful-pada-flutter/
https://belajarflutter.com/perbedaan-final-dan-const-pada-dart-dan-flutter/