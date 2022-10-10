# Writing and Presentation Test 3-7 oktober

### **Array**

- **Array** merupakan struktur data yang digunakan untuk menyimpan sekumpulan data dalam satu tempat

	```
	const students = ['lisa', 'eka', 'eki'];
	```
- Array didefinisikan menggunakan square brackets ````[]```
- indeks dalam array dimulai dari 0, data 'lisa' merupakan data indeks 0
- cara memanggil data spesifik dengan ```namavariabel[indeks]```
	```
	let buah = ['manggis', 'mangga', 'apel'];
	console.log(buah[1]);
	```
	maka output yang didapatkan adalah mangga
- kita dapat mengupdate data dalam array 
	```
	let buah = ['manggis', 'mangga', 'apel'];
	let buah[1]='jeruk'
	console.log(buah);
	```
-  properti Array  yang sering digunakan yaitu
	- constructor berfungsi mengembalikan fungsi
		```
		const warna = ['merah', 'kuning', 'biru'];
		let text = warna.constructor;
		```
	- length berfungsi menghitung panjang array
		```
		const warna = ['merah', 'kuning', 'biru'];
		let length = warna.length;
		```
- method array
	- array push, menambah elemen pada array di akhir
		```
		const warna = ['merah', 'kuning', 'biru'];
		warna.push("hijau");
		```
	- array pop, menghapus elemen array yang paling akhir
		```
		const warna = ['merah', 'kuning', 'biru'];
		warna.pop();
		```
	- array shift, menghapus elemen array yang paling depan
		```
		const warna = ['merah', 'kuning', 'biru'];
		warna.shift();
		```
	- array unshift, mengembalikan nilai panjang array yang baru
		```
		const warna = ['merah', 'kuning', 'biru'];
		warna.unshift('biru');
		```
- looping array
	- ```forEach()``` perulangan yang dilakukan pada semua elemen array
		```
		const warna = ['merah', 'kuning', 'biru'];
		warna.forEach(myFunction);
		```
	- ```map()``` perulangan yang dilakukan dengan membuat array baru
		```
		const sisi = [5, 11, 12, 19];
		const luas = sisi.map(luasPersegi)

		function luasPersegi(num) {
		return num * num;
		}
		```
- **Multi-dimensional Array** adalah array yang menyimpan array lain pada setiap indeks, bukan elemen tunggal. Dengan kata lain, kita dapat mendefinisikan array multi dimensi sebagai array dari suatu array. singkatnya adalah array didalam array
	```
	var kar1 = ["lisa", 22, 2000];
	var kar2 = ["eka", 23, 1999];
	var kar3 = ["eki", 24, 1998];
	var kar4 = ["edi", 22, 2000];
	var kar5 = ["bambang", 24, 1998];
	var karyawan = [kar1, kar2, kar3, kar4, kar5]; 
	for(var i = 0; i < karyawan.length; i++) {
		document.write(karyawan[i] + "<br>");
	}
	```
### **Object**
- **Object** adalah sekumpulan list dari tipe data primitif (terkadang juga tipe data reference) yang menyimpan nilai dengan konsep berpasangan name-value. Tiap item (yang lebih dikenal dengan nama variabel) disebut dengan property, dan function disebut dengan method.
	```
	let buah = {nama:"jeruk", warna:"oren", bentuk:"bulat"};
	```
- mengakses properti object
	```
	let buah = {nama:"jeruk", warna:"oren", bentuk:"bulat"};
	console.log(buah.warna);
	```
- bisa juga memanggil properti object menggunakan bracket notation
	```
	let buah = {nama:"jeruk", warna:"oren", bentuk:"bulat"};
	console.log(buah[warna]);
	```
- update data object
	```
	let buah = {nama:"jeruk", warna:"oren", bentuk:"bulat"};
	buah.warna="kuning";
	console.log(buah);
	```
- menambahkan data baru
	```
	let buah = {nama:"jeruk", warna:"oren", bentuk:"bulat"};
	buah.jumlah=2;
	console.log(buah);
	```
- menghapus data 
	```
	let buah = {nama:"jeruk", warna:"oren", bentuk:"bulat"};
	delete buah.warna;
	console.log(buah);
	```
- Nested Object adalah object yang berasal dari turunan object lainya

- Pass by Reference adalah salah satu metode pemberian argument kepada function parameter saat pemanggilan function, dengan memanfaatkan reference pada function parameter
- Array of Object, array yang terdiri dari banyak object
	```
	let buah =[ 
		{nama:"jeruk", warna:"oren", bentuk:"bulat"},
		{nama:"semangka", warna:"hijau", bentuk:"bulat"},
		{nama:"durian", warna:"hijau", bentuk:"berduri"}
		];
