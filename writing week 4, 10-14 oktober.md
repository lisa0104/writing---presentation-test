# Writing and Presentation Test 10-14 september
### **Async await dan Fetch**

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

### **Responsive Web Desain**

- **Desain responsive** adalah desain yang memungkinkan berbagai jenis device menampilkan situs sesuai ukuran layar perangkat. Baik itu desktop, tablet, hingga mobile.Tanpa desain yang responsive, user experience pengguna akan terganggu.

- kita dapat menggunakan tools untuk melihat viewport mobile website pada google chrome dengan klik kanan->inspect->Ctrl + Shift + M

- **Viewport** merupakan area yang dapat dilihat oleh pengguna kita pada halaman website. Ukuran viewport bervariasi berdasarkan peranti. Ukuran viewport pada sebuah peranti mobile, lebih kecil dibandingkan dengan layar komputer.
- menyertakan elemen <meta> viewport pada  halaman web
	```
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	```
- ```content="width=device-width```mengatur lebar halaman untuk mengikuti lebar layar perangkat (yang akan bervariasi tergantung pada perangkat).

- ```initial-scale=1.0"``` ini mengatur tingkat zoom awal saat halaman pertama kali dimuat oleh browser.

- CSS memiliki beberapa unit berbeda untuk menyatakan panjang.

- Satuan panjang relative menentukan panjang relatif terhadap properti panjang lainnya. Skala unit panjang relatif lebih baik antara media rendering yang berbeda.
	- ```em```	Relatif terhadap ukuran font elemen (2em berarti 2 kali ukuran font saat ini)
		```
		<style>
		span {
		font-size: 16px;
		line-height: 2em;
		}
		</style>
		```
	- ```ex```	Relatif terhadap x-height dari font saat ini (jarang digunakan)

	- ```ch```	Relatif terhadap lebar "0" (nol)	
		```
		span {
		font-size: 3ch;
		}
		```
	- ```rem```	Relatif terhadap ukuran font elemen root
		```
		div {
		font-size: 2rem;
		}
		```
	- ```vw```	Relatif terhadap 1% dari lebar viewport*
		```
		h3 {
		font-size: 10vw;
		}
		```
	- ```vh```	Relatif terhadap 1% dari ketinggian viewport*
		```
		h6 {
		font-size: 10vh;
		}
		```
	- ```vmin```	Relatif terhadap 1% dari viewport* dimensi yang lebih kecil
		```
		h1 {
		font-size: 15vmin;
		}
		```
	- ```vmax```	Relatif terhadap 1% dari viewport* dimensi yang lebih besar
		```
		h1 {
		font-size: 15vmax;
		}
		```
	- ```%```	Relatif terhadap elemen parent
		```
		h1 {
		font-size: 150%;
		}
		```

- **Media Query** mengatur style yang berbeda apabila menggunakan ukuran device yang berbeda pula. 
	```
	@media only screen and (max-width: 600px) {
	body {
		background-color: white;
	}
	}
	```
	contoh diatas menjelaskan apabila browser berukuran 600 piksel atau lebih kecil, warna latar belakang akan menjadi putih

- **flexbox dan grid**
- Flexbox responsif, jika kita membuat layout dua kolom untuk sebagian besar ukuran layar, dan layout satu kolom untuk ukuran layar kecil (seperti ponsel dan tablet), Anda dapat mengubah ```flex-direction``` dari ```row``` ke ```column``` pada ukuran kurang dari atau  800px
	```
	.flex-container {
	display: flex;
	flex-direction: row;
	}
	@media (max-width: 800px) {
	.flex-container {
		flex-direction: column;
	}
	}
	```
- grid resposif, 
semua elemen HTML memiliki box-sizing properti yang disetel ke border-box
	```
	* {
	box-sizing: border-box;
	}
	```
	ukuran width diatur dengan satuan %
	```
	.menu {
	width: 25%;
	float: left;
	}
	.main {
	width: 75%;
	float: left;
	}
	```
### **Bootstrap**
- **Bootstrap** adalah kerangka kerja CSS yang open source dan bebas untuk merancang situs web dan aplikasi web. Kerangka kerja ini berisi templat desain berbasis HTML dan CSS untuk tipografi, formulir, tombol, navigasi, dan komponen antarmuka lainnya, serta juga ekstensi opsional JavaScript.

