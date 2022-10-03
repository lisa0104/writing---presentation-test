# Writing and Presentation Test 26-30 september

### **Scope**

- **Scope** adalah bagaimana cakupan variable atau data dan function dapat diakses. terdapat dua scode local dan global
- **Local Scope** adalah variable atau function yang terdapat dalam scope tersebut hanya dapat diakses oleh kode dalam function tersebut, contohnya
	```
	var buah = 'apel';

	function makanBuah() {
		var buah = 'pisang';
		console.log(buah); // 'pisang'
	}
	makanBuah();
	console.log(buah); // 'apel'
	```
	function makanBuah() adalah local scope, kita mendeklarasikan variable buah secara local dalam function tersebut.

- **Global Scope**, kebalikan dari local scope, function atau variable yang dibuat pada global scope dapat diakses pada semua kode walaupun kode tersebut didalam/diluar function. contohnya
	```
	var buah = 'pisang';
	```
	contoh global scope secara default

- **Block** adalah area yang dicakup oleh scope yang ada di dalam statement if-else atau looping, atau bisa disebut dengan block statement. singkatnya block adalah kode didalam curly braces {} Perlu diperhatikan, block di JavaScript tidak menciptakan local scope baru di dalam scope yang ditempati sekarang. 
	```
	function makanBuah() {
	var buah = 'pisang';
	console.log(buah); // 'pisang'
	
	if(true) {
		let buah = 'mangga';
		console.log(buah); // 'mangga'
	}
	console.log(buah); // 'pisang'
	}
	```
	buah di dalam block statement if merupakan variable di dalam block scope yang berbeda dengan variable buah di function makanBuah()

### **Function**

- **Function** adalah blok kode yang dirancang untuk melakukan menyelesaikan 1 task tertentu. 
	```
	function berkata(){
		console.log("Selamat datang!!!");
	}
	//memanggil function
	berkata();
	```

- **Parameter** merupakan variable yang menyimpan nilai untuk diproses di dalam function. 
	```
	function luasPersegi(a){
		//mengembalikan nilai
		return a*a;
	}
	```
	a adalah parameter

- **Argumen** merupakan nilai yang digunakan untuk memanggil function 
	```
	function luasPersegi(a){
		return a*a;
	}
	console.log(luasPersegi(3));
	```
	3 adalah argumen

- **Default Parameters** adalah memberikan value default pada function
	```
	function luasPersegi(a=3){
		return a*a;
	}
	console.log(luasPersegi(5)); //25
	console.log(luasPersegi()); //9
	```
- **Function Helper**, kita dapat menggunakan function yang telah kita buat sebelumnya dalam function lain

### **Error messages & debugging**
- Reference errors disebabkan oleh variabel yang belum dideklarasikan atau karena var , let atau const belum diberikan, contohnya
	```
	mobil="merah";//Uncaught ReferenceError: mobil is not defined
	console.log(mobil);
	```
	penyelesaian
	```
	let mobil="merah";
	console.log(mobil);
	```
- Syntax errors disebabkan oleh kode memiliki sesuatu yang tidak dapat diuraikan dalam hal sintaksis, seperti ketika Anda mencoba mengurai objek yang tidak valid menggunakan JSON.parse.
	```
	JSON.parse( {'foo': 'bar'} ) // Uncaught SyntaxError: Unexpected token o in JSON at position 1
	```
	penyelesaian
	```
	JSON.parse('{"foo":"bar"}')
	```
- Range errors disebabkan oleh panjang yang tidak valid coba mengganti objek dengan panjang tertentu
	```
	let mobil= []
	mobil.length = mobil.length -1 // Uncaught RangeError: Invalid array length
	```
	penyelesaian
	```
	let mobil = [0, 0]
	mobil.length = mobil.length - 2 // (atau mobil.length - mobil.length)
	mobil //akan menjadi []
	```
- Type errors, kesalahan ketik contohnya mengakses properti dalam jenis variabel yang tidak ditentukan

- **Debugging** dapat menggunakan console.log() pada chrome, buka halaman dengan kode JS Anda (tekan cmd+o di macOS / Ctrl+o di Windows) dan pilih file Anda untuk di-debug, klik baris yang ingin di debug dan refresh kembali halaman dengan (F5). menggunakan Node.js dengan Visual Studio Code, kita dapat menekan tab debug.

