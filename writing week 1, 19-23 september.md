# Writing and Presentation Test 19-23 september

### **Unix Command Line**

- **Shell** adalah user interface yang bertugas untuk memproses semua perintah yang diketik di CLI. 
- Shell membaca dan mengartikan perintah, lalu menginstruksikan sistem operasi untuk menjalankan task sesuai permintaan. 

- **CLI** adalah singkatan dari Command Line Interface. user bisa mengetikkan perintah dalam bentuk teks dan memberikan instruksi pada komputer untuk mengerjakan tugas tertentu.
- contoh CLI : sh,bash,cmd.exe

- Untuk mengakses CLI dapat menggunakan Terminal Emulator

- Filesystem berguna untuk mengatur bagaimana data disimpan di dalam sebuah system
- Sistem operasi Windows & Unix-like menyusun file dan direktori menggunakan struktur yang bentuknya mirip tree
- Sistem operasi Windows menggunakan banyak tree
- Unix-like menggunakan satu tree

- Perintah pada CLI
  - perintah **pwd** menampilkan pada direktori mana anda berada.
  - perintah **ls** melihat isi pada suatu direktori.
  - perintah **cd** berpindah dari satu direktori ke direktori lainnya.
  - perintah **cat** melihat isi sebuah file
  - perintah **tail** melihat beberapa line akhir dari sebuah file text
  - perintah **head** melihat beberapa line awal dari sebuah file text
  - perintah **touch** membuat file baru
  - perintah **cp** menyalin file, cp -R menyalin direktori
  - perintah **mv** memindahkan dan merename file, mv -R memindahkan dan merename direktori
  - perintah **rm** menghapus file, rm -R menghapus direktori

### **Git dan GitHub dasar**
- Git adalah salah satu sistem pengontrol versi (Version Control System) pada proyek perangkat lunak yang diciptakan oleh Linus Torvalds.

- VCS atau pengontrol versi bertugas mencatat setiap perubahan pada file proyek yang dikerjakan oleh banyak orang maupun sendiri.

- Git dapat menggunakan command-line tool, yaitu pengubah kode dan dapat digabungkan menuju perangkat lokal. Sedangkan, GitHub menyediakan interface grafis berbasis cloud sebagai tempat untuk melakukan seluruh tugas.

- Git dapat membantu programmer untuk berkolaborasi dalam proyek dan melacak perubahan dan pembaruan proyek

- cara kerja git
	1. git init, perintah ini digunakan untuk membuat repositori di file lokal.
		```
		git init
		```
	2. git add, menambahkan semua file di dalam folder proyek ke dalam Staging Area
		```
		git add .
		```
	3. git commit, digunakan untuk melakukan commit pada perubahan ke head.
		```
		git commit –m “keterangan”
		```
	4. git remote, Git remote adalah petunjuk ke versi repositori yang biasanya disimpan di server lain.
		```
		git remote add origin https://github.com/lisa0104/tes.git
		```
	5. git push, akan mengirimkan perubahan ke main branch dari remote repository
		```
		git push origin main
		```
	6. git clone, merupakan sebuah perintah yang digunakan untuk membuat salinan repository lokal.
		```
		git clone url
		```
- git init hanya dilakukan sekali
- apabila terdapat perubahan pada file di dalam folder proyek maka dapat mengirimkan perubahan dengan melakukan git add, git commit dan git push 
### **HTML**

- **HTML** adalah singkatan dari Hypertext Markup Language, yaitu bahasa markup standar untuk membuat dan menyusun halaman dan aplikasi web.
- HTML digunakan untuk menampilkan konten dalam web contohnya audio, text, video, image dll
- HTML bukan bahasa pemrograman karena tidak bisa mengolah data

- Tools HTML
  - Code Editor digunakan untuk membuat code contohnya, sublime text, VScode dll
  - Browser digunakan untuk menjalankan code contohnya, chrome, mozilla

- Setiap halaman HTML sudah pasti mempunyai struktur dasar yang terdiri dari : tag Doctype, tag html, tag head, dan tag body.
    ``` 
	<!DOCTYPE html>
	<html>
	<head>
	    <title>judul website</title>
	</head>
	<body>
	    <p>konten website</p>
	</body>
	</html>	
    ```
- Element yang berapa didalam element lain diasebut child element, element yang diatasnya disebut parent element
    ``` 
	<body>
	    <p>konten website</p>
	</body>
    ```
- Element pada HTML terdapat content yang ditutup dengan opening tag dan closing tag
    ``` 
	<p>konten website</p>
    ```
- Comment digunkan untuk memberikan penjelasan maksud dari line code yang kita kerjakan.
    ``` 
	<!--comment html-->
    ```

- Menjalankan HTML dengan mencari lokasi file HTML kita lalu membukanya via browser
- Kita bisa menggunakan live server di VScode untuk membuat HTML auto reload 
  - install extension Live Server pada VScode
  - kemudian setelah diinstall klik kanan file HTML, klik open with Live Server
  - selesai, HTML sudah auto reload

