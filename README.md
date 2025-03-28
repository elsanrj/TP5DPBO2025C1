# Janji
Saya Elsa Nurjanah dengan NIM 2306026 mengerjakan Tugas Praktikum 5 dalam mata kuliah Desain dan Pemrograman Berorientasi Objek untuk keberkahanNya maka saya tidak melakukan kecurangan seperti yang telah dispesifikasikan. Aamiin.

# Alur Program
Program terdiri dari dua Kelas dan satu Database

## **1. Database Mahasiswa**
`mahasiswa` dari `db_mahasiswa` merepresentasikan data seorang mahasiswa dengan atribut berikut:
- `nim: str` -> Nomor Induk Mahasiswa
- `nama: str` -> Nama mahasiswa
- `jenisKelamin: str` -> Jenis kelamin mahasiswa
- `jalurMasuk: str` -> Jalur penerimaan mahasiswa (SNBP/SNBT/Mandiri)

## **2. Kelas Database**
`Database.java` digunakan untuk menangani koneksi ke database MySQL dan menjalankan perintah SQL dengan atribut berikut:
- `connection : Connection` -> Objek koneksi ke database.
- `statement : Statement` -> Objek untuk mengeksekusi query SQL.

Methods
- `Database()` -> Konstruktor yang membuat koneksi ke database menggunakan `JDBC`
- `selectQuery(String sql)` -> Menjalankan query SELECT dan mengembalikan hasil dalam ResultSet.
- `insertUpdateDeleteQuery(String sql)` -> Menjalankan query INSERT, UPDATE, atau DELETE.

## **3. Kelas Menu**
`Menu.java` adalah aplikasi GUI berbasis Java Swing yang memungkinkan pengguna untuk mengelola data mahasiswa. Aplikasi ini memungkinkan pengguna untuk menambahkan, memperbarui, dan menghapus data mahasiswa yang disimpan dalam `db_mahasiswa`. Data mahasiswa ditampilkan dalam `JTable`, yang diperbarui setiap kali ada perubahan.

Program terdiri dari beberapa komponen utama:
- **JFrame**: Sebagai jendela utama aplikasi.
- **JTable**: Untuk menampilkan daftar mahasiswa.
- **JTextField**: Untuk menginput NIM dan Nama mahasiswa.
- **JComboBox**: Untuk memilih jenis kelamin mahasiswa.
- **JRadioButton**: Untuk memilih jalur masuk mahasiswa (SNBP, SNBT, Mandiri).
- **JButton**: Untuk menambahkan, memperbarui, menghapus, dan membatalkan aksi input.

## **Fitur Utama Program**

### **a. Menampilkan Data Awal**
Saat program dijalankan, `mahasiswa` dari `db_mahasiswa` dimuat ke dalam `JTable`.

### **b. Menambahkan Data Mahasiswa**
1. Pengguna mengisi **NIM**, **Nama**, memilih **Jenis Kelamin**, dan **Jalur Masuk**.
2. Klik tombol **"Add"**, data baru ditambahkan ke `mahasiswa` dengan query `INSERT`.
3. Validasi data baru, apakah kolom sudah terisi semua dan NIM tidak duplikasi.
4. Jika syarat tidak dipenuhi tampilkan pesan peringatan.
5. Tabel diperbarui dengan memanggil `setTable()`.
6. Form input dikosongkan dengan `clearForm()`.
7. Notifikasi sukses ditampilkan.

### **c. Memperbarui Data Mahasiswa**
1. Pengguna memilih baris dalam `JTable`, yang secara otomatis mengisi formulir input.
2. Tombol **"Add"** berubah menjadi **"Update"**.
3. Pengguna dapat mengubah data dan klik **"Update"**.
4. Data dalam `mahasiswa` diperbarui dengan query `UPDATE` dengan **id** berdasarkan **NIM** mahasiswa yang diklik.
5. Validasi data baru, apakah kolom sudah terisi semua.
6. Jika syarat tidak dipenuhi tampilkan pesan peringatan.
7. Tabel diperbarui dengan memanggil `setTable()`.
8. Form input dikosongkan dengan `clearForm()`.
9. Notifikasi sukses ditampilkan.

### **d. Menghapus Data Mahasiswa**
1. Pengguna memilih baris dalam `JTable`, yang secara otomatis mengisi formulir input.
2. Tombol **"Delete"** muncul.
3. Jika diklik, akan muncul konfirmasi.
4. Jika konfirmasi "Yes", data dalam `mahasiswa` dihapus dengan query `DELETE` dengan **id** berdasarkan **NIM** mahasiswa yang diklik.
5. Tabel diperbarui dengan memanggil `setTable()`.
6. Form input dikosongkan dengan `clearForm()`.
7. Notifikasi sukses ditampilkan.

### **e. Membatalkan Aksi Input**
1. Klik tombol **"Cancel"** akan mengosongkan form input.
2. Tombol **"Update"** kembali menjadi **"Add"**.
3. Tombol **"Delete"** disembunyikan kembali.

## **Implementasi Event Handling**
- `ActionListener` digunakan pada tombol **Add/Update**, **Delete**, dan **Cancel**.
- `MouseAdapter` digunakan untuk menangani klik pada tabel, memungkinkan pemilihan dan pengisian otomatis form input.

# Dokumentasi
## 1. Insert
### Input data

![Main](https://github.com/elsanrj/TP5DPBO2025C1/blob/main/Dokumentasi/1.1_add.png?raw=true)

### Data masuk ke database

![Main](https://github.com/elsanrj/TP5DPBO2025C1/blob/main/Dokumentasi/1.2_addResult.png?raw=true)

## 2. Update
### Edit data

![Main](https://github.com/elsanrj/TP5DPBO2025C1/blob/main/Dokumentasi/1.3_update.png?raw=true)

### Data diperbarui di database

![Main](https://github.com/elsanrj/TP5DPBO2025C1/blob/main/Dokumentasi/1.4_updateResult.png?raw=true)

## 3. Delete
### Delete data

![Main](https://github.com/elsanrj/TP5DPBO2025C1/blob/main/Dokumentasi/1.5_delete.png?raw=true)

### Data terhapus dari database

![Main](https://github.com/elsanrj/TP5DPBO2025C1/blob/main/Dokumentasi/1.6_deleteResult.png?raw=true)

##  4. Warning
### Add NIM duplikasi

![Main](https://github.com/elsanrj/TP5DPBO2025C1/blob/main/Dokumentasi/2.1_NIMwarning.png?raw=true)

### Add kolom kosong

![Main](https://github.com/elsanrj/TP5DPBO2025C1/blob/main/Dokumentasi/2.3_emptyAddWarning.png?raw=true)

### Update kolom kosong

![Main](https://github.com/elsanrj/TP5DPBO2025C1/blob/main/Dokumentasi/2.2_emptyUpdateWarning.png?raw=true)
