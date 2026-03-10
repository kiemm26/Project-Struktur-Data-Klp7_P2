# Sistem Deteksi Duplikasi Data Arsip

## Deskripsi Proyek

Proyek ini mengimplementasikan sistem sederhana untuk **mengelola arsip
digital serta mendeteksi data duplikat secara otomatis**. Sistem ini
memungkinkan pengguna untuk menambahkan data arsip, mencari data,
menghapus data, menampilkan seluruh data, serta mendeteksi data duplikat
berdasarkan beberapa kriteria.

Pada implementasi ini, data arsip disimpan menggunakan **struktur data
Linked List**. Struktur ini dipilih karena fleksibel untuk operasi
penyisipan data secara dinamis serta mudah diimplementasikan untuk
kebutuhan eksplorasi struktur data dasar.

Selain itu, sistem juga mampu melakukan **deteksi duplikasi data
menggunakan beberapa metode**, yaitu:

- Berdasarkan **content (isi data)**
- Berdasarkan **metadata (name + size)**
- Berdasarkan **kesamaan seluruh atribut data**

Sistem juga dilengkapi dengan fitur **pengukuran waktu eksekusi
(execution time)** untuk setiap operasi utama seperti insert, search,
delete, show, dan duplicate detection.

---

# Arsitektur Sistem

Sistem menggunakan pendekatan **in-memory data management** dengan
dataset awal yang dimuat dari file CSV.

Alur data sistem:

dataset.csv\
      ↓\
readCSV()\
      ↓\
Linked List (runtime storage)\
      ↓\
Operasi sistem\
(insert, search, delete, show, detect duplicate)\
      ↓\
Hasil duplicate disimpan ke\
output/result.txt

---

# Struktur Folder

duplicate-detection/

├── main.cpp --- program utama dan menu sistem\
├── data.h --- struktur data arsip\
├── linkedList.h --- deklarasi Linked List\
├── linkedList.cpp --- implementasi Linked List\
├── fileHandler.h --- deklarasi fungsi pembaca dataset\
├── fileHandler.cpp --- membaca dataset CSV
dataset/\
└── dataset.csv --- dataset arsip
output/\
└── result.txt --- hasil deteksi duplikasi

---

# Struktur Data

## Data Arsip

Field Deskripsi

---

id          -> ID unik file
name        -> nama file
size        -> ukuran file
upload_date -> tanggal upload
source      -> sumber dokumen
content     -> representasi isi file

---

# Dataset

Format CSV:

id,name,size,upload_date,source,content

Contoh:

004901,ClimateRepo.pdf,2048,2004-07-24,JohnSmith,a81f3c92d11a0e5b\
004912,ClimateRepo_copy.pdf,2048,2004-07-24,JohnSmith,a81f3c92d11a0e5b

---

# Mekanisme Deteksi Duplikasi

Sistem mendukung tiga metode deteksi duplikasi:

1.  **Content**\
2.  **Metadata (name + size)**\
3.  **Full data comparison**

---

# Algoritma Duplicate Detection

Pseudo code:

for each node A\
 for each node B setelah A\
  if data sama → tandai duplicate

Kompleksitas:

O(n²)

---

# Fitur Sistem

1.  Insert Data\
2.  Search Data\
3.  Detect Duplicate\
4.  Show Data\
5.  Delete Data\
6.  Statistics

---

# Pengukuran Execution Time

Program menggunakan library **chrono** dari C++ untuk mengukur waktu
eksekusi setiap operasi.

---

# Kompleksitas Operasi

Operasi Kompleksitas

---

Insert O(1)
Search O(n)
Delete O(n)
Show Data O(n)
Detect Duplicate O(n²)

---

# Cara Menjalankan Program

Compile:

g++ *.cpp -o program1

Run:

./program1

---

# Teknologi yang Digunakan

- C++17
- STL
- Linked List
- chrono library
- CSV file handling

---

# Pengembangan Selanjutnya

- Implementasi Hash Table
- Perbandingan performa Linked List vs Hash Table
- Grafik execution time
- Analisis performa struktur data
- Penambahan fitur Update dan Perbaikan Bug