### **Data Types**
- Primitive adalah tipe data dasar yang tersedia secara langsung pada suatu bahasa pemrograman.
	- Numbers
		```
		let=3;//nilai berupa angka
		```
	- Strings
		```
		let name = "lisa";//nilai berisi karakter
		```
	- Booleans 
		```true``` atau ```false```
		```
		let a = 2;
		let b = 2;
		let c = 3;
		(x == b)       // Returns true
		(x == c)       // Returns false
		```

	- undefined
		```
		let mobil;//nilai tidak didefinisikan
		mobil = undefined;
	- null
		```
		let mobil = null;//nilai kosong
		```
- Non-Primitive adalah tipe data yang didefinisikan sendiri oleh programmer dan biasanya berisi lebih dari satu nilai.
	- Objects, berisi kumpulan property (props), setiap property berisi pasangan key:value
		```
		const orang = {nama:"John", umur:18, tinggi:150};
		```
	- Arrays adalah tipe data yang dapat menampung banyak value
		```
		const sepatu = ["adidas", "nike"];
		```
- **Math** adalah objek bawaan yang memiliki property dan method untuk perhitungan matematika.
	- Math Methods
		- ```Math.round(x)``` dibulatkan ke bilangan bulat terdekat
		- ```Math.ceil(x)``` dibulatkan ke atas ke bilangan bulat terdekat
		- ```Math.floor(x)``` dibulatkan ke bawah ke bilangan bulat terdekat
		- ```Math.trunc(x)``` Mengembalikan bagian bilangan bulat dari x
		- ```Math.sign(x)``` mengembalikan jika x negatif, null atau positif
		- ```Math.pow(x,y)``` nilai x ke pangkat y
		- ```Math.sqrt(y)``` akar kuadrat dari x
		- ```Math.abs(x)``` nilai absolut (positif) dari x
		- ```Math.min(x)``` dan ```Math.max(x)``` menemukan nilai terendah atau tertinggi dalam daftar 
		- ```Math.random()``` mengembalikan angka acak antara 0 (inklusif), dan 1 (eksklusif)
### **DOM**
- **DOM** adalah singkatan dari (Document Object Model). Ini dalah sebuah interface yang memungkinkan Anda sebagai developer untuk memanipulasi style, konten dari sebuah website. 
- Mengambil Elemen HTML
	- Nama Class
		```
		let elements  = document.getElementsByClassName(name);
		```
	- Nama ID
		```
		const myElement = document.getElementById("demo");
		```
	- Nama Tag
		```
		const collection = document.getElementsByTagName("li");
		```
	- Nama
		```
		let elements = document.getElementsByName("fname");
		```
- Mengubah Konten Element
	- Element.textContent digunakan untuk mengubah teks dalam HTML
		```
		<p id="paragraf"></p>
		```
		```
		document.getElementById("paragraf").textContent="Lorem ipsum"
		```
		hasil
		```
		<p id="paragraf">Lorem ipsum</p>
		```
	- Element.innerHTML berbeda dengan textContent, innerHTML dapat mengubah konten dalam HTML
		```
		<ul id="product"></ul>
		```
		```
		document.getElementById("product").innerHTML="<li>candy</li>"
		```
		hasil
		```
		<ul id="product"><li>candy</li></ul>
		```
- JavaScript HTML DOM Events, 
JavaScript dapat dieksekusi ketika suatu peristiwa terjadi, contohnya
	- Ketika pengguna mengklik mouse
	- Ketika halaman web telah dimuat
	- Saat gambar telah dimuat
	- Saat mouse bergerak di atas elemen
	- Ketika bidang input diubah
	- Saat formulir HTML dikirimkan
	- Saat pengguna menekan tombol

- **addEventListener()** method dalam JavaScript yang menunggu event terjadi. Contoh sederhana dari suatu peristiwa adalah pengguna mengklik mouse atau menekan tombol pada keyboard.
	```
	//mencari id pada html
	const element = document.getElementById("myBtn");

	//tambahkan eventlistener clink maka function myFunction() akan dieksekusi
	element.addEventListener("click", myFunction);

	function myFunction() {
	//saat myFunction() dieksekusi id="demo" innerHTML akan mengubah konten HTML <p id="demo">Hello World</p>
	document.getElementById("demo").innerHTML = "Hello World";
	}
	```
	


