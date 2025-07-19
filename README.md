# Tugas-SBD
sistem CRUD Resep Obat

<img width="307" height="180" alt="Screenshot 2025-07-19 173554" src="https://github.com/user-attachments/assets/5263c98b-f34b-48f8-85ca-efc5ad2735e8" />

berikut**phpmyadmin**


<img width="284" height="107" alt="Screenshot 2025-07-19 173859" src="https://github.com/user-attachments/assets/706683b3-8142-41e9-8d81-cb9545e9e7f2" />
<img width="1609" height="894" alt="Screenshot 2025-07-19 174054" src="https://github.com/user-attachments/assets/7422d112-ec94-4e3a-b14b-32ab536aae92" />




📌 Tujuan Program
Program ini adalah aplikasi desktop berbasis Java Swing yang digunakan untuk mengelola data resep obat (tambah, edit, hapus, dan tampilkan) dengan menyimpan data ke database MySQL.
________________________________________
🧱 Komponen Utama
1.	GUI (Graphical User Interface):
o	Dibuat menggunakan Java Swing (JFrame).
o	Terdiri dari input teks (JTextField) dan tabel (JTable) untuk menampilkan data.
o	Tombol: Tambah, Edit, Hapus, dan Reset.
2.	Koneksi Database:
o	Menggunakan JDBC (Java Database Connectivity).
o	Terhubung ke database MySQL lokal (medika), tabel resep.
3.	Tabel resep menyimpan 4 kolom:
o	kode_resep
o	nama_resep
o	id_kategori
o	kode_satuan
________________________________________
🔄 Fungsi Utama
1.	Tambah (btntambah):
Menyimpan data resep baru ke database.
2.	Edit (btnedit):
Memperbarui data resep berdasarkan kode_resep.
3.	Hapus (btnhapus):
Menghapus data berdasarkan kode_resep.
4.	Reset (btnreset):
Mengosongkan semua field input.
5.	Tampilkan (tampilkan):
Menampilkan seluruh isi tabel resep dari database ke tabel GUI.
6.	Klik Tabel (tabelMouseClicked):
Mengisi form input ketika salah satu baris tabel diklik.
________________________________________
🔧 Catatan Tambahan
•	Jika koneksi database gagal, atau field kosong saat input, maka akan muncul pesan kesalahan.
•	Model tabel (DefaultTableModel) digunakan untuk menampilkan data ke dalam tabel Swing (JTable).
•	Semua aksi terjadi secara langsung ke database MySQL tanpa ORM.

 <img width="786" height="536" alt="Screenshot 2025-07-19 115139" src="https://github.com/user-attachments/assets/de3395fb-ddca-4b1f-9316-f38c12b2301a" />

1.	Komentar Header
Menunjukkan informasi penulis program, dalam hal ini adalah "rafikhanz".
2.	Import Library
Program ini mengimpor berbagai library Java yang dibutuhkan untuk:
o	Menghubungkan dan berinteraksi dengan database (seperti koneksi, query, dan hasil).
o	Menangani kesalahan atau error saat berkomunikasi dengan database.
o	Menampilkan pop-up pesan ke pengguna.
o	Mengatur tampilan tabel pada GUI.
o	Mencatat log sistem jika terjadi kesalahan.
3.	Deklarasi Kelas
Kelas Resep merupakan turunan dari JFrame, artinya ini adalah sebuah tampilan atau jendela dalam aplikasi GUI.
4.	Deklarasi Model Tabel
Digunakan untuk menyimpan dan menampilkan data dalam bentuk tabel di antarmuka pengguna.
5.	Konstruktor
Saat objek Resep dibuat:
o	Komponen antarmuka (form) diinisialisasi.
o	Judul kolom tabel ditentukan (Kode Resep, Nama Resep, ID Kategori, Kode Satuan).
o	Model tabel dibuat dan diatur ke tampilan tabel.
o	Data dari database ditampilkan ke tabel melalui pemanggilan fungsi tampilkan().
Singkatnya, bagian ini adalah fondasi awal dari antarmuka pengguna untuk mengatur dan menampilkan data resep obat dari database.

<img width="1486" height="247" alt="Screenshot 2025-07-19 115642" src="https://github.com/user-attachments/assets/d5591716-8864-4093-88e6-5b568d6d028c" />

 
🔘 Fungsi: btntambahActionPerformed
Fungsi ini dijalankan ketika tombol "Tambah" diklik oleh pengguna.
________________________________________
🔁 Proses yang Terjadi:
1.	Membuka koneksi ke database
Terhubung ke database MySQL lokal dengan nama medika, menggunakan username root dan tanpa password.
2.	Menjalankan query INSERT
Mengambil nilai dari 4 field input (kode_resep, nama_resep, id_kategori, kode_satuan) lalu menyimpannya ke dalam tabel resep.
3.	Menampilkan data yang baru ditambahkan
Memanggil fungsi tampilkan() agar data terbaru langsung muncul di tabel tampilan GUI.
4.	Membersihkan field input
Memanggil fungsi reset() untuk mengosongkan kembali form input setelah data ditambahkan.
5.	Penanganan error (try-catch)
Jika terjadi kesalahan seperti field kosong atau kesalahan koneksi, maka akan muncul pop-up pesan: "ada yang belum di isi kak".
________________________________________
🎯 Kesimpulan
Fungsi ini menangani penyimpanan data resep baru ke database, sekaligus menampilkan dan mereset form, serta memberikan umpan balik jika ada kesalahan.