- Bootstrap memudahkan kita dalam membuat aplikasi web, kita cukup memanggil 
- cara mudah untuk menggunakan Bootstrap adalah dengan copy-paste stylesheet <link>ke <head>
	``` 
	<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.6.2/dist/css/bootstrap.min.css" integrity="sha384-xOolHFLEh07PJGoPkLv1IbcEPTNtaed2xpHsD9ESMhqIYd0nLMwNLD69Npy4HI+N" crossorigin="anonymous">
	```
- **Containers**  adalah elemen layout paling dasar di Bootstrap dan diperlukan saat menggunakan grid. Containers  digunakan untuk menampung, melapisi, dan (terkadang) memusatkan konten di dalamnya. 
Bootstrap hadir dengan tiga Containers  berbeda:
	- ```container```, yang menetapkan ```max-width``` pada setiap breakpoint responsif
		```
		<div class="container">
		</div>
		```
	- ```container-fluid```, yaitu ```width: 100%``` di semua breakpoints
		```
		<div class="container-fluid">
		</div>
		```
	- ```container-{breakpoint}```, yaitu ```width: 100%``` hingga breakpoint yang ditentukan
- content pada bootstrap
	- images
		```
		<img src="..." class="rounded float-right" alt="...">
		```
	- tabel
		```
			<table class="table table-dark">
		<thead>
			<tr>
			<th scope="col">#</th>
			<th scope="col">Nama depan</th>
			<th scope="col">Nama Belakang</th>
			</tr>
		</thead>
		<tbody>
			<tr>
			<th scope="row">1</th>
			<td>Mark</td>
			<td>Otto</td>
			</tr>
			<tr>
			<th scope="row">2</th>
			<td>Jacob</td>
			<td>Thornton</td>
			</tr>
		</tbody>
		</table>
		```
	- text
		```
		<h3>
		Fancy display heading
		<small class="text-muted">With faded secondary text</small>
		</h3>
		```
- component pada bootstrap
	- alerts / peringatan
		```
		<div class="alert alert-primary" role="alert">
		A simple primary alert—check it out!
		</div>
		```
	- badge /lencana
		```
		<span class="badge badge-primary">Primary</span>
		```
	- breadcrumb digunakan untuk lokasi halaman/ navigasi
		```
		<nav aria-label="breadcrumb">
		<ol class="breadcrumb">
			<li class="breadcrumb-item"><a href="#">Home</a></li>
			<li class="breadcrumb-item"><a href="#">Library</a></li>
			<li class="breadcrumb-item active" aria-current="page">Data</li>
		</ol>
		</nav>
		```
	- buttons /tombol
		```
		<button type="button" class="btn btn-success">Success</button>
		```
	- card
		```
		<div class="card">
			<div class="card-body">
				text didalam card
			</div>
		</div>
		```
	- Carousel/ slide gambar atau teks
		```
		<div id="carouselExampleSlidesOnly" class="carousel slide" data-ride="carousel">
		<div class="carousel-inner">
		<div class="carousel-item active">
			<img src="..." class="d-block w-100" alt="...">
		</div>
		<div class="carousel-item">
		<img src="..." class="d-block w-100" alt="...">
		</div>
		<div class="carousel-item">
		<img src="..." class="d-block w-100" alt="...">
		</div>
		</div>
		</div>
		```
	
	- Dropdowns
		```
		<div class="dropdown">
		<button class="btn btn-secondary dropdown-toggle" type="button" data-toggle="dropdown" aria-expanded="false">
			Dropdown button
		</button>
		<div class="dropdown-menu">
			<a class="dropdown-item" href="#">Action</a>
			<a class="dropdown-item" href="#">Another action</a>
			<a class="dropdown-item" href="#">Something else here</a>
		</div>
		</div>
		```
- responsif pada bootstrap
	``` 
	// Small devices (landscape phones, 576px and up)
	@include media-breakpoint-up(sm) { ... }
	// Medium devices (tablets, 768px and up)
	@include media-breakpoint-up(md) { ... }
	// Large devices (desktops, 992px and up)
	@include media-breakpoint-up(lg) { ... }
	// Extra large devices (large desktops, 1200px and up)
	@include media-breakpoint-up(xl) { ... }
	```