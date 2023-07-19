# DDL-DML-CONSTRAINT
<img src="https://avatars.githubusercontent.com/u/88238381?v=4" height=200 width=200>

:wave: Perkenalkan, nama saya **Randy Aulia Ananda Ruslani**. <br/>
:ledger: Dalam dokumen ini, saya akan menjelaskan tenang bahasa DDL, DML, dan *Constraint*

## DDL (Data Definition Language)

DDL adalah bahasa yang digunakan untuk mendefinisikan struktur dan skema basis data. Perintah-perintah DDL digunakan untuk membuat, mengubah, atau menghapus objek basis data seperti tabel, indeks, dan *constraint*.

### - CREATE DATABASE
 Digunakan untuk membuat basis data baru.

Sintaks:
> CREATE DATABASE nama_database;

&nbsp;
### CREATE TABLE
 Digunakan untuk membuat tabel baru dalam basis data.

**Sintaks**:
> CREATE TABLE nama_tabel (
    kolom1 tipe_data_kolom1,
    kolom2 tipe_data_kolom2,
    ...
    PRIMARY KEY (kolom1)
);

&nbsp;
### ALTER TABLE
Digunakan untuk mengubah struktur tabel, menambahkan kolom baru, atau menambahkan *constraint* setelah tabel dibuat.

**Sintaks**:
> ALTER TABLE nama_tabel
ADD COLUMN nama_kolom tipe_data,
ADD CONSTRAINT nama_constraint jenis_constraint (nama_kolom);

&nbsp;
**Contoh**:
> ALTER TABLE Employees
ADD COLUMN salary DECIMAL(10,2),
ADD CONSTRAINT ck_salary CHECK (salary > 0);

&nbsp;
### DROP TABLE
 Digunakan untuk menghapus tabel beserta seluruh data yang ada di dalamnya.
 
Sintaks:
>DROP TABLE nama_tabel;

&nbsp;
Contoh:
>DROP TABLE Employees;

&nbsp;
## DML (Data Manipulation Language)
DML adalah bahasa yang digunakan untuk memanipulasi data dalam tabel, seperti menyisipkan, memperbarui, menghapus, dan mengambil data.

### INSERT INTO
Digunakan untuk menyisipkan data baru ke dalam tabel.

**Sintaks**:

> INSERT INTO nama_tabel (kolom1, kolom2, ...)
VALUES (nilai_kolom1, nilai_kolom2, ...);

&nbsp;
**Contoh**:
>INSERT INTO Employees (employee_id, first_name, last_name, hire_date, department)
VALUES (1, 'John', 'Doe', '2023-07-19', 'HR');

&nbsp;
### UPDATE
Digunakan untuk memperbarui data yang sudah ada dalam tabel.

**Sintaks**:
> UPDATE nama_tabel
SET kolom1 = nilai_baru1, kolom2 = nilai_baru2, ...
WHERE kondisi;

&nbsp;
**Contoh**:
> UPDATE Employees
SET department = 'Finance'
WHERE employee_id = 1;

&nbsp;
### DELETE FROM
Digunakan untuk menghapus data dari tabel berdasarkan kondisi tertentu.

**Sintaks**:
> DELETE FROM nama_tabel
WHERE kondisi;

&nbsp;
**Contoh**:
> DELETE FROM Employees
WHERE hire_date < '2022-01-01';

&nbsp;
### SELECT
Digunakan untuk mengambil data dari tabel.

**Sintaks**:
> SELECT kolom1, kolom2, ...
FROM nama_tabel
WHERE kondisi;

&nbsp;
**Contoh**:
> SELECT employee_id, first_name, last_name, hire_date
FROM Employees
WHERE department = 'HR';

&nbsp;
## Constraint
Constraint digunakan untuk memberlakukan aturan tertentu pada data yang dimasukkan ke dalam tabel, sehingga memastikan integritas data dan konsistensi dalam basis data.

### PRIMARY KEY
Menandakan bahwa kolom tertentu adalah kunci utama (primary key) dan akan mengidentifikasi secara unik setiap baris dalam tabel.

**Contoh**:
> CREATE TABLE Employees (
    employee_id INT PRIMARY KEY,
    ...
);

&nbsp;
### FOREIGN KEY
Menandakan bahwa kolom tertentu adalah kunci asing (foreign key) yang merujuk ke kolom pada tabel lain, sehingga terjaga relasi antar tabel.

**Contoh**:
> CREATE TABLE Borrowers (
    borrower_id INT,
    book_id INT,
    FOREIGN KEY (book_id) REFERENCES Books (book_id)
);

&nbsp;
### UNIQUE
Menandakan bahwa nilai dalam kolom tertentu harus unik, tidak boleh ada duplikat.

**Contoh**:
> CREATE TABLE Employees (
    employee_id INT UNIQUE,
    ...
);

&nbsp;
### CHECK
 Menandakan bahwa nilai dalam kolom tertentu harus memenuhi kondisi tertentu.

**Contoh**:
> CREATE TABLE Employees (
    employee_id INT,
    salary DECIMAL(10,2),
    CONSTRAINT ck_salary CHECK (salary > 0)
);

&nbsp;
<br/>
:book: Terima kasih telah membaca dokumen ini sampai terakhir <br/>
:package: Pastikan untuk check [*reposity* saya yang lainnya](https://github.com/RandyAnanda11)