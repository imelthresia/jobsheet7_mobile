# ord_sederhana

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

NAMA:Imel Theresia br sembiring
kelas:3f
Nim:23760046
UTS Pemrograman Mobile

Instruksi Awal (SETUP)

Pastikan proyek ocr_sederhana sudah diinisialisasi sebagai repositori Git dan terhubung ke akun GitHub Anda.

Lakukan commit awal untuk memastikan branch main Anda bersih.
<img width="446" height="109" alt="image" src="https://github.com/user-attachments/assets/d27e8941-6742-4225-9c77-7e5e1f23828c" />
Soal 1: Modifikasi Struktur Navigasi dan Aliran

Pengubahan Navigasi Home
• Ubah ElevatedButton di HomeScreen (lib/screens/home_screen.dart) menjadi widget ListTile. • Atur ListTile: leading: Icon(Icons.camera_alt, color: Colors.blue); title: Text(’Mulai Pindai Teks Baru’). • Fungsi onTap harus menggunakan Navigator.push() untuk ke ScanScreen.

sebelum
<img width="852" height="418" alt="image" src="https://github.com/user-attachments/assets/c8fe9fbe-eff3-479d-bc83-fd500ade3248" />
sesudah Modifikasi
<img width="886" height="411" alt="image" src="https://github.com/user-attachments/assets/ac9385f5-569e-443b-b477-54d204aa3d21" />
Teks Utuh dan Navigasi Balik
 Di ResultScreen (lib/screens/result_screen.dart), hapus fungsi ocrText.replaceAll( agar hasil teks ditampilkan dengan baris baru (\n) yang utuh. • Tambahkan FloatingActionButton dengan ikon Icons.home. • Ketika tombol ditekan, navigasi harus kembali langsung ke HomeScreen menggunakan Navigator.pushAndRemoveUntil() (atau metode yang setara) untuk menghapus semua halaman di atasnya dari stack navigasi.
<img width="571" height="232" alt="image" src="https://github.com/user-attachments/assets/987d728c-3199-48e3-bec2-ab436bb09ec2" />
<img width="785" height="494" alt="image" src="https://github.com/user-attachments/assets/353c95af-8ea3-4cc4-bfe0-be6fd159c9a4" />
<img width="829" height="356" alt="image" src="https://github.com/user-attachments/assets/b30127b5-48c6-4313-8022-ae3511eb163e" />
Muncul icon camera di Home page
<img width="799" height="207" alt="image" src="https://github.com/user-attachments/assets/93c073d6-833d-4815-bd8e-1645c9bf3f3b" />
<img width="799" height="178" alt="image" src="https://github.com/user-attachments/assets/0ac30238-31df-499b-ae35-394a1ab350b2" />
Setelah melakukan scan terdapat icone home, yang ketika di klik akan kembali ke halaman home
<img width="343" height="595" alt="image" src="https://github.com/user-attachments/assets/2c3855af-a583-4d2c-a9b5-3f4b0deb1802" />
<img width="632" height="143" alt="image" src="https://github.com/user-attachments/assets/b7a6ee60-fd94-47dc-ad9f-76b2878007e3" />
<img width="774" height="85" alt="image" src="https://github.com/user-attachments/assets/d8550032-bc1e-4022-9a46-93f6fb2c2d3f" />

Soal 2: Penyesuaian Tampilan dan Penanganan State/Error

Tujuan: Memperbaiki tampilan loading dan memberikan feedback error yang lebih jelas.

Custom Loading Screen di ScanScreen (20 Poin): • Di ScanScreen (lib/screens/scan_screen.dart), modifikasi tampilan loading yang muncul sebelum kamera siap (if (!controller.value.isInitialized)) : • Latar Belakang: Scaffold(backgroundColor: Colors.grey[900]). • Isi: Di dalam Center, tampilkan Column berisi CircularProgressIndicator(colo Colors.yellow). • Di bawah indikator, tambahkan Text(’Memuat Kamera... Harap tunggu.’, style: TextStyle(color: Colors.white, fontSize: 18)).
<img width="818" height="506" alt="image" src="https://github.com/user-attachments/assets/9ed8a28a-9b71-4d9b-99d9-e57e8fedab15" />
<img width="1042" height="482" alt="image" src="https://github.com/user-attachments/assets/8afedb19-530a-4aa0-880c-875651baef27" />
Spesifikasi Pesan Error (20 Poin): • Di fungsi _takePicture() pada ScanScreen, modifikasi blok catch (e) untuk mengubah pesan error pada SnackBar. • Pesan SnackBar harus berbunyi: "Pemindaian Gagal! Periksa Izin Kamera atau coba lagi." (Hilangkan variabel error ($e)).
Modifikasi pada blok catch e untuk pesan error
<img width="846" height="306" alt="image" src="https://github.com/user-attachments/assets/3cf64e29-ce9e-4e42-b5fd-8620d556ac46" />
<img width="356" height="239" alt="image" src="https://github.com/user-attachments/assets/637f5677-e5f1-423b-9391-b9fe4dff5dcc" />
Soal 3: Implementasi Plugin Text-to-Speech Tujuan: Mengintegrasikan fitur membaca teks secara lisan menggunakan plugin flutter_tts.

Instalasi Plugin : • Tambahkan plugin flutter_tts ke dalam file pubspec.yaml (gunakan versi terbaru yang kompatibel).
<img width="726" height="302" alt="image" src="https://github.com/user-attachments/assets/8d059a6c-9dc1-4e24-bc14-50b384a8b667" />
Jalankan flutter pub get.
<img width="659" height="334" alt="image" src="https://github.com/user-attachments/assets/3dd4b0f0-7c78-4742-a8a8-0c089ed4a7cf" />
Konversi Widget dan Inisialisasi: • Ubah ResultScreen dari StatelessWidget menjadi StatefulWidget.
<img width="679" height="352" alt="image" src="https://github.com/user-attachments/assets/5d8eedc4-a967-4c1a-b709-89ec8268820a" />
Di initState(), inisialisasi FlutterTts dan atur bahasa pembacaan menjadi Bahasa Indonesia.
<img width="714" height="363" alt="image" src="https://github.com/user-attachments/assets/2c9e7639-cec3-4799-b475-bca304d8eee2" />
 Implementasikan dispose() untuk menghentikan mesin TTS saat halaman ditutup.
<img width="689" height="355" alt="image" src="https://github.com/user-attachments/assets/e01286a4-7529-4439-bb69-8a45aae162cd" />

Fungsionalitas Pembacaan:
• Tambahkan FloatingActionButton kedua di ResultScreen (atau ganti AppBar dengan action button) dengan ikon Icons.volume_up. • Ketika tombol ditekan, panggil fungsi speak() pada FlutterTts untuk membacakan seluruh isi ocrText
<img width="357" height="410" alt="image" src="https://github.com/user-attachments/assets/5881c948-7116-4236-bf1a-ef70048fe717" />
Muncul icin volume
![Uploading image.png…]()

















