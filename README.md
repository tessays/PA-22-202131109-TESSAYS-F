
# uas pengolahan citra - Deteksi gambar dan bentuk menggunakan countur 

Kontur didefinisikan sebagai garis yang menghubungkan semua titik di sepanjang batas suatu citra yang memiliki intensitas yang sama. Kontur berguna dalam analisis bentuk, menemukan ukuran objek yang menarik, dan deteksi objek.

1.Deteksi tepi canny 
Detektor tepi cerdik adalah algoritme multi-tahap untuk mendeteksi tepi dalam gambar. Itu dibuat oleh John F. Canny pada tahun 1986 dan diterbitkan dalam makalah " A Computational Approach to Edge Detection ". Ini adalah salah satu teknik paling populer untuk deteksi tepi, bukan hanya karena kesederhanaannya, tetapi juga karena menghasilkan hasil berkualitas tinggi.
    Algoritma Canny edge detector memiliki empat langkah:
A.Pengurangan noise dengan mengaburkan gambar menggunakan Gaussian blur.
B.Menghitung gradien intensitas gambar.              
C.Penindasan Tepi.     
D.Menggunakan ambang batas histeresis.

2.Deteksi Kontur
Kontur adalah blok bangunan dasar untuk visi komputer. Merekalah yang memungkinkan komputer untuk mendeteksi bentuk dan ukuran umum objek yang ada dalam gambar sehingga dapat diklasifikasikan, disegmentasi, dan diidentifikasi.                                  
    Menggunakan OpenCV, kita dapat menemukan kontur dengan mengikuti langkah-langkah berikut:
Ubah gambar menjadi gambar biner. Kita bisa menggunakan thresholding atau edge detection. Kami akan menggunakan detektor tepi Canny.Lalu Temukan kontur menggunakan fungsi cv2.findContours.Gambar kontur pada gambar menggunakan fungsi cv2.drawContours.     

Langkah- langkah mendeteksi gambar menggunakan kontur :
1.Menggunakan import cv,numpy as np dan matplotlib untuk membuat array numerik dalam pemprosesan gambar.pyplot untuk membuat visualiasi seperti gambar.             

2.cv2.imread('topi.jpeg'): Fungsi ini digunakan untuk membaca gambar dari file dengan nama 'topi.jpeg' dan mengembalikan gambar dalam bentuk matriks dengan nilai piksel.
cv2.cvtColor(image, cv2.COLOR_BGR2RGB): Fungsi ini digunakan untuk mengubah format warna gambar dari BGR (Blue-Green-Red) ke RGB (Red-Green-Blue). Format warna BGR umum digunakan dalam OpenCV, sementara format warna RGB lebih umum digunakan dalam visualisasi gambar di Matplotlib.                            OpenCV memiliki findContour()fungsi yang membantu dalam mengekstraksi kontur dari gambar.               

3.Gunakan cv2.RETR_EXTERNAL kita untuk mengambil kontur luar objek pada gambar dan cv2.CHAIN_APPROX_SIMPLE yang akan mengompresi segmen horizontal, vertikal, dan diagonal untuk mempertahankan hanya titik akhirnya.                   

4.Selanjutnya, kita membuat salinan dari gambar asli yang akan kita gunakan untuk menggambar kontur di atasnya. Menggambar kontur dilakukan dengan menggunakan fungsi cv2.drawContours (image_copy, contours, -1, (0, 255, 0), 3).
Argumen pertama untuk fungsi ini adalah gambar yang ingin kita gambar konturnya. Sekali lagi, kami telah menggambar kontur pada salinan gambar karena kami tidak ingin mengubah gambar aslinya.
Argumen kedua adalah kontur dan argumen ketiga adalah indeks kontur yang akan digambar, menggunakan nilai negatif akan menggambar semua kontur.
Argumen keempat adalah warna kontur dan argumen terakhir adalah ketebalan garis kontur.      

5.Gunakan binary = np.zeros_like(image_rgb): Sintaks ini membuat array yang sama ukurannya dengan image_rgb tetapi dengan semua elemen bernilai nol. Array ini akan digunakan sebagai citra biner, di mana kontur akan diisi dengan warna putih. 
dan cv2.drawContours(binary, contours, -1, (255, 255, 255), thickness=cv2.FILLED): Fungsi ini digunakan untuk menggambar kontur pada citra binary. dimana argumen pertama adalah citra dimana kontur akan digambar,argumen kedua adalah daftar kontur yang akan digambar,argumen ketiga adalah indeks kontur yang akan digambar, argumen selanjutnya adalah warna kontur yaitu RGB dan argumen terakhir yaitu ketebalan garis kontur. 

6.Selanjutnya gunakan fungsi fig, axes = plt.subplots(1, 3, figsize=(10, 10)): Sintaks ini digunakan untuk membuat satu gambar dengan tiga sumbu (axes) secara sejajar (1 baris dan 3 kolom). Setiap sumbu akan digunakan untuk menampilkan gambar secara terpisah.Fungsi plt.subplots() mengembalikan objek Figure dan array Axes yang berisi sumbu-sumbu yang digunakan untuk menampilkan gambar. Objek Figure adalah gambar utama yang berisi satu atau lebih sumbu.                     
ax = axes.ravel(): Sintaks ini mengubah array dua dimensi axes menjadi array satu dimensi ax. Fungsi ravel() digunakan untuk meratakan array dua dimensi menjadi satu dimensi secara berurutan.Setiap sumbu (ax[0], ax[1], dan ax[2]) dapat digunakan untuk menampilkan gambar secara terpisah pada setiap sumbu tersebut



TESSA YOLANDA SITORUS                 
202131109                               
PENGOLAHAN CITRA F