- Perintah HTML populer
  - img adalah tag untuk membuat gambar
 	 ``` 
     <img src="/images/Love.jpg" alt="Love" width="24" height="39">
 	 ``` 
  - table	adalah tag untuk membuat tabel
  - th adalah tag untuk membuat sebuah sel header tabel
  - tr adalah tag untuk membuat baris dalam sebuah tabel
  - td adalah tag untuk membuat sel dalam sebuah tabel
 	 ``` 
	 <table>
	  <tr>
	    <th>no</th>
	    <th>nama</th>
	    <th>alamat</th>
	  </tr>
	  <tr>
	    <td>1</td>
	    <td>Eka</td>
	    <td>malang</td>
	  </tr>
	  <tr>
	    <td>2</td>
	    <td>Eki</td>
	    <td>solo</td>
	  </tr>
	 </table>
 	 ``` 
  - form adalah tag untuk membuat sebuah form HTML untuk input pengguna
  - input	adalah tag untuk membuat sebuah kontrol input
  - textarea adalah tag untuk membuat sebuah kontrol input multibaris (text area)
 	 ``` 
	 <form>
	  <label for="nama">Nama Lengkap:</label><br>
	  <input type="text" id="nama" name="nama"><br>
	  <textarea name="alamat" rows="10" cols="30">
	  </textarea>
	 </form>
 	 ``` 
  - ul adalah tag untuk membuat daftar dengan selain nomor
  - ol adalah tag untuk membuat daftar dengan nomor
  - li adalah tag untuk membuat sebuah item daftar
  	 ``` 
	 <ul>
	  <li>Coffee</li>
	  <li>Tea</li>
	  <li>Milk</li>
	</ul>
	<ol>
	  <li>Coffee</li>
	  <li>Tea</li>
	  <li>Milk</li>
	</ol>
	``` 	
- Elemen semantik adalah elemen-elemen yang menyatakan makna atau tujuan dari elemen itu sendiri
- Contohnya tag footer, tag ini digunakan untuk membuat elemen footer atau bagian kaki dari web.

- Deployment adalah kegiatan yang bertujuan untuk menyebarkan aplikasi yang telah dikerjakan oleh para programmer
- Cara deploy
  - masuk dalam netlify.com
  - register menggunakan email
  - masuk ke tab Sites
  - drag dan drop folder HTML

### **CSS**

- **CSS** atau Cascading Style Sheet merupakan aturan untuk mengatur beberapa komponen dalam sebuah web sehingga akan lebih terstruktur dan seragam.
- dengan CSS, kita bisa mengubah warna, menggunakan font custom, editing text format, mengatur tata letak, dan lainnya.

- menambahkan CSS ke dalam dokumen HTML
  - Inline – menggunakan atribut style dalam elemen HTML
    ```
	<h1 style="background-color:red; color:white" >
         Text
    </h1>
	```
  - Internal – menggunakan elemen ```<style>``` di dalam elemen ```<head>```
	```
	<style type="text/css">
        h1 {
        background-color:red;
        color:white;
        }
    </style>
	```
  - Eksternal – menggunakan elemen ```<link>``` di dalam elemen ```<head>```
	```
	<link rel="stylesheet" type="text/css" href="css.css">
	```
	```
	.h1 {
	background-color:red;
	color:white;
	}
	```
- Struktur CSS, Sintaks CSS terdiri dari tiga bagian: 
  - pemilih atau selektor (selector) adalah elemen atau tag HTML yang akan didefinisikan
  - sifat atau properti (property) adalah atribut yang akan diganti dengan nilai/value tertentu.
  - nilai (value)
  ```
  .elementHTML{
	property : value;
  }
  ```
- Kita bisa menggunakan lebih dari 1 class yang berbeda untuk 1 element HTML
	```
	<h3 class="judul kecil">
         Text
    </h3>
	```
	```
	.kecil {
	text-transform:lowercase;
	}
	.judul {
	color:black;
	}
	```
- HTML yang memiliki class yang sama, akan mempunyai styling yang sama saat digunakan pada CSS.
	```
	<h6>
         Text
    </h6>
	<h6>
         Text2
    </h6>
	```
	```
	.h6 {
	background-color:red;
	color:white;
	}
	```
	style Text dan Text akan sama
- ID Name bersifat unik artinya hanya ada 1 nama ID pada 1 element HTML.
   ```
	<div id="top">
		<h1>Judul</h1>
	</div>   
	```
	```
	#top {
    background-color: #ccc;
    padding: 20px
	}
	```
- Responsive web design atau desain web responsif adalah sebuah teknik atau metode bagi web designer untuk membuat suatu layout website yang dapat menyesuaikan diri sesuai dengan ukuran layar pengguna.

