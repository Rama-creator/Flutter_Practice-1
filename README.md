# Write and build with Flutter app, part 1 

Beberapa panduan untuk membuat aplikasi Flutter pertama. jika terbiasa dengan kode berorientasi objek dan konsep pemrograman dasar seperti variabel, loop, dan kondisional, dapat menyelesaikan tutorial ini. tidak memerlukan pengalaman sebelumnya dengan Dart, seluler, atau pemrograman web.

# Apa yang akan dibangun pada bagian pertama ?

menerapkan aplikasi sederhana yang menghasilkan nama yang diusulkan untuk perusahaan startup. Pengguna dapat memilih dan membatalkan pilihan nama, menyimpan yang terbaik. Kode dengan malas menghasilkan 10 nama sekaligus. Saat pengguna menggulir, lebih banyak nama dihasilkan. Tidak ada batasan seberapa jauh pengguna dapat menggulir.

# Apa yang akan dipelajari dibagian pertama ini ?

- Cara menulis aplikasi Flutter yang terlihat natural di iOS, Android, dan web
- Struktur dasar aplikasi Flutter
- Menemukan dan menggunakan paket untuk memperluas fungsionalitas
- Menggunakan hot reload untuk siklus pengembangan yang lebih cepat
- Bagaimana menerapkan widget stateful
- Cara membuat daftar yang tak terbatas dan dimuat dengan malas

# Apa yang akan digunakan ?

memerlukan dua perangkat lunak untuk menyelesaikan lab : Flutter SDK dan editor. Codelab ini mengasumsikan Android Studio, tetapi juuga dapat menggunakan editor pilihan.
dapat juga menjalankan codelab ini dengan menggunakan salah satu perangkat berikut:

- Perangkat fisik (Android atau iOS) yang terhubung ke komputer Anda dan disetel ke mode pengembang
- Simulator iOS (memerlukan penginstalan alat Xcode)
- Emulator Android (memerlukan penyiapan di Android Studio)
- Sebuah browser (Chrome diperlukan untuk debugging)

# Langkah pertama membuat aplikasi flutter pemula

Buat aplikasi Flutter dengan template sederhana, menggunakan petunjuk di Memulai dengan aplikasi Flutter pertama. Beri nama proyek startup_namer (bukan flutter_app)
Tip: Jika tidak melihat “New Flutter Project” sebagai opsi di IDE, pastikan telah menginstal plugin untuk Flutter dan Dart.

1. Ganti konten lib/main.dart.
Hapus semua kode dari lib/main.dart. Ganti dengan kode berikut, yang menampilkan "Hello World" di tengah layar.
Tip: Saat menempelkan kode ke aplikasi, lekukan bisa menjadi miring. hal ini dapat memperbaikinya dengan alat Flutter berikut:
Android Studio dan IntelliJ IDEA: Klik kanan kode dan pilih Reformat Code with dartfmt.
Kode VS: Klik kanan dan pilih Format Dokumen.
Terminal: Jalankan format flutter <nama file>.
  
2. Jalankan aplikasi seperti yang dijelaskan oleh IDE. dari sana akan terlihat output Android, iOS, atau web, tergantung pada perangkat.
Tip: Pertama kali menjalankan di perangkat fisik, mungkin perlu beberapa saat untuk memuat. Setelah itu, dapat menggunakan hot reload untuk pembaruan cepat. Save juga melakukan hot reload jika aplikasi sedang berjalan. Saat menjalankan aplikasi langsung dari konsol menggunakan flutter run, masukkan r untuk melakukan hot reload.
  
# Observasi
Contoh ini membuat aplikasi Material. Materi adalah bahasa desain visual yang standar di seluler dan web. Flutter menawarkan serangkaian widget Material yang kaya. Sebaiknya gunakan desain bahan-penggunaan: entri yang benar di bagian flutter file pubspec.yaml. Ini akan memungkinkan untuk menggunakan lebih banyak fitur Material, seperti kumpulan Ikon yang telah ditentukan sebelumnya.

- Metode main() menggunakan notasi panah (=>). Gunakan notasi panah untuk fungsi atau metode satu baris.
- Aplikasi ini memperluas StatelessWidget, yang menjadikan aplikasi itu sendiri sebagai widget. Di Flutter, hampir semuanya adalah widget, termasuk perataan, padding, dan tata letak.
- Widget Scaffold, dari pustaka Material, menyediakan bilah aplikasi default, dan properti badan yang menampung pohon widget untuk layar beranda. Subpohon widget bisa sangat kompleks.
- Tugas utama widget adalah menyediakan metode build() yang menjelaskan cara menampilkan widget dalam kaitannya dengan widget tingkat rendah lainnya.
- Badan untuk contoh ini terdiri dari widget Pusat yang berisi widget turunan Teks. Widget Tengah menyelaraskan subpohon widgetnya ke tengah layar.
  
# Langkah kedua Menggunakan paket eksternal
  
Pada langkah ini, akan mulai menggunakan paket sumber terbuka bernama english_words, yang berisi beberapa ribu kata bahasa Inggris yang paling sering digunakan ditambah beberapa fungsi utilitas.
  
1. File pubspec.yaml mengelola aset dan dependensi untuk aplikasi Flutter. Di pubspec.yaml, tambahkan english_words (3.1.5 atau lebih tinggi) ke daftar dependensi.
2. Saat melihat file pubspec.yaml di tampilan editor Android Studio, klik Pub get. Ini menarik paket ke dalam proyek.
   Performing Pub get juga menghasilkan file pubspec.lock secara otomatis dengan daftar semua paket yang ditarik ke dalam proyek dan nomor versinya.
3. Di lib/main.dart, impor paket baru:
    Saat mengetik, Android Studio memberi saran untuk perpustakaan yang akan diimpor. itu kemudian membuat string impor menjadi abu-abu, memberi tahu bahwa perpustakaan yang diimpor tidak digunakan (sejauh ini).
4. Gunakan paket kata bahasa Inggris untuk menghasilkan teks alih-alih menggunakan string "Hello World":
5. Jika aplikasi sedang berjalan, muat ulang untuk memperbarui aplikasi yang sedang berjalan. Setiap kali mengklik hot reload, atau menyimpan proyek, akan melihat pasangan kata yang berbeda, dipilih secara acak, di aplikasi yang sedang berjalan. Ini karena pasangan kata dihasilkan di dalam metode build, yang dijalankan setiap kali MaterialApp memerlukan rendering, atau saat mengaktifkan Platform di Flutter Inspector.

# Problem / masalah ?
Jika aplikasi tidak berjalan dengan benar, cari kesalahan ketik. Jika Anda ingin mencoba beberapa alat debugging Flutter, lihat rangkaian alat debugging dan profil DevTools. Jika perlu, gunakan kode di tautan berikut untuk kembali ke jalur semula.
  
