# Writing and Presentation Test 7-11 november 

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
### **Postman**

- **Postman** adalah sebuah aplikasi yang berfungsi sebagai REST CLIENT untuk uji coba REST API. Postman biasa digunakan oleh developer pembuat API sebagai tools untuk menguji API yang telah mereka buat.

- Test REST API

  - Create New Todo, Untuk create new todo, pada halaman request method menjadi POST. Kemudian isi request URL dengan url server, contoh http://localhost:5000/api/task . Pilih option raw kemudian ganti format text menjadi JSON, kemudian input data body JSON
  ![Teks alternatif](posttrue.png)
   klik send, dan kita akan menerima response dari server.
    ![Teks alternatif](postt.png)
  - Get All Todo, pilih method GET.  http://localhost:5000/api/task
  ![Teks alternatif](gett.png)
   klik send, dan kita akan menerima response dari server.
  - Get Todo By Id, pilih method GET.  
  ![Teks alternatif](get.png)
   klik send, dan kita akan menerima response dari server.
  - Update Todo By Id, pilih method PUT.
  ![Teks alternatif](update.png)
  - Delete Todo By Id, pilih method DELETE.
  ![Teks alternatif](delete.png)

- **Membuat API Documentation**
  - Buka Collection yang ingin di buat dokumentasinya, pilih View documentation, kemudian akan tampil halaman documentation
  - Pada halaman documentation tersebut, kita bisa menambahkan deskripsi documentation, deskripsi pada setiap request.
  - kita dapat melihat detail dari sebuah request, seperti HTTP Method, url, request body, request header, dll.


### **MongoDB**

- MongoDB adalah salah satu jenis database NoSQL yang cukup populer digunakan dalam pengembangan website. Berbeda dengan database jenis SQL yang menyimpan data menggunakan relasi tabel, MongoDB menggunakan dokumen dengan format JSON. 
- Sistem database ini menggunakan beberapa komponen penting, yaitu: 
  - Database – merupakan wadah dengan struktur penyimpanan yang disebut collection. 
  - Collection – merupakan tempat kumpulan informasi data yang berbentuk dokumen. Collection dipadankan seperti tabel-tabel yang berisi data pada database SQL.  
  - Document – merupakan satuan unit terkecil dalam MongoDB. 

- Sebagai satuan terkecil, dokumen akan berisi baris-baris data tanpa schema tertentu, tapi berupa struktur pasangan key-value. Key digunakan untuk melacak objek dengan (value) nilai yang bervariasi, seperti data angka, string, atau objek kompleks lainnya. 

- Create data
```
exports.createTask = asyncHandler(async (req, res) => {
    const {task, active} = req.body
    const todo = await Todo.create({task, active});
    res.status(201).json({
        success: true,
        data: todo,
        message: 'Task is created successfully'
    })
})
```

- Read data
```
 exports.getAllTasks = asyncHandler(async (req, res) => {
    const allTasks = await Todo.find({})
    if(allTasks){
        res.status(200).json({
            success: true,
            data:allTasks,
            message: 'All Tasks are fetched successfully'
        })
    }else{
        res.status(401).json({
            success: false,
            data: null,
            message: 'Tasks are Not Found'
        })
    }
   
})
```
- Update data
```
 exports.updateTask = asyncHandler(async (req, res) => {
    const {task, active} = req.body
    const existTask = await Todo.findOne({ _id : req.params.id})
    if(existTask){
        existTask.task = task;
        existTask.active = active
        const updatedTask = await existTask.save();
        res.status(200).json({
            success: true,
            data: updatedTask,
            message: 'Task is updated successfully'
        })
    }else{
        res.status(401).json({
            success: false,
            data: null,
            message: 'Task is Not Found'
        })
    }
   
})
```
- delete data
```
 exports.deleteTask = asyncHandler(async (req, res) => {
    const existTask = await Todo.findOne({ _id : req.params.id})
    if(existTask){
        await existTask.remove();
        res.status(200).json({
            success: true,
            message: 'Task is deleted successfully'
        })
    }else{
        res.status(401).json({
            success: false,
            data: null,
            message: 'Task is Not Found'
        })
    }
   
})
```
- membuat Schema MongoDB
```
const mongoose = require('mongoose');
const todoSchema = mongoose.Schema({
    task: {
        type: String,
        required: true
    },
    active: {
        type: Boolean,
        default: true
    }
})
const Todo = mongoose.model('Todo', todoSchema)
module.exports = Todo
```



### **mongoose**


- install npm package
```
$ mkdir learn-express
$ cd learn-express
$ npm init -y
```

```
$ npm install express mongoose
```
Di sini, kami menginstal Expressuntuk berinteraksi dengan database MongoDB


- membuat index.js dan membuat server Express sederhana. 
```
const express = require("express")

const app = express()

app.listen(5000, () => {
	console.log("Server has started!")
})
```
Kita bisa mulai menghubungkan server ke database MongoDB.


```
const express = require("express")
const mongoose = require("mongoose") // new

// Connect to MongoDB database
mongoose
	.connect("mongodb://localhost:27017/acmedb", { useNewUrlParser: true })
	.then(() => {
		const app = express()

		app.listen(5000, () => {
			console.log("Server has started!")
		})
	})
  ```

- Jalankan kembali server, dan pastikan tidak ada error.

```
$ npm start
Server has started!
```






### **Docker**

- Dalam penggunaan Docker, Container adalah sebuah lingkungan khusus yang dibuat untuk instance Docker image. Menjalankan sebuah Image akan menghasilkan satu Docker container.

- Image menyediakan template yang bisa digunakan dalam pembuatan container. Image mungkin berisi informasi yang dibutuhkan untuk membuat container, dan bisa disimpan di komputer atau secara remote.

![Teks alternatif](docker.png)

- Docker bekerja dengan arsitektur client-server. Client akan berinteraksi dengan Docker daemon yang bertugas untuk menjalankan, mendistribusi dan membuat kontainer. Docker client dan daemon dapat berjalan pada sistem operasi yang sama.

- Docker daemon dan client berinteraksi menggunakan Docker Engine RestAPI. Docker daemon akan menerima request client dari API yang diakses oleh client melalui HTTP.