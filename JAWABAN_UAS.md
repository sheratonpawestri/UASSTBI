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


====================================================================================

## NO 2
Soal : Metode evaluasi yang digunakan serta jelaskan hasil evaluasi

== JAWABAN ==

Sistem ini memberikan hasil pencarian yang bersifat exactly match, karena hasil yang ditampilkan adalah selalu sesuai dengan query dan dataset yang ada. Sehingga evaluasi yang digunakan menjawab pertanyaan 'apakah hasil yang ditampilkan sudah sesuai dengan query yang ditulis?'. Jawabannya iya. Misal saja masukkan query 'ha', maka akan muncul gambar yang sesuai dengan aksara tersebut seperti ha, anak, hanoman, aku mangan tahu, anak polah bapak kepradhah, jer basuki mawa bea, adikku mangan sega, sugeng rawuh ing donya, sampun dhahar acar.

Oleh karena itu, evaluasi juga dilakukan dengan menghitung waktu pencarian. Waktu pencarian dicatat untuk mengetahui waktu yang dibutuhkan untuk proses pencarian setiap query aksara sampai menampilkan hasil yang sesuai. Eksperimen dilakukan dalam tiga percobaan yang berbeda berdasarkan variasi dataset. Percobaan ke-1 menggunakan dataset yang terdiri dari 20 aksara dasar, percobaan ke-2 menggunakan dataset yang terdiri dari 36 data yaitu gabungan 20 aksara dasar dan 16 kata, serta percobaan ke-3 menggunakan dataset yang terdiri dari 51 data yaitu gabungan 20 aksara dasar, 16 kata, dan 15 kalimat.

Pada percobaan ke-1, rata-rata waktu pencarian untuk 20 aksara dasar adalah 0.1403924584 detik.

Pada percobaan ke-2, rata-rata waktu pencarian untuk 36 data adalah 0.4636428356 detik. 

Pada percobaan ke-3, rata-rata waktu pencarian untuk 51 data adalah 1.179515135 detik. 

Berdasarkan percobaan yang dilakukan, diketahui bahwa waktu pencarian berbanding lurus dengan jumlah data yang ada. Semakin banyak jumlah data yang dimiliki, maka waktu pencarian yang dibutuhkan semakin lama. Sedangkan prapemrosesan berupa lowercase diketahui tidak begitu mempengaruhi kecepatan proses pencarian karena berbagai bentuk variasi input yang telah dicoba memberikan hasil waktu pencarian yang cepat dengan perbedaan waktu di bawah 0.1 detik.


====================================================================================

## NO 3
Soal : Perbedaan sistem rekomendasi dan sistem tanya jawab.

== JAWABAN ==

Sistem rekomendasi: Sistem yang memberikan feedback berupa jawaban dari beberapa query yang diinputkan. Query bisa berupa beberapa keyword atau klik tombol pilihan keyword yang ada pada sistem yang kemudian dicari rekomendasinya. Misal pada sistem rekomendasi anime yang akan ditonton. Pada halaman website yang menyediakan anime legal gratis akan menampilkan beberapa genre seperti action, romance, comedy, slice of life, dan lain-lain. Kemudian user akan klik 'comedy' jika ingin menonton anime bergenre comedy kemudian akan muncul beberapa anime yang bergenre comedy.

Sistem tanya jawab: Sistem memberikan feedback berupa jawaban dari query yang biasanya berupa pertanyaan. Sistem tersebut akan mencari jawaban yang ada pada database sistem berdasarkan pertanyaan tersebut. Biasanya dilakukan similarity antar pertanyaan-pertanyaan yang sudah terdapat pada database sistem. 
Contohnya adalah bot chat. 
Misal kita bertanya pada bot 'apa kamu sudah makan?' maka bot tersebut akan memproses pertanyaan tersebut dengan menyamakan pertanyaan tersebut dengan yang ada di database bot. Kemudian setelah itu bot bisa menentukan jawaban berdasarkan database yang ada pada bot tersebut. 
Misal jawaban untuk 'sudah makan belum' adalah 'aku ga makan ga minum.' maka bot akan menampilkan kalimat tersebut. 

Pada penelitian ini, digunakan sistem tanya jawab sehingga jika kita klik suatu keyword kemudian akan muncul informasi yang sesuai dengan keyword tersebut. Dalam penelitian ini digunakan string matching untuk mencocokkan antara query dengan informasi yang diterima.

====================================================================================

## NO 4
a. Soal : rangkuman proyek STBI




b. Soal : Apakah proyek anda termasuk multimedia information retrieval system?

Untuk dataset berupa gambar (multimedia), namun yang dilakukan penelitian ini adalah pencocokan antar teks. oleh karena itu, lebih tepat jika penelitian ini termasuk 
teks information retrieval system yang mengeluarkan informasi berupa gambar (multimedia).
