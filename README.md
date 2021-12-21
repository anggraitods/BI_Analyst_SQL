# BI_Analyst_SQL
Studi kasus sederhana dari Query SQL

Link : https://www.testdome.com/files/resources/10/b9c0be7f-d981-428a-9f06-899ec15a5f5d.txt

-- Suggested testing environment:
-- http://sqlite.online/

-- Example case create statement:
CREATE TABLE employees (
  id INTEGER NOT NULL PRIMARY KEY,
  managerId INTEGER REFERENCES employees(id), 
  name VARCHAR(30) NOT NULL
);

INSERT INTO employees(id, managerId, name) VALUES(1, NULL, 'John');
INSERT INTO employees(id, managerId, name) VALUES(2, 1, 'Mike');

Expected output (in any order):
name
----
Mike

Explanation:
In this example.
John is Mike's manager. Mike does not manage anyone.
Mike is the only employee who does not manage anyone.

JAWABAN :

Langkah-langkah pengerjaan querynya :
1. Buat nama databasenya disini saya menggunakan nama database jabar_digital
Perintah : CREATE DATABASE jabar_digital;
2. Kemudian cek untuk databasenya
Perintah : SHOW Databases;
3. Buat tabel dalam database jabar_digital
pindah ke database jabar_digital 
perintah : use jabar_digital;
4. Setelah masuk ke database jabar_digital, buat tabel untuk employees
perintah : 
          CREATE TABLE employees (
            id INTEGER NOT NULL PRIMARY KEY,
            managerId INTEGER REFERENCES employees(id), 
            name VARCHAR(30) NOT NULL
          );
5. Kemudian cek tabel employees
perintah : SHOW tables;
6. setelah memastikan tabel employees dibuat, kemudian lakukan query insert data kedalam tabel employees
perintah : 
INSERT INTO employees(id, managerId, name) VALUES(1, NULL, 'John');
INSERT INTO employees(id, managerId, name) VALUES(2, 1, 'Mike');
7. Kemudian query untuk menjawab studi kasus diatas, dimana tampilkan dari kolom nama karyawan yang bukan merupakan manager, disini hanya ada 2 data karyawan yaitu 
John dan Mike. Disini John adalah seorang manager dari Mike, maka ouputnya nantinya menampilkan tabel employees dengan kolom name yaitu Mike.
perintah :
          Select name
          FROM employees
          WHERE managerId is NOT NULL;

Capture Query :

![cmd_VFn2RZmn1o](https://user-images.githubusercontent.com/30334980/146882659-f87f8fb5-9242-4180-aa13-2066b67fb4fc.png)

![chrome_XZ81732PzS](https://user-images.githubusercontent.com/30334980/146882687-d505af7d-c4f8-4e63-8dbe-6f6347f5fcb4.png)

![chrome_XpLZqXEOpV](https://user-images.githubusercontent.com/30334980/146882705-e1330fa7-d8c4-4502-93ea-f57d2d78c3fa.png)


