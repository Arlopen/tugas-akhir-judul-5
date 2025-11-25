# tugas-akhir-judul-5

<img width="822" height="553" alt="image" src="https://github.com/user-attachments/assets/1141c14e-56d7-4e53-b358-ce07eb11ac7b" />

Fungsi ini digunakan untuk melakukan perhitungan aritmatika dasar antara dua angka. Fungsi ini mengambil nilai dari variabel previousInput (angka pertama) dan currentInput (angka kedua), yang sebelumnya telah diubah menjadi tipe data numerik (parseFloat). Inti dari fungsi ini adalah blok try...catch yang menggunakan fungsi eval() untuk mengeksekusi ekspresi matematika, seperti num1 + num2 atau num1 * num2. Sebelum melakukan perhitungan, fungsi ini memiliki mekanisme penanganan kesalahan: jika operator adalah bagi (/) dan angka kedua (num2) adalah nol, fungsi akan segera mengatur errorState menjadi true dan mengembalikan pesan "Sihir Gagal" (Pembagian dengan Nol). Jika perhitungan berhasil, fungsi akan mengembalikan nilai hasil perhitungan (return result) agar dapat digunakan oleh bagian lain dari program, seperti handleEquals().



<img width="281" height="195" alt="image" src="https://github.com/user-attachments/assets/2e65b3f7-ea93-49ee-9166-7d03925bf931" />

Fungsi clearAll() adalah fungsi prosedural yang berfungsi untuk mereset seluruh kondisi atau state dari kalkulator. Fungsi ini tidak memerlukan parameter apa pun karena tujuannya hanyalah untuk mengembalikan kalkulator ke kondisi awal. Semua variabel global yang menyimpan status perhitungan, seperti currentInput, previousInput, operator, isNewInputNeeded, dan errorState, disetel ulang ke nilai default mereka (misalnya, 0, string kosong, atau false). Setelah mereset variabel status, fungsi ini kemudian memanggil updateDisplay() untuk memastikan bahwa tampilan di antarmuka pengguna segera mencerminkan status yang bersih (menampilkan angka '0').



<img width="982" height="465" alt="image" src="https://github.com/user-attachments/assets/949f6a29-3ed5-4ce4-8b2e-99dac5427751" />

Fungsi memory() digunakan untuk mengelola fitur memori tingkat lanjut dan merupakan contoh yang baik dari penggunaan fungsi dengan parameter untuk mengontrol perilaku. Fungsi ini menerima satu parameter, yaitu action, yang merupakan string ("MC", "MR", "M+", atau "M-") yang menentukan operasi memori mana yang harus dieksekusi. Di dalamnya terdapat logika kondisional (if/else if) untuk memeriksa nilai action. Misalnya, jika action adalah 'MC', variabel memoryValue disetel ke nol (Memory Clear). Jika action adalah 'MR', nilai dari memoryValue diambil dan disalin ke currentInput di layar (Memory Recall). Dengan menggunakan parameter, satu fungsi dapat mengimplementasikan empat perilaku berbeda.



<img width="1304" height="440" alt="image" src="https://github.com/user-attachments/assets/80fa0fa0-a3db-44d8-936c-0d59ee507511" />

Fungsi updateDisplay() digunakan untuk mengubah tampilan utama. Fungsi ini menggunakan properti innerText (resultDisplay.innerText = ...) untuk menampilkan angka dan hasil yang sedang diketik atau dihitung, serta menampilkan ekspresi yang menunggu. Selain itu, fungsi ini mengelola style error: saat errorState benar, ia menggunakan resultDisplay.classList.add('error') untuk menerapkan class CSS yang mengubah tampilan (misalnya, menjadi merah darah), dan menghapusnya saat kondisi normal.



<img width="536" height="282" alt="image" src="https://github.com/user-attachments/assets/d347a102-cb8c-4207-a0ad-4d306a28e070" />

Fungsi ini berguna untuk memasang event click secara massal pada semua tombol kalkulator (elemen dengan class .btn). Kode ini memilih semua tombol dan menambahkan listener yang memicu logika perhitungan atau memori. Saat tombol diklik, listener akan membaca atribut data-type dan data-value tombol tersebut untuk menentukan fungsi mana yang harus dipanggil (handleInput() atau memory()) dengan parameter yang tepat. Ini membuat penanganan interaksi tombol sangat efisien.

<img width="765" height="459" alt="image" src="https://github.com/user-attachments/assets/622346c0-88a9-47e1-82c2-f07efee41306" />
Fungsi ini berguna untuk mengaktifkan dukungan keyboard pada kalkulator, yang merupakan event listener global yang dipasang pada seluruh document untuk mendeteksi penekanan tombol fisik (keydown). Logikanya memeriksa tombol yang ditekan (event.key): jika tombol tersebut adalah angka, desimal, atau operator, fungsi akan memanggil handleInput() yang sesuai untuk memproses input. Selain itu, listener ini menangani tombol seperti Enter atau operator / dengan memanggil event.preventDefault(), sebuah tindakan penting yang mencegah aksi bawaan browser (seperti scrolling atau membuka fitur pencarian) agar tidak mengganggu fungsi kalkulator, sehingga menjamin operasi yang mulus melalui keyboard.
