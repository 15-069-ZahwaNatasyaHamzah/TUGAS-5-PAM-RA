# MyProfile & Notes App - Kotlin Multiplatform

Aplikasi manajemen catatan (Notes App) interaktif yang dibangun menggunakan **Compose Multiplatform**. Proyek ini merupakan pengembangan lebih lanjut yang mengintegrasikan sistem navigasi kompleks, manajemen data dinamis, dan profil pengguna dalam satu arsitektur MVVM yang solid.

## Fitur 

- **Bottom Navigation**: Navigasi utama dengan 3 tab:
  - **Notes**: Daftar utama semua catatan pengguna.
  - **Favorites**: Koleksi catatan yang ditandai sebagai favorit.
  - **Profile**: Informasi profil pengguna dengan fitur Dark Mode & Edit.
- **Full CRUD Notes**: 
  - Menambah catatan baru melalui **Floating Action Button (FAB)**.
  - Melihat detail catatan dengan passing `noteId`.
  - Mengedit catatan yang sudah ada.
  - Menghapus dan menandai favorit.
- **Advanced Navigation**: 
  - Implementasi `androidx.navigation.compose`.
  - Perpindahan layar dengan argument passing (Passing `noteId`).
  - Navigasi balik (Back stack) yang proper di semua layar.
- **Multi-ViewModel Arch**: 
  - `NotesViewModel`: Mengelola state daftar catatan dan logika CRUD.
  - `ProfileViewModel`: Mengelola status profil dan tema aplikasi.

## Struktur Arsitektur

### 1. Navigasi
Menggunakan **Jetpack Navigation Compose** untuk mengatur aliran aplikasi:
- `NavHost` sebagai kontainer utama.
- Rute dinamis untuk detail dan edit: `note_detail/{noteId}`.
- Integrasi `Scaffold` untuk mengelola Bottom Bar dan FAB secara global.

### 2. State Management
- **StateFlow & UI State**: Setiap perubahan pada catatan atau profil dipancarkan melalui `StateFlow` dan diobservasi oleh UI secara reaktif.
- **Lifecycle Awareness**: Menggunakan `collectAsStateWithLifecycle()` untuk efisiensi memori pada platform Android.

## Cara Menjalankan Project

1. **Persiapan Resource**: Pastikan file `profile_user.png` berada di folder `composeApp/src/commonMain/composeResources/drawable/`.
2. **Sync Project**: Lakukan *Gradle Sync* di Android Studio.
3. **Run**:
   - Untuk Android: Pilih modul `composeApp` lalu klik **Run**.
   - Untuk Desktop: Jalankan perintah `./gradlew :composeApp:run` di terminal.

## Dokumentasi Visual

| Profile pengguna | Favorite | Tambah catatan | List catatan |
| :---: | :---: | :---: | :---: |
| <img width="478" height="876" alt="image" src="https://github.com/user-attachments/assets/ae0a8424-231b-4011-8106-1f4df766aa5a" /> | <img width="486" height="882" alt="image" src="https://github.com/user-attachments/assets/ed6c3461-51e2-4928-8bb7-219b88f1c009" /> | <img width="484" height="877" alt="image" src="https://github.com/user-attachments/assets/46e80406-bce7-45d2-9c21-484d5e3b1c71" /> | <img width="490" height="876" alt="image" src="https://github.com/user-attachments/assets/5155b0ce-0e78-44dd-b15d-7edc2d90de6c" /> |



