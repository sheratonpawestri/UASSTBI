# UAS Sistem Temu Kembali Informasi
MKOM --- 14 Desember 2022 --- 13.00 - 15.00
Sheraton Pawestri -- 21/486087/PPA/06234

====================================================================================

## NO 1
Soal : Jelaskan secara detail metode kueri pencarian dan similarity search pada proyek anda.

== JAWABAN == 

Metode == Metode yang digunakan adalah brute force dalam string matching. 
Setiap aksara Jawa (20 aksara dasar) dan contoh penggunaannya (contoh dalam kata dan kalimat) akan disimpan dalam bentuk gambar (.jpg). 
Masing-masing gambar tersebut akan diberi label secara manual sesuai dengan cara baca dari masing-masing aksara Jawa. 
Misal pada gambar 'ha' akan disimpan ke file gambar bernamakan 'ha.jpg'. 
Sistem akan menerima query berupa huruf latin dari aksara Jawa. 
Selanjutnya akan dilakukan prapemrosesan query oleh sistem, lalu query akan dibandingkan dengan label gambar aksara Jawa menggunakan brute force string matching. 
Brute force string matching adalah algoritma algoritma pencocokan string secara straight forward, 
yaitu pencarian pola dilakukan secara satu per satu dalam suatu teks dari kiri atau kanan sampai akhir dari string tersebut. 
Apabila terdapat salah satu karakter dari pola yang tidak sesuai dengan teks, maka pencarian ulang akan dilakukan dari awal pola yang ada. 
Output dari sistem ini adalah gambar aksara Jawa yang sesuai dengan query. Berikut ini adalah rincian spesifikasi sistem yang dikembangkan.

Dataset == Dataset yang digunakan:
dataset gambar (https://drive.google.com/drive/u/0/folders/1_TK-ucIKJ_XXNo8glEiKKZIR5Uf1xpHs) 

dataset tulisan (https://docs.google.com/spreadsheets/d/1QonddxFSpJjHX5SawXdCulpeJc7ou1lGIyl3EPJ-j-o/edit#gid=0)

Dataset yang digunakan adalah gambar aksara Jawa yang berasal dari dataset Gamatutor dan contoh penggunaan aksara Jawa dalam kata dan kalimat. Aksara Jawa yang digunakan dibatasi pada bentuk dasar saja yang belum mendapatkan imbuhan atau sandhangan.

Prapemorosesan == Pada dataset tulisan, query pada sistem ini berupa huruf latin dari aksara Jawa. Misalnya “ha”, “na”, “ca”, dan seterusnya. Praproses yang akan dilakukan pada data teks query yaitu case folding. Contohnya untuk query “Ha” akan diubah menjadi “ha” untuk proses matching pada label gambar. 

Pada dataset gambar, prapemrosesan yang dilakukan pada gambar daftar huruf aksara Jawa adalah dengan cropping gambar satu-satu. Sehingga yang awalnya terdapat 1 gambar hanacaraka, menjadi 20 gambar ha, na, ca, ra, ka, dll. Kemudian dari setiap huruf tadi akan diberi label berupa nama gambar sesuai dengan bacaannya. Misalnya untuk gambar di bawah ini akan diberi nama gambar yaitu ‘ha.jpg’. Begitu pula dengan kata dan kalimat. Penelitian ini menentukan kata-kata apa saja dan kalimat yang berbentuk aksara jawa lalu diberi nama file sesuai kata atau kalimat tersebut. Misal pada gambar 'hanoman' disimpan dalam bentuk gambar dengan nama file 'hanoman.jpg'.

Query == aksara latin untuk satu aksara jawa. Misal 'ha' atau 'na' tapi penelitian ini belum mampu menampilkan kata seperti 'aku'.

Output == keluaran berupa gambar yang sesuai dengan input. Jika input 'ha', maka akan keluar gambar aksara ha dan beberapa contohnya pada kata dan kalimat.

Metode pencocockan (string matching) == Pada penelitian ini digunakan brute force string matching sebagai metode pencocokan. Brute force string matching  merupakan sebuah metode pencarian pola dari sebuah string pada teks. Misalkan terdapat string x yang memiliki panjang karakter m, akan dicocokkan dengan teks y yang memiliki panjang karakter n. Proses pencocokan string dimulai dengan menempatkan window string dari 0 sampai m pada awal teks. Kemudian, karakter pada window akan dibandingkan dengan karakter pada teks dari arah kiri ke kanan dengan pergeseran sebanyak 1 karakter string sampai window sesuai dengan teks atau window berada pada akhir teks. 
Query pada penelitian ini bertindak sebagai string sedangkan teks yang akan dibandingkan adalah cara baca aksara Jawa.


==============================================================================================================================================

## NO 2
Soal: Metode evaluasi yang digunakan serta jelaskan hasil evaluasi