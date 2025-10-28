# Laporan Praktikum: Implementasi CRUD API dengan Flutter

## Tujuan Praktikum
1. Memahami konsep dasar API dan REST dalam pengembangan aplikasi
2. Mengimplementasikan operasi CRUD (Create, Read, Update, Delete) menggunakan REST API
3. Memahami penggunaan package http dalam Flutter untuk komunikasi dengan API
4. Mengembangkan aplikasi Flutter yang dapat berinteraksi dengan backend service

## Dasar Teori

### API (Application Programming Interface)
API adalah sekumpulan aturan dan protokol yang memungkinkan berbagai komponen software atau sistem untuk berkomunikasi. API bertindak sebagai perantara yang memungkinkan dua aplikasi untuk berbicara satu sama lain.

### REST (Representational State Transfer)
REST adalah arsitektur software yang memberlakukan syarat-syarat tentang bagaimana API bekerja. REST menggunakan HTTP requests untuk berkomunikasi data:
- GET: Membaca data
- POST: Membuat data baru
- PUT/PATCH: Mengupdate data
- DELETE: Menghapus data

### JSON (JavaScript Object Notation)
JSON adalah format pertukaran data yang ringan, mudah dibaca oleh manusia, dan mudah di-parse oleh mesin. Dalam proyek ini, JSON digunakan sebagai format data untuk berkomunikasi dengan API.

### HTTP Package di Flutter
Package http adalah library resmi Flutter untuk melakukan HTTP requests. Package ini menyediakan cara yang mudah untuk berinteraksi dengan REST API melalui berbagai metode HTTP.

## Langkah-langkah Implementasi

### 1. Konfigurasi Project
- Menambahkan dependency http di pubspec.yaml
- Membuat model class untuk data
- Mengatur konfigurasi API

### 2. Implementasi API Service
```dart
class ApiService {
  static const String baseUrl = 'https://reqres.in/api';

  // READ (GET)
  Future<List<User>> fetchUsers() async {
    final response = await http.get(
      Uri.parse('$baseUrl/users?page=2'),
      headers: {
        'Content-Type': 'application/json; charset=UTF-8',
        'x-api-key': ApiConfig.apiKey,
      },
    );
    // ... processing response
  }
}
```

### 3. Implementasi UI
Aplikasi menggunakan Material Design dengan tema yang dikustomisasi:
```dart
MaterialApp(
  title: 'Flutter API CRUD Praktikum',
  theme: ThemeData(
    primarySwatch: Colors.blue,
    appBarTheme: const AppBarTheme(
      backgroundColor: Colors.blueAccent,
      foregroundColor: Colors.white,
    ),
    // ... konfigurasi tema lainnya
  ),
)
```

## Analisis Kode

### 1. Model User
Model User mengimplementasikan serialisasi JSON untuk memudahkan konversi data dari dan ke API.

### 2. API Service
- Menggunakan singleton pattern untuk efisiensi penggunaan resources
- Implementasi error handling untuk setiap request
- Penggunaan async/await untuk operasi asynchronous

### 3. State Management
- Menggunakan StatefulWidget untuk mengelola state aplikasi
- Implementasi Future untuk handling asynchronous data

### 4. UI Components
- Penggunaan ListView.builder untuk efisiensi rendering list
- Implementasi form validation untuk input user
- Feedback visual untuk user saat operasi CRUD

## Kesimpulan
1. Implementasi CRUD API dalam Flutter memerlukan pemahaman yang baik tentang asynchronous programming
2. Package http sangat membantu dalam implementasi komunikasi dengan REST API
3. Proper error handling sangat penting dalam pengembangan aplikasi yang berinteraksi dengan API

## Saran
1. Implementasi caching untuk meningkatkan performa aplikasi
2. Menambahkan fitur offline mode dengan local database
3. Implementasi unit testing untuk API service
4. Meningkatkan UI/UX dengan animasi dan transisi
5. Menambahkan fitur refresh dan pagination untuk list users

## Screenshot Hasil Implementasi
[Screenshot akan ditambahkan setelah implementasi selesai]