- Flexbox atau Flexible Box  merupakan sebuah mode pengaturan atau konsep layout pada CSS yang digunakan untuk mengatur elemen atau container beserta item didalamnya pada halaman web.
	- display, menambahkan “flex” pada property “display”
	  ```
		.container {
		display: flex;
		}
	  ```
	- flex-direction, menentukan arahnya item-item yang ada didalam container
	  ```
		.container {
		flex-direction: row | row-reverse | column | column-reverse;
		}
	  ```
	- flex wrap
		- Nowrap (default): semua item akan berada di satu baris
		- Wrap: item flex akan pindah ke baris selanjutnya apabila tidak muat, dari atas ke bawah
		- Wrap-reverse: sama seperti wrap, tetapi arah nya dari bawah ke atas
			```
			.container {
			flex-wrap: nowrap | wrap | wrap-reverse;
			}
			```
	- justify-content, mengkontrol atas penyelarasan (alignment) item flex yang berada di dalam container.
		```
		.container{
			justify-content: flex-start | flex-end | center | space-between | space-around;
		}
		```
### **Algoritma**

- Struktur data adalah cara penyimpanan , pengorganisasian , dan pengaturan data di dalam media penyimpanan komputer sehingga data tersebut dapat digunakan secara efisien. 

- Algoritma adalah sederetan langkah-langkah logis yang disusun secara sistematis untuk memecahkan suatu masalah.

- Struktur data bisa digunakan untuk membuat perintah dalam bahasa pemrograman dengan mudah

- Algoritma membuat kita menjadi lebih berpikir panjang untuk menyelesaikan suatu masalah dengan cara seefektif mungkin.

- contoh algoritma program sederhana mencari luas persegi 
	```
	start
	deklarasi variabel sisi, luas=0
	luas= sisi * sisi
	print luas
	stop
	```
- Pseudocode dapat diartikan sebagai deskripsi dari algoritma pemrograman yang dituliskan secara sederhana dibandingkan dengan sintaksis bahasa pemrograman.

- Procedural adalah bagaimana serangkaian perintah yang beruntun
- Conditional dibutuhkan dalam percabangan kasus, apabila memenuhi syarat tertentu maka tindakan akan dilakukan
- Looping adalah proses yang dilakukan berulang kali
- Recursive, memanggil method/function didalam sebuah function.

- contoh program dan algoritma conditional dalam javascript menentukan nilai lolos atau tidak
	```
	 start
	 deklarasi variabel nilai
	 if nilai>=90
		print lolos
	  else
	    print tidak lolos
	 stop
	```
	```
	const nilai = 90;

	if (nilai >= 80) {
	console.log("Lolos");
	} else {
	console.log("Tidak Lolos");
	}
	```	
### **JavaScript**
- JavaScript adalah bahasa pemrograman tingkat tinggi dan dinamis. digunakan untuk logic pada sebuah website. Kode JavaScript dapat disisipkan dalam halaman web menggunakan tag script.

- JavaScript dapat dijalankan pada browser seperti Google Chrome, Internet Explorer, Mozilla Firefox, Netscape dan Opera.

- tipe data dalam pemrograman Javascript:
	- String (teks)
		```
		let string= 'teks';
		```
	- Integer atau Number (bilangan bulat)
		```
		let number= 9;
		```
	- null
		```
		let data= null;
		```
	- Boolean
		```
		let benar= true;
		let salah= false;
		```
	- Object, sekumpulan list dari tipe data primitif (terkadang juga tipe data reference)
	- Undefined
- Operator
	- Assignment Operator (=)
	- Arithmetic Operator 
		- Tambah (+)
		- Kuramg (-)
		- Perkalian (*)
		- Pembagian (/)
		- Modulus (%)
	- Increment (++) dan Decrement (--)
	- comparison operator
		- Lebih kecil dari : <
		- Lebih besar dari: >
		- Lebih kecil atau sama dengan: <=
		- Lebih besar atau sama dengan: >=
		- Sama dengan: ===
		- Tidak sama dengan: !==
	- Logical Operator
		- AND operator : &&
		- OR operator: ||
		- NOT operator: !
- Conditional adalah statement percabangan yang menggambarkan suatu kondisi, contoh conditional 
	- if else
	```
	const nilai = 90;
	if (nilai >= 80) {
	console.log("lulus");
	} else {
	console.log("tidak lulus");
	}
	```	
	- if else if
	```
	let x = '';
	if (nilai >= 80) {
	console.log("A");
	} else if (nilai >= 60){
	console.log("B");
	}else {
	console.log("C");
	}
	```	
	- switch case
	```	
	switch (new Date().getDay()) {
	case 0:
		day = "Sunday";
		break;
	case 1:
		day = "Saturday";
		break;
	case 2:
		day = "Friday";
		break;
	case 3:
		day = "Thursday";
	}
	```	
- Looping adalah proses yang dilakukan berulang kali
	- do while
	```
		let i = 0;
		do {
		i += 1;
		console.log(i);
		} while (i < 7);
	```
	- while
	```
		let n = 0;
		let x = 0;
		while (n < 5) {
		n++;
		x += n;
		}
	```
	- for
	```
		for (var i = 0; i < 3; i++) {
		let kota = "surabaya";
		console.log(kota);
		}
	```