<img width="1281" height="268" alt="Screenshot 2025-07-19 161441" src="https://github.com/user-attachments/assets/615ee321-1abd-4968-984b-b33c320d4998" />

📝 Penjelasan Fungsi btneditActionPerformed
Fungsi ini dijalankan saat tombol Edit ditekan.

🔁 Langkah-langkah yang Dilakukan:
Membuka koneksi ke database
Aplikasi terhubung ke MySQL dengan database medika.

Menjalankan perintah UPDATE
Query SQL UPDATE digunakan untuk memperbarui data pada tabel resep.
Field yang diperbarui adalah:

nama_resep

id_kategori

kode_satuan

Pembaruan dilakukan terhadap baris yang memiliki kode_resep sesuai input.

Menampilkan ulang data
Setelah data diperbarui, fungsi tampilkan() dipanggil untuk menyegarkan tampilan tabel.

Membersihkan field input
Fungsi reset() dipanggil untuk mengosongkan kembali form input.

Menangani kesalahan
Jika terjadi kesalahan saat proses update, error akan dicatat di log dengan tingkat SEVERE.

🎯 Kesimpulan
Fungsi ini digunakan untuk mengedit data resep obat berdasarkan kode_resep, memperbarui nilai-nilai yang diinputkan, dan menyegarkan tampilan data setelah perubahan.

<img width="955" height="246" alt="Screenshot 2025-07-19 161457" src="https://github.com/user-attachments/assets/6a6a7cfd-b903-4d7b-82ac-88828d789af3" />

🧾 Penjelasan Fungsi btnhapusActionPerformed
Fungsi ini digunakan untuk menghapus data resep dari database berdasarkan kode_resep.

🔁 Proses yang Terjadi:
Membuka koneksi ke database
Terhubung ke database MySQL medika menggunakan user root.

Eksekusi Query DELETE
Query SQL dijalankan:

sql
Salin
Edit
delete from resep where kode_resep = '...'
Artinya, baris pada tabel resep yang memiliki kode_resep tertentu akan dihapus.

Refresh tampilan tabel
Memanggil fungsi tampilkan() untuk memperbarui data yang ditampilkan.

Reset form input
Form input dikosongkan menggunakan reset().

Menangani error
Jika ada kesalahan (misalnya koneksi gagal atau query error), error dicatat ke log.

📌 Kesimpulan
Fungsi ini dipakai untuk menghapus data resep obat dari database dengan mencocokkan kode_resep, dan kemudian memperbarui tampilan serta membersihkan form.

<img width="911" height="228" alt="Screenshot 2025-07-19 161516" src="https://github.com/user-attachments/assets/dd135b42-7442-4dd3-9171-104a269fd7f3" />

🧾 Penjelasan Fungsi:
🔘 btnresetActionPerformed
Fungsi ini dijalankan saat pengguna menekan tombol Reset pada antarmuka aplikasi.

java
Salin
Edit
private void btnresetActionPerformed(java.awt.event.ActionEvent evt) {
    reset();
}
Fungsi ini memanggil metode reset() untuk membersihkan seluruh field input.

🔄 Metode reset()
Metode ini mengosongkan semua field teks (input pengguna), yaitu:

java
Salin
Edit
private void reset(){
    kode_resep.setText("");
    nama_resep.setText("");
    id_kategori.setText("");
    kode_satuan.setText("");
}
💡 Artinya:
setText("") digunakan untuk menghapus isi dari setiap JTextField.

Sehingga semua input kembali kosong seperti semula.

📌 Kesimpulan
Tombol Reset digunakan untuk menghapus seluruh data yang telah diketik oleh pengguna tanpa mengubah data di database. Sangat berguna jika pengguna ingin mengisi ulang form dari awal.

<img width="648" height="389" alt="Screenshot 2025-07-19 161605" src="https://github.com/user-attachments/assets/52ddbbe6-9bd2-4780-b88b-5d89e405b896" />

Gambar tersebut menampilkan deklarasi variabel GUI (Graphical User Interface) pada aplikasi Java menggunakan Swing. Ini merupakan bagian dari desain antarmuka pengguna (biasanya otomatis dihasilkan oleh NetBeans atau IDE sejenis).

Penjelasan Komponen:
JButton (Tombol)

btnedit: Tombol untuk mengedit data.

btnhapus: Tombol untuk menghapus data.

btnreset: Tombol untuk mengosongkan input.

btntambah: Tombol untuk menambahkan data baru.

JTextField (Kolom Input Teks)

id_kategori: Input untuk ID kategori resep.

kode_resep: Input untuk kode resep.