### **Rekursif**
-  Rekursif adalah suatu proses atau prosedur dari fungsi yang memanggil dirinya sendiri secara berulang-ulang.
- Rekrusif harus dibuktikan bisa berhenti, karena jika tidak maka akan terjadi error/ infinity loop
- fungsi rekrusif memecahkan masalah dengan terus memanggil dirinya sendiri, memecah masalah menjadi bagian bagian kecil, agar lebih mudah.
	```
	function penjumlahan(bil){
		if (bil === 0) {
			return 0;
		} else {
			return bil + penjumlahan(--bil)
		}
	}
	penjumlahan(5);   
	```
	output dari function diatas 15, function penjumlahan() akan terus memanggil dirinya sendiri sampai bil=0

### **Asynchronous**
- Asynchronous hasil eksekusi atau output tidak selalu berdasarkan urutan kode, tetapi berdasarkan waktu proses. Eksekusi dengan asynchronous tidak akan membloking atau menunggu suatu perintah sampai selesai. Daripada menunggu, asynchronous akan mengeksekusi perintah selanjutnya.

	```
	console.log('Hello');
	setTimeout(() => { console.log('Javascript')},100) // tunda selama 100 miliseconds
	console.log('Coder');
	```
- Callback di eksekusi dalam function lain melalui parameter

	```
	function main(param1,param2,callBack){ 
	console.log(param1, param2) 
	callBack()  
	}

	function myCallback(){ 
	console.log ('hello callback')
	}

	main(1,2,myCallback)
	```
	Function dapat dijadikan parameter
- Promise adalah salah satu fitur baru di ES6, biasa digunakan untuk melakukan http request/fetch data dari API. ada 3 kemungkinan state :
	- Pending ( sedang dalam proses )
	- Fulfilled ( berhasil )
	- Rejected ( gagal )
	```
	function myDisplayer(some) {
	document.getElementById("demo").innerHTML = some;
	}
	let myPromise = new Promise(function(myResolve, myReject) {
	let x = 0;
	if (x == 0) {
		myResolve("berhasil");
	} else {
		myReject("Error");
	}
	});
	myPromise.then(
	function(value) {myDisplayer(value);},
	function(error) {myDisplayer(error);}
	);
	```
- async and await membuat promise lebih mudah ditulis, async mengubah function menjadi asynchronous, await menunda eksekusi hingga proses asynchronous selesai
	```
	async function myDisplay() {
	let myPromise = new Promise(function(resolve, reject) {
		resolve("I love You !!");
	});
	document.getElementById("demo").innerHTML = await myPromise;
	}
	```
- Fetch API adalah API untuk membuat network reques yang mirip dengan XMLHttpRequest (XHR). Perbedaan utama adalah bahwa Fetch API menggunakan Promise, hingga API lebih sederhana dan mudah dibaca.

	contoh apabila kita memiliki data json yang terletak di server web dan memuat data user

	```
	async function getUsers() {
		let url = 'users.json';
		try {
			let res = await fetch(url);
			return await res.json();
		} catch (error) {
			console.log(error);
		}
	}
	```
	membuat function getUsers()fungsi yang diambil users.json dari server
	```
	async function renderUsers() {
		let users = await getUsers();
		let html = '';
		users.forEach(user => {
			let htmlSegment = `<div class="user">
								<img src="${user.profileURL}" >
								<h2>${user.firstName} ${user.lastName}</h2>
								<div class="email"><a href="email:${user.email}">${user.email}</a></div>
							</div>`;

			html += htmlSegment;
		});

		let container = document.querySelector('.container');
		container.innerHTML = html;
	}

	renderUsers();
	```
	function renderUsers() yang merender data pengguna

### **Web Storage**
- LocalStorage merupakan salah satu cara yang dapat digunakan untuk menyimpan data di web browser. Pada localStorage penyimpanan data tidak memiliki kadaluarsa, artinya data yang disimpan tetap ada meskipun browser telah ditutup.
- SessionStorage menyimpan data secara sementara, data akan menghilang saat tab ditutup atau browser ditutup

- SetItem() digunakan untuk menyimpan data kedalam localStorage dibutuhkan dua parameter yaitu key dan value
	```
	window.localStorage.setItem('Alat', 'gunting');
	window.localStorage.setItem('Buah','Apel');
	```
- getItem() digunakan untuk mengakses data yang disimpan pada localStorage
	```
	let val = localStorage.getItem('Buah'));
  	console.log(val)
	```
- removeItem() digunakan untuk menghapus data tertentu pada penyimpanan localStorage kalian bedasarkan key.
	```
	window.localStorage.removeItem('Buah')
	```
- clear() digunakan untuk menghapus seluruh data yang telah tersimpan di localStorage
	```
	window.localStorage.clear()
	```
- Memeriksa Item menggunakan ```if```
	```
	if (localStorage.length > 0) {
	// ...
	} else {
	// ...
	}
	```
- Mengulangi item di localStorage menggunakan ```for```
	```
	for (let i = 0; i < localStorage.length; i++){
	let key = localStorage.key(i);
	}
	```