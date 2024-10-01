# 📚 Laporan CRUD dengan Java Swing 

Selamat datang di laporan pratikum **Pemrograman Berorientasi Objek**! 🎉😄

## 📖 Deskripsi

Laporan ini membuat aplikasi menggunakan Java Swing untuk menampilkan dan mengelola data buku dalam bentuk tabel yang mencakup ISBN, Judul buku, Tahun terbit, dan Penerbit dengan melakukan operasi CRUD  (Create, Read, Update, Delete).💻✨

## 📋 Penjelasan
1. Membuat Database baru dengan nama `Perpustakaan` dan membuat tabel `Buku` pada PostgreSQL
   ![image](https://github.com/user-attachments/assets/ce6c9373-5684-488f-b252-7c72cc9cdb70)
   
2. Menghubungkan Database PostgreSQL dan membuat koneksi baru ke tabel
   - ![image](https://github.com/user-attachments/assets/20f62c3d-3a4f-4ec5-b59e-dd288b98ad03)
   - Menambahkan library JAR PostgreSQL ke dalam proyek
   - ![image](https://github.com/user-attachments/assets/ff5931ed-98f0-49b2-a498-8a3e53a5506c)

3. Membuat Java DbUtils untuk menjembatani antara data yang diambil dari database dan tampilan tabel dalam aplikasi Java Swing
 
   ![image](https://github.com/user-attachments/assets/9925ef4d-4414-447c-94da-0164ea93e598)

4. Membuat GUI untuk menampilkan data Buku
   - Komponen yang disisipkan salah satunya yaitu button. seperti Insert, Delete dan Update agar Ketika diisi, dihapus 
maupun diperbarui data dapat ditampilkan
   
   ![image](https://github.com/user-attachments/assets/558c568a-5a53-4f3a-bcd8-10cd4ef9ff59)

5. Membuat method showTable
  - ![image](https://github.com/user-attachments/assets/148cc1cc-65f5-402e-aeff-7b80c3ddfa74)
  - Membuat TableMouseClicked
- ![image](https://github.com/user-attachments/assets/526342c5-d0dd-4488-b968-f4ca82c736eb)

8. Memasukkan data dengan button insert
   ![image](https://github.com/user-attachments/assets/50a5af54-e223-4688-b399-e3dd621c705c)

9. Memperbarui data dengan button Update
   ![image](https://github.com/user-attachments/assets/18e9aaf6-0461-4e3f-9d1a-2e5c2afb8b3c)

10. Menghapus data dengan button
   - ![image](https://github.com/user-attachments/assets/e9a68acc-8f71-4ca3-85a8-79dfa94237e9)

11. Mengosongkan semua field input menggunkan metode `Bersih`
   - ![image](https://github.com/user-attachments/assets/88459937-b623-42c3-b370-c23464b58ff3)







   









        📌 DbUtils
        . Penjelasan mengenai kelas DbUtils.
        . Metode untuk mengonversi `ResultSet` menjadi `TableModel`.
        . Langkah-Langkah 
        
        📌 Java Swing
        . Penjelasan Java Swing
        . Komponen yang digunakan dalam aplikasi.
        . Operasi CRUD menggunakan Java Swing.

## 📦DbUtils 
🔗 Kelas DbUtilsmerupakan utilitas yang diguakan untuk mengonversi objek ResultSet dari database menjadi model tabel yang dapat digunakan dalam komponen GUI, seperti tabel di Java Swing.

🔗 Metode utama dalam kelas DbUtils  yaitu resultSetToTableModel. Metode ini mengambil objek ResultSet kemudian mengonversinya menjadi objek TableModel. proses ini dilakukan untuk mengisi data dalam tabel Swing.

🔗 Langkah - langkah :
- Mengambil Metadata Menggunakan `ResultSetMetaData` untuk mendapatkan jumlah kolom dan nama kolom dari `ResultSet`.
- Melakukan Iterasi melalui kolom untuk menyimpan nama kolom dalam `Vector`.
- Melakukan loop untuk mengiterasi setiap baris dalam `ResultSet`, kemudian menyimpan nilai kolom dalam vector baru untuk setiap baris.
- Setelah semua data terkumpul, kemudian mengembalikan objek `DefaultTableModel` yang siap digunakan untuk mengisi tabel di Swing.

## 🎨Java Swing 
🔗 Java Swing adalah toolkit GUI (Graphical User Interface) yang merupakan bagian dari Java Foundation Classes (JFC). java swing juga dapat terhubung dengan database dengan mengoprasikan CRUD. 

🔗 Komponen yang digunakan  

- JFrame: jendela utama aplikasi yang menampung semua komponen lainnya.
  - Nama variabel: Mahasiswa
   
- JLabel: Menampilkan teks statis yang berfungsi sebagai label untuk field input (NIM, NAMA, PROGRAM STUDI).
  - Nama variabel: jLabel1, jLabel2, jLabel3, jLabel4
   
- JTextField: Field input untuk menerima data dari pengguna, seperti NIM, nama mahasiswa, dan program studi.
  - Nama variabel: txtNim, txtNama, txtPd

- JToggleButton : Tombol yang digunakan untuk melakukan operasi CRUD (Create, Read, Update, Delete) pada data mahasiswa.
  - Nama variabel: btnInsert, btnUpdate, btnDelete

- JTable: Menampilkan daftar mahasiswa dalam bentuk tabel, termasuk NIM, nama, dan program studi.
  - Nama variabel: tblMahasiswa
 
- JScrollPane: Menyediakan scroll bar untuk tabel mahasiswa agar pengguna dapat menggulir jika data melebihi ukuran tampilan.
  - Nama variabel: jScrollPane1
 
🔗 CRUD 
- Create (Insert)
  - Metode: btnInsertActionPerformed
  - Proses:
    1. Memeriksa apakah semua field diisi.
    2. Menghubungkan ke database menggunakan JDBC.
    3. Menyiapkan pernyataan SQL untuk menambahkan data mahasiswa baru ke tabel.
    4. Menjalankan pernyataan SQL dan melakukan commit untuk menyimpan perubahan.
    5. Menampilkan pesan sukses atau gagal kepada pengguna.
       
- Read (Show)
  - Metode: showTable
  - Proses:
    1. Menghubungkan ke database dan mengambil semua data mahasiswa.
    2. Mengatur model tabel (tblMahasiswa) untuk menampilkan hasil query.
    3. Menutup koneksi setelah data ditampilkan.
       
- Update
  - Metode: btnUpdateActionPerformed
  - Proses:
    1. Memeriksa apakah semua field diisi.
    2. Menghubungkan ke database dan menyiapkan pernyataan SQL untuk memperbarui data mahasiswa berdasarkan NIM.
    3. Menjalankan pernyataan SQL dan memberikan umpan balik kepada pengguna mengenai keberhasilan atau kegagalan pembaruan.
       
- Delete
  - Metode: btnDeleteActionPerformed
  - Proses:
    1. Mengambil NIM dari field input untuk menentukan data mana yang akan dihapus.
    2. Meminta konfirmasi dari pengguna sebelum melanjutkan penghapusan.
    3. Menghubungkan ke database dan menyiapkan pernyataan SQL untuk menghapus data mahasiswa.
    4. Menjalankan pernyataan SQL dan menutup koneksi setelah selesai.

## 📝 Kesimpulan
Laporan pratikum ini menjelaskan pengembangan aplikasi desktop menggunakan Java Swing untuk mengelola data mahasiswa. Aplikasi ini memungkinkan pengguna untuk melakukan operasi CRUD (Create, Read, Update, Delete) dengan antarmuka pengguna yang intuitif dan responsif. 
 



  