kode_satuan: Input untuk kode satuan.

nama_resep: Input untuk nama resep.

JLabel (Label Teks Tampilan)

jLabel1 hingga jLabel6: Label yang digunakan untuk memberi judul atau keterangan pada masing-masing field/input di form.

JScrollPane

jScrollPane1: Komponen pembungkus tabel agar dapat di-scroll (digulir) jika data banyak.

JTable

tabel: Tabel yang menampilkan data resep yang tersimpan di database.

Kesimpulan:
Semua komponen ini membentuk antarmuka pengguna untuk aplikasi pengelolaan resep (seperti tambah, edit, hapus data resep), dan masing-masing komponen memiliki peran untuk menangani input, tampilan data, serta aksi tombol yang dilakukan pengguna.

<img width="934" height="396" alt="Screenshot 2025-07-19 161620" src="https://github.com/user-attachments/assets/85bc7d8e-5b67-4aba-a1a1-4510bb63d1ad" />

Gambar tersebut menunjukkan fungsi tampilkan(), yang digunakan untuk menampilkan data dari tabel resep di database ke dalam tabel GUI (JTable). Berikut penjelasan langkah-langkahnya:

🔁 1. Menghapus Semua Baris dari Tabel GUI
java
Salin
Edit
int row = tabel.getRowCount();
for(int a= 0; a<row; a++){
    model.removeRow(0);
}
Fungsi ini akan menghapus semua baris yang sudah ada di tabel tampilan (GUI) agar tidak menampilkan data ganda saat memuat ulang.

🔗 2. Menghubungkan ke Database
java
Salin
Edit
Connection cn = DriverManager.getConnection("jdbc:mysql://localhost/medika","root","");
Membuka koneksi ke database MySQL lokal bernama medika, dengan user root dan tanpa password.

📄 3. Menjalankan Query SQL
java
Salin
Edit
ResultSet rs = cn.createStatement().executeQuery("SELECT * FROM resep");
Mengambil semua data dari tabel resep.

🔁 4. Membaca dan Menampilkan Data
java
Salin
Edit
while(rs.next()) {
    String data []={rs.getString(2), rs.getString(3), rs.getString(4)};
    model.addRow(data);
}
Mengambil kolom ke-2, ke-3, dan ke-4 dari setiap baris hasil query, lalu memasukkannya ke dalam tabel GUI.

model.addRow(data) berarti menambahkan baris baru ke dalam tabel tampilan.

⚠️ 5. Penanganan Error
java
Salin
Edit
} catch (SQLException ex) {
    Logger.getLogger(Resep.class.getName()).log(Level.SEVERE, null, ex);
}
Jika terjadi error saat koneksi atau query, akan dicatat di log sistem.

Kesimpulan:
Fungsi tampilkan() digunakan untuk menyegarkan tampilan tabel di antarmuka aplikasi, dengan cara:

Menghapus data lama,

Mengambil data baru dari database,

Menampilkannya ke tabel GUI (JTable).

Ini umum digunakan setelah tambah, edit, atau hapus data agar tampilan selalu sesuai dengan isi database.

berikut **ini penambahan data**

<img width="661" height="494" alt="Screenshot 2025-07-19 161851" src="https://github.com/user-attachments/assets/9fbf56f6-f29d-47fc-822d-0dd84ab977e4" />
<img width="655" height="494" alt="Screenshot 2025-07-19 161914" src="https://github.com/user-attachments/assets/86f1e0b4-31d2-42a1-a551-14d4079b545c" />
<img width="1304" height="733" alt="Screenshot 2025-07-19 161943" src="https://github.com/user-attachments/assets/8105a219-3b07-4a19-9180-e657818bb392" />


ini **edit data**

<img width="657" height="311" alt="Screenshot 2025-07-19 162346" src="https://github.com/user-attachments/assets/7557533f-dea9-41e0-8519-22d85260861b" />
<img width="659" height="494" alt="Screenshot 2025-07-19 162400" src="https://github.com/user-attachments/assets/da97524d-0623-4b12-8228-f0a76ecb00fc" />


ini **penghapusan data**

<img width="661" height="499" alt="Screenshot 2025-07-19 162446" src="https://github.com/user-attachments/assets/cb584517-3d27-40ff-909f-a772ca357cab" />
<img width="648" height="498" alt="Screenshot 2025-07-19 162458" src="https://github.com/user-attachments/assets/b5d62762-6802-45e3-b5d1-634adf3374d2" />
<img width="1311" height="766" alt="Screenshot 2025-07-19 162526" src="https://github.com/user-attachments/assets/4525e3ec-39df-48e6-b481-936609332bdb" />


ini **reset Data**

<img width="657" height="501" alt="Screenshot 2025-07-19 162549" src="https://github.com/user-attachments/assets/176562f7-8e29-4b24-a99e-da7e9c93e20a" />
<img width="662" height="485" alt="Screenshot 2025-07-19 162608" src="https://github.com/user-attachments/assets/4d205863-b671-4711-a0ea-3e43918f5beb" />







