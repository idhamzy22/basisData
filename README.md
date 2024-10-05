# Hasil Eksekusi

Hasil eksekusi MariaDB yang menunjukkan langkah-langkah dari membuat database hingga melakukan manipulasi data:

```bash
C:\Users\HP>cd c:\xampp\mysql\bin

c:\xampp\mysql\bin>mysql -u root -p
Enter password:
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 10
Server version: 10.4.32-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| phpmyadmin         |
| test               |
+--------------------+
5 rows in set (0.001 sec)

MariaDB [(none)]> create database praktikum;
Query OK, 1 row affected (0.002 sec)

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| phpmyadmin         |
| praktikum          |
| test               |
+--------------------+
6 rows in set (0.001 sec)

MariaDB [(none)]> use praktikum;
Database changed

MariaDB [praktikum]> create table praktikum (
    -> ID INT AUTO_INCREMENT PRIMARY KEY,
    -> Nama VARCHAR(100),
    -> NIM VARCHAR(15),
    -> Jam TIME,
    -> Hari VARCHAR(10),
    -> Ruangan VARCHAR(50),
    -> Dosen VARCHAR(100)
    -> );
Query OK, 0 rows affected (0.022 sec)

MariaDB [praktikum]> insert into praktikum (Nama, NIM, Jam, Hari, Ruangan, Dosen)
    -> values ('Idham Kholid N.A', '20230801192', '16:20', 'Senin', 'CR 401', 'Ranny Meilisa S.Kom., M.Pd.T.');
Query OK, 1 row affected (0.007 sec)

MariaDB [praktikum]> select * from praktikum;
+----+------------------+-------------+----------+-------+---------+-------------------------------+
| ID | Nama             | NIM         | Jam      | Hari  | Ruangan | Dosen                         |
+----+------------------+-------------+----------+-------+---------+-------------------------------+
|  1 | Idham Kholid N.A | 20230801192 | 16:20:00 | Senin | CR 401  | Ranny Meilisa S.Kom., M.Pd.T. |
+----+------------------+-------------+----------+-------+---------+-------------------------------+
1 row in set (0.001 sec)

MariaDB [praktikum]> update praktikum
    -> set Hari = 'Minggu';
Query OK, 1 row affected (0.007 sec)
Rows matched: 1  Changed: 1  Warnings: 0

MariaDB [praktikum]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| phpmyadmin         |
| praktikum          |
| test               |
+--------------------+
6 rows in set (0.001 sec)

MariaDB [praktikum]> select * from praktikum;
+----+------------------+-------------+----------+--------+---------+-------------------------------+
| ID | Nama             | NIM         | Jam      | Hari   | Ruangan | Dosen                         |
+----+------------------+-------------+----------+--------+---------+-------------------------------+
|  1 | Idham Kholid N.A | 20230801192 | 16:20:00 | Minggu | CR 401  | Ranny Meilisa S.Kom., M.Pd.T. |
+----+------------------+-------------+----------+--------+---------+-------------------------------+
1 row in set (0.001 sec)

MariaDB [praktikum]>
```


# Panduan Penggunaan MariaDB Beserta Hasil Eksekusi

## 1. Koneksi ke MariaDB
Untuk memulai, gunakan perintah berikut untuk masuk ke MariaDB menggunakan user `root`:

```bash
c:\xampp\mysql\bin>mysql -u root -p
```

Setelah memasukkan kata sandi, Anda akan melihat tampilan berikut:

```
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 10
Server version: 10.4.32-MariaDB mariadb.org binary distribution
```

## 2. Menampilkan Daftar Database
Untuk menampilkan semua database yang ada dalam server, gunakan perintah:

```sql
show databases;
```

### Hasil
```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| phpmyadmin         |
| test               |
+--------------------+
5 rows in set (0.001 sec)
```

## 3. Membuat Database Baru
Buat database baru bernama `praktikum` menggunakan perintah:

```sql
create database praktikum;
```

### Hasil
```
Query OK, 1 row affected (0.002 sec)
```

## 4. Menampilkan Daftar Database Setelah Pembuatan
Gunakan perintah berikut untuk menampilkan daftar database yang telah ada:

```sql
show databases;
```

### Hasil
```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| phpmyadmin         |
| praktikum          |
| test               |
+--------------------+
6 rows in set (0.001 sec)
```

## 5. Menggunakan Database Praktikum
Berpindah ke database `praktikum` menggunakan perintah:

```sql
use praktikum;
```

### Hasil
```
Database changed
```

## 6. Membuat Tabel
Buat tabel `praktikum` dengan struktur berikut:

```sql
create table praktikum (
    ID INT AUTO_INCREMENT PRIMARY KEY,
    Nama VARCHAR(100),
    NIM VARCHAR(15),
    Jam TIME,
    Hari VARCHAR(10),
    Ruangan VARCHAR(50),
    Dosen VARCHAR(100)
);
```

### Hasil
```
Query OK, 0 rows affected (0.022 sec)
```

## 7. Menyisipkan Data ke Tabel
Untuk menyisipkan data ke dalam tabel, gunakan perintah berikut:

```sql
insert into praktikum (Nama, NIM, Jam, Hari, Ruangan, Dosen)
values ('Idham Kholid N.A', '20230801192', '16:20', 'Senin', 'CR 401', 'Ranny Meilisa S.Kom., M.Pd.T.');
```

### Hasil
```
Query OK, 1 row affected (0.007 sec)
```

## 8. Menampilkan Data dari Tabel
Gunakan perintah berikut untuk melihat semua data yang ada di tabel:

```sql
select * from praktikum;
```

### Hasil
```
+----+------------------+-------------+----------+-------+---------+-------------------------------+
| ID | Nama             | NIM         | Jam      | Hari  | Ruangan | Dosen                         |
+----+------------------+-------------+----------+-------+---------+-------------------------------+
|  1 | Idham Kholid N.A | 20230801192 | 16:20:00 | Senin | CR 401  | Ranny Meilisa S.Kom., M.Pd.T. |
+----+------------------+-------------+----------+-------+---------+-------------------------------+
1 row in set (0.001 sec)
```

## 9. Mengupdate Data
Jika ingin memperbarui data, misalnya mengubah kolom `Hari`, gunakan perintah berikut:

```sql
update praktikum
set Hari = 'Minggu';
```

### Hasil
```
Query OK, 1 row affected (0.007 sec)
Rows matched: 1  Changed: 1  Warnings: 0
```

## 10. Menampilkan Data Setelah Update
Tampilkan kembali data untuk memastikan perubahan berhasil:

```sql
select * from praktikum;
```

### Hasil
```
+----+------------------+-------------+----------+--------+---------+-------------------------------+
| ID | Nama             | NIM         | Jam      | Hari   | Ruangan | Dosen                         |
+----+------------------+-------------+----------+--------+---------+-------------------------------+
|  1 | Idham Kholid N.A | 20230801192 | 16:20:00 | Minggu | CR 401  | Ranny Meilisa S.Kom., M.Pd.T. |
+----+------------------+-------------+----------+--------+---------+-------------------------------+
1 row in set (0.001 sec)
```

## Penutup
Dengan langkah-langkah di atas, Anda telah berhasil membuat database `praktikum`, tabel dengan data mahasiswa, serta melakukan update dan menampilkan hasil dari setiap perubahan.