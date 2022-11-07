# Writing and Presentation Test 31okt-4nov 

### **Design Database With MySQL**

- **Entitas** merupakan sekumpulan objek yang dapat diidentifikasi secara unik dan berbeda satu dengan yang lainnya.
- pada dasarnya entitas dapat sebuah tabel, apabila ada daatabase bernama toko maka databse yag ada didalamnya adalah entitas kasir, transaksi, barang
- **Atribut** merupakan properti atau karakteristik yang mendeskripsikan sebuah entitas. contohnya, apabila terdapat entitas kasir maka atributnya kasir_id, kasir_nama
- **ERD** (Entity Relationship Diagram) atau diagram hubungan entitas adalah sebuah diagram yang digunakan untuk perancangan suatu database dan menunjukan relasi atau hubungan antar objek atau entitas beserta atribut-atributnya secara detail. 

![Teks alternatif](erd.drawio.png)

dalam erd diatas terdapat entitas kasir dan transaksi, tabel kasir memiliki primary key kasir_id, dan berelasi dengan tabel transaksi, kasir_id pada tabel trannsaksi menjadi foreign key. artinya setiap kasir memiliki banyak transaksi

### **MySQL Basic**

- **Database** atau basis data adalah kumpulan data yang dikelola sedemikian rupa berdasarkan ketentuan tertentu yang saling berhubungan sehingga mudah dalam pengelolaannya. Melalui pengelolaan tersebut pengguna dapat memperoleh kemudahan dalam mencari informasi, menyimpan informasi dan membuang informasi.

- **DBMS** adalah singkatan dari “Database Management System” yaitu sistem penorganisasian dan sistem pengolahan Database pada komputer. DBMS atau database management system ini merupakan perangkat lunak (software) yang dipakai untuk membangun basis data yang berbasis komputerisasi.

- **MySQL** merupakan salah satu aplikasi relational database open source terbaik yang ada saat ini. Selain itu aplikasi ini juga beberapa lisensi tambahan yang bisa diambil sesuai dengan kebutuhan. MySQL memberikan kemudahan saat input data dan memiliki performa tinggi.

- Tipe data numeric
<table>
 <tr>

 <th>
  Tipe data
 </th>
 <th>
  Keterangan
 </th>
 <th>
  Ukuran
 </th>
  </tr>
 <tr>
    <td>
Integer atau Int</td>	
<td>Bilangan bulat  ( Positif / Negatif )

Signed value : -2147683648 to 2147683647	
Unsigned value : 0 to 4294967295	</td>
<td>
4 byte
</td>
 </tr>

  <tr>
    <td>
Decimal </td>	
<td>Bilangan pecahan ( Positif / Negatif )
Bilangan desimal 
</td>
<td>M byte</td>

</tr>
<tr>
<td>
Float (m,d)
</td>	
<td>Bilangan pecahan presisi tunggal</td>
<td>4 byte</td>
</tr>
<tr>
<td>
Double
</td>	
<td>Bilangan pecahan presisi ganda</td>
<td>8 byte</td>
</tr>
<tr>
<td>
Tinyint 
</td>	
<td>Bilangan bulat  ( Positif / Negatif )
Signed value : -128 to 127	

Unsigned value : 0 to 255</td>
<td>1 byte</td>
</tr>
</table>

- Tipe Data String
<table>
 <tr>

 <th>
  Tipe data
 </th>
 <th>
  Keterangan
 </th>

  </tr>
 <tr>
    <td>
Char </td>	
<td>menyatakan deretan karakter (string) yang lebarnya tetap yaitu maksimum adalah 255 karakter	</td>

 </tr>

  <tr>
    <td>
Varchar</td>	
<td>Data string dengan lebar data yang bervariasi (M), Maksimum lebar adalah 255 karakter	
</td>
</tr>

</table>

- Tipe Data tanggal

<table>
 <tr>

 <th>
  Tipe data
 </th>
 <th>
  Keterangan
 </th>
 <th>
  Ukuran
 </th>
  </tr>
 <tr>
    <td>
Date </td>	
<td>	Digunakan untuk tanggal dengan format "YYYY-MM-DD" Range nilai : "1000-01-01" s.d "9999-12-31"	</td>
<td>
	3 byte
</td>
 </tr>

  <tr>
    <td>
Time</td>	
<td>Digunakan untuk waktu dengan format "hh:mm:ss" Range nilai : -838:59:59" s.d "838:59:59"	
</td>
<td>3 byte</td>

</tr>
<tr>
<td>
Datetime
</td>	
<td>Digunakan untuk tanggal dan waktu dengan format "YYYY-MM-DD hh:mm:ss" Range nilai :"1000-01-01 00:00:00" s.d "9999-12-31 23:59:59"</td>
<td>8 byte</td>
</tr>
<tr>
<td>
Time stamp
</td>	
<td>Digunakan untuk penulisan tanggal dan waktu dengan format "YYYYMMDDhhmmss"</td>
<td>4 byte</td>
</tr>
</table>

- **memilih** semua data column dari tabel pegawai dengan ```SELECT```
```
SELECT * FROM pegawai;
```
- **mengubah** data dari tabel pegawai menjadi  "lisa" dengan ```UPDTAE```
```
UPDATE pegawai
SET nama='lisa'
WHERE kota='solo';
```
- **menambahkan** data di tabel pegawai dengan ```INSERT```
```
INSERT INTO pegawai
VALUES (1,adi,malang, ...);
```
- **menghapus** data di tabel pegawai dengan ```DELETE```
```
DELETE FROM pegawai WHERE nama='lisa';
```

- memilih data di tabel pegawai dengan nama='lisa' **dan** kota='solo' menggunakan ```AND```
```
SELECT * FROM pegawai
WHERE nama='lisa' AND kota='solo';
```
- memilih data di tabel pegawai dengan nama='lisa' **atau** kota='malang' menggunakan ```OR```
```
SELECT * FROM pegawai
WHERE nama='lisa' OR kota='malang';
```
- memilih data di tabel pegawai dengan kota **selain** 'malang' menggunakan ```NOT```
```
SELECT * FROM pegawai
WHERE NOT kota='solo';
```
### **authentication dan authorization**

- **Authentication** adalah proses dimana seorang user (melalui berbagai macam akses fisik berupa komputer , melalui jaringan , atau melalui remote access ) mendapatkan hak akses kepada suatu entity (dalam hal ini jaringan suatu corporate). Seorang user melakukan login kedalam suatu infrastruktur jaringan dan sistem mengenali user ID ini dan menerimanya untuk kemudian diberikan akses terhadap resources jaringan sesuai dengan authorisasi yang dia terima.
metode authentication seperti password/PIN, digital certificate

- **Authorization** adalah proses penentuan apakah user tersebut diijinkan / ditolak untuk melakukan satu atau beberapa action atau akses terhadap resources tertentu dalam system. User login terhadap system dengan menggunakan user-ID dan password, kemudian system mengenalinya dan user mendapatkan akses atau ditolak terhadap suatu resource system tertentu.

- **enkripsi** adalah cara mengacak data sehingga informasi tersebut hanya bisa dibaca oleh orang-orang yang memiliki aksesnya saja.encryption merupakan proses konversi teks biasa yang terbaca manusia (human-readable plaintext) menjadi teks yang tidak bisa dibaca dan dimengerti (incomprehensible text). Data atau teks yang terenkripsi disebut ciphertext.
- inisialisasi proyek Node.js

- user authentication menggunakan JWT with Express

```
npm init -y
```
- install the Express framework
```
npm install --save express
```
-  membuat file auth.js, yang menjadi layanan autentikasi
```
const express = require('express');
const app = express();

app.listen(3000, () => {
    console.log('Authentication service started on port 3000');
});
```
- membuat role admin, member
```
const users = [
    {
        username: 'lisa',
        password: 'admin123',
        role: 'admin'
    }, {
        username: 'adi',
        password: 'member123',
        role: 'member'
    }
];
```
- instal ```body-parser``` middleware
```
$ npm i --save body-parser jsonwebtoken
```
- modules dan konfigurasi di Express app
```
const jwt = require('jsonwebtoken');
const bodyParser = require('body-parser');

app.use(bodyParser.json());
```
- menangani user login request
```
const accessTokenSecret = 'accesstoken';
```
- mencari pengguna yang cocok dengan username dan password di request body. kemudian kita generated access token dengan JSON object dengan username dan role user.
```
app.post('/login', (req, res) => {
    // Read username and password from request body
    const { username, password } = req.body;

    // Filter user from the users array by username and password
    const user = users.find(u => { return u.username === username && u.password === password });

    if (user) {
        // Generate an access token
        const accessToken = jwt.sign({ username: user.username,  role: user.role }, accessTokenSecret);

        res.json({
            accessToken
        });
    } else {
        res.send('Username or password incorrect');
    }
});
```
- Layanan otentikasi, jalankan
```
$ node auth.js
```
- mengirim post request ke http://localhost:3000/login endpoint dengan JSON
```
{
    "username": "lisa",
    "password": "admin123"
}
```
- mendapatkan token akses
```
{
  "accessToken": "..."
}
```
### **Sequelize**

- **Sequelize** adalah Node.js promise-based ORM untuk MySQL, PostgreSQL, SQLite, MSSQL dan database SQL lainnya. Sequelize berfungsi untuk bekerja dengan database dan relasi-relasi di dalamnya.

- **Menginstal Sequelize**

- membuat direktori untuk proyek kita, masukkan, dan buat proyek
```
$ mkdir catatan-app
$ cd catatan-app
$ npm init -y
```
- Selanjutnya, untuk membuat server web dengan mudah, kita akan menginstal Express:
```
$ npm install --save express
```
- siapkan server
```
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => res.send('catatan App'));

app.listen(port, () => console.log(`catatan-app listening on port ${port}!`));
```
- menginstal Sequelize dan database melalui npm:
```
$ npm install --save sequelize
$ npm install --save sqlite3
```
- menambahkan beberapa kode ke index.js file untuk mengatur database dan check connection menggunakan Sequelize
```
const Sequelize = require('sequelize');
const sequelize = new Sequelize({
  // The `host` parameter is required for other databases
  // host: 'localhost'
  dialect: 'sqlite',
  storage: './database.sqlite'
});
```
- URI connection
```
const sequelize = new Sequelize('postgres://user:pass@example.com:5432/dbname');
```
- test connection dengan menjalankan .authenticate() method. Di bawah tenda, menjalankan SELECT query dan memeriksa apakah database merespons dengan benar:
```
sequelize
  .authenticate()
  .then(() => {
    console.log('Connection has been established successfully.');
  })
  .catch(err => {
    console.error('Unable to connect to the database:', err);
  });
```
jalankan app
```
$ node index.js
catatan-app listening on port 3000!
Executing (default): SELECT 1+1 AS result
Connection has been established successfully.
```
- **CRUD**
- read
```
app.get('/catatan', function(req, res) {
  catatan.findAll().then(catatan => res.json(catatan));
});
```
- update
```
app.put('/catatan/:id', function(req, res) {
  catatan.findByPk(req.params.id).then(function(catatan) {
    catatan.update({
      catatan: req.body.catatan,
      tag: req.body.tag
    }).then((catatan) => {
      res.json(catatan);
    });
  });
});
```
- delete
```
app.delete('/catatan/:id', function(req, res) {
  catatan.findByPk(req.params.id).then(function(catatan) {
    catatan.destroy();
  }).then((catatan) => {
    res.sendStatus(200);
  });
});
```
- insert
```
const bodyParser = require('body-parser');
app.use(bodyParser.json());

app.post('/catatan', function(req, res) {
  catatan.create({ catatan: req.body.catatan, tag: req.body.tag }).then(function(catatan) {
    res.json(catatan);
  });
});
```