# <h1 align="center">Laporan Praktikum Modul Tipe Data</h1>
<p align="center">Egi Rizkiyansyah</p>

## Dasar Teori
1. Program untuk Menampilkan Output Berdasarkan Input Pengguna:

Dasar Teori:
Program ini mengilustrasikan konsep pengambilan input dari pengguna melalui keyboard dan menampilkan output berdasarkan input tersebut.
Input dari pengguna (nama, umur, pekerjaan) disimpan dalam variabel yang sesuai.
Output ditampilkan menggunakan fungsi print().

2. Program Input Array Tiga Dimensi dengan Ukuran yang Diinputkan Pengguna:

Dasar Teori:
Program ini menunjukkan bagaimana mengonfigurasi array tiga dimensi dengan ukuran yang ditentukan oleh pengguna.
Input dari pengguna berupa jumlah elemen untuk setiap dimensi array.
Program menggunakan nested loop untuk membuat array tiga dimensi sesuai dengan ukuran yang dimasukkan pengguna.
Output program adalah array tiga dimensi yang telah dibuat.

3. Program Menu untuk Mencari Nilai Maksimum, Minimum, dan Nilai Rata-rata dari Array dengan Input Pengguna:

Dasar Teori:
Program ini menunjukkan bagaimana membuat menu interaktif untuk melakukan operasi pada array yang dimasukkan oleh pengguna.
Input dari pengguna mencakup jumlah elemen array dan nilai-nilai array itu sendiri.
Program menampilkan menu pilihan kepada pengguna dan kemudian memproses pilihan pengguna untuk mencari nilai maksimum, minimum, atau rata-rata dari array.
Output program adalah hasil operasi sesuai dengan pilihan pengguna.
Semua program tersebut memperlihatkan bagaimana komunikasi antara pengguna dan program dapat digunakan untuk memperoleh informasi, melakukan operasi, dan menampilkan hasil yang relevan kepada pengguna. Ini mencerminkan konsep dasar dalam pemrograman interaktif dan pemahaman dasar struktur data.

## Guided 

### 1. [Program Input Array Tiga Dimensi]

```C++
#include <iostream>
using namespace std;
// PROGRAM INPUT ARRAY 3 DIMENSI
int main()
{
    //Deklarasi Array
    int arr[2][3][3];
    // Input Elemen
    for (int x = 0; x < 2; x++)
    {
        for (int y = 0; y < 3; y++)
        {
            for (int z = 0; z < 3; z++)
            {
                cout << "Input Array[" << x << "][" << y << "][" << z << "] = ";
                cin >> arr[x][y][z];
            }
        }
        cout << endl;
    }
    // Output Array
    for (int x = 0; x < 2; x++)
    {
        for (int y = 0; y < 3; y++)
        {
            for (int z = 0; z < 3; z++)
            {
                cout << "Data Array[" << x << "][" << y << "][" << z << "] = " << arr[x][y][z] << endl;
            }
        }
    }
    cout << endl;
    // Tampilan Array
    for (int x = 0; x < 2; x++)
    {
        for (int y = 0; y < 3; y++)
        {
            for (int z = 0; z < 3; z++)
            {
                cout << arr[x][y][z] << ends;
            }
            cout << endl;
        }
        cout << endl;
    }
}
```
#### Full code Screenshot:
![Screenshot 2024-03-19 191515](https://github.com/egirizkiyan/ndak-tau/assets/162097461/f05777a8-4103-464b-87ee-3b8c5871795c)

#### Output:
![Screenshot 2024-03-19 192703](https://github.com/egirizkiyan/laporan-praktikum-alpro-egi-rizkiyansyah-2311110042/assets/162097461/8bebf211-498d-4155-b5f5-7c097b69bb8b)

Kode program di atas merupakan contoh implementasi array tiga dimensi dalam bahasa pemrograman C++. Program ini dibuat untuk melakukan input, output, dan menampilkan array tiga dimensi.
Pada bagian awal, dilakukan deklarasi array dengan ukuran 2 x 3 x 3. Kemudian, dilakukan proses input elemen array menggunakan tiga perulangan bersarang untuk mengakses setiap elemen array. Pengguna diminta untuk memasukkan nilai dari setiap elemen array.
Setelah nilai-nilai array dimasukkan, dilakukan output nilai-nilai array tersebut dengan menyertakan indeksnya dalam perulangan for. Selanjutnya, nilai-nilai array juga ditampilkan tanpa pesan teks tambahan, sehingga menghasilkan tampilan "datar" dari array tersebut.
Penggunaan namespace std digunakan untuk menggunakan objek cin dan cout dari pustaka standar C++.
Kode ini merupakan contoh penerapan konsep array tiga dimensi dan perulangan bersarang dalam pemrograman C++. Meskipun sederhana, namun dapat memberikan pemahaman tentang cara kerja dan penggunaan array tiga dimensi dalam bahasa pemrograman C++.

### 2. [Program Mencari Nilai Maksimal pada Array]

```C++
#include <iostream>
using namespace std;

int main() {
    int maks, a, i = 0, lokasi = 0;

    cout << "Masukkan panjang array: ";
    cin >> a;
    
    int array[a];

    cout << "Masukkan " << a << " angka\n";
    
    for (i = 0; i < a; i++) {
        cout << "Array ke-" << (i + 1) << ": ";
        cin >> array[i];
    }

    maks = array[0];

    for (i = 1; i < a; i++) {
        if (array[i] > maks) {
            maks = array[i];
            lokasi = i;
        }
    }

    cout << "Nilai maksimum adalah " << maks << " berada di Array";
    cout << " ke-" << (lokasi + 1) << endl;

    return 0;
}
```
#### Full code Screenshot:
![Screenshot 2024-03-22 200215](https://github.com/egirizkiyan/tugas-2-praktikum/assets/162097461/5e587040-8856-4ee4-b4f3-91faac43c12b)

#### Output:
![Screenshot 2024-03-22 200336](https://github.com/egirizkiyan/tugas-2-praktikum/assets/162097461/b5b1dd3a-4e8d-4ba9-ae08-9faf161a82b3)

Program di atas adalah program dalam bahasa C++ yang bertujuan untuk menemukan nilai maksimum dari sejumlah angka yang dimasukkan oleh pengguna ke dalam sebuah array.
Prosesnya dimulai dengan meminta pengguna untuk memasukkan panjang array, yaitu berapa banyak angka yang akan dimasukkan. Setelah itu, pengguna diminta untuk memasukkan angka-angka tersebut satu per satu.
Program kemudian mencari nilai maksimum dari angka-angka yang dimasukkan. Ini dilakukan dengan membandingkan setiap angka dalam array dan menyimpan nilai maksimum serta posisinya dalam array.
Setelah menemukan nilai maksimum, program mencetak nilai tersebut beserta posisinya sebagai output.
Dengan menggunakan program ini, pengguna dapat dengan mudah menemukan nilai maksimum dari sejumlah angka yang dimasukkan, tanpa perlu melakukan perhitungan secara manual.

## Unguided 
### 1. [Soal]

```C++
#include <iostream>
#include <vector>
using namespace std;

int main() {
    // Inisialisasi array dengan data yang diberikan
    int arr[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    int n = sizeof(arr) / sizeof(arr[0]); // Menghitung jumlah elemen dalam array

    // Membuat vektor untuk menampung angka genap dan ganjil
    vector<int> even, odd;

    // Memisahkan elemen array menjadi angka genap dan ganjil
    for (int i = 0; i < n; i++) {
        if (arr[i] % 2 == 0)
            even.push_back(arr[i]);
        else
            odd.push_back(arr[i]);
    }

    // Menampilkan array
    cout << "Data array: ";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;

    // Menampilkan nomor genap
    cout << "Nomer genap: ";
    for (int i = 0; i < even.size(); i++) {
        cout << even[i] << " ";
    }
    cout << endl;

    // Menampilkan nomor ganjil
    cout << "Nomer ganjil: ";
    for (int i = 0; i < odd.size(); i++) {
        cout << odd[i] << " ";
    }
    cout << endl;

    return 0;
}

```
#### Output:
![Screenshot 2024-03-22 200853](https://github.com/egirizkiyan/tugas-2-praktikum/assets/162097461/cff60230-07e1-450f-9994-2b8374bbaa90)

#### Full code Screenshot:
![Screenshot 2024-03-22 200715](https://github.com/egirizkiyan/tugas-2-praktikum/assets/162097461/53a221b6-9a50-411e-aad8-7395f9f169ba)

Program di atas adalah contoh program dalam bahasa C++ yang mengilustrasikan bagaimana memisahkan angka-angka dalam sebuah array menjadi dua kategori: angka genap dan angka ganjil. Setelah memisahkan angka-angka tersebut, program menampilkan array awal beserta angka-angka genap dan ganjil secara terpisah sebagai output.
Pertama-tama, program menginisialisasi sebuah array dengan angka-angka yang sudah ditentukan sebelumnya. Kemudian, program menggunakan vektor untuk menampung angka-angka genap dan ganjil setelah dipisahkan dari array awal.
Proses pemisahan dilakukan dengan iterasi melalui setiap elemen dalam array. Pada setiap iterasi, program memeriksa apakah angka tersebut genap atau ganjil dengan menggunakan operasi modulo. Jika angka tersebut genap, maka akan dimasukkan ke dalam vektor angka genap. Sebaliknya, jika angka tersebut ganjil, akan dimasukkan ke dalam vektor angka ganjil.
Setelah proses pemisahan selesai, program menampilkan array awal beserta angka-angka genap dan ganjil secara terpisah sebagai output. Ini dilakukan dengan menggunakan pernyataan cout untuk menampilkan elemen-elemen array serta angka-angka genap dan ganjil yang terdapat dalam vektor.
Terakhir, setelah semua output ditampilkan, program selesai dan mengembalikan nilai 0.

### 2. [Soal]

```C++
#include <iostream>
using namespace std;

int main() {
    int x_size, y_size, z_size;

    // Meminta pengguna untuk memasukkan ukuran array
    cout << "Masukkan jumlah elemen untuk dimensi x: ";
    cin >> x_size;
    cout << "Masukkan jumlah elemen untuk dimensi y: ";
    cin >> y_size;
    cout << "Masukkan jumlah elemen untuk dimensi z: ";
    cin >> z_size;

    // Deklarasi array tiga dimensi
    int arr[x_size][y_size][z_size];

    // Input elemen array
    for (int x = 0; x < x_size; x++) {
        for (int y = 0; y < y_size; y++) {
            for (int z = 0; z < z_size; z++) {
                cout << "Input Array[" << x << "][" << y << "][" << z << "] = ";
                cin >> arr[x][y][z];
            }
        }
        cout << endl;
    }

    // Output elemen array
    cout << "Array yang dimasukkan:" << endl;
    for (int x = 0; x < x_size; x++) {
        for (int y = 0; y < y_size; y++) {
            for (int z = 0; z < z_size; z++) {
                cout << "Data Array[" << x << "][" << y << "][" << z << "] = " << arr[x][y][z] << endl;
            }
        }
    }

    // Tampilan array tanpa label
    cout << "Array tanpa label:" << endl;
    for (int x = 0; x < x_size; x++) {
        for (int y = 0; y < y_size; y++) {
            for (int z = 0; z < z_size; z++) {
                cout << arr[x][y][z] << " ";
            }
            cout << endl;
        }
        cout << endl;
    }

    return 0;
}

```
#### Output:
![Screenshot 2024-03-22 201432](https://github.com/egirizkiyan/tugas-2-praktikum/assets/162097461/03c41831-aa7d-4f45-8936-20d4f7d1f6bd)

#### Full code Screenshot:
![Screenshot 2024-03-22 201235](https://github.com/egirizkiyan/tugas-2-praktikum/assets/162097461/026b4aa6-4baa-4b85-9296-1b13e184bc27)

Array tiga dimensi merupakan struktur data yang memungkinkan penyimpanan data dalam tiga dimensi, sering digunakan dalam pemrograman untuk merepresentasikan data multidimensi seperti gambar, citra medis, atau data spasial. Program di bawah ini adalah contoh sederhana penggunaan array tiga dimensi dalam bahasa pemrograman C++:
Program tersebut meminta pengguna untuk memasukkan ukuran array dalam tiga dimensi (x, y, dan z), kemudian mengisi array tersebut dengan nilai-nilai yang dimasukkan, dan menampilkan elemen-elemen array bersama dengan label koordinatnya. Program juga menampilkan elemen-elemen array tanpa label koordinat.
Dengan memahami kode tersebut, pengguna dapat belajar tentang:
-Penggunaan array multidimensi dalam C++.
-Interaksi dengan pengguna melalui input-output sederhana.
-Penggunaan loop bersarang untuk mengakses dan memanipulasi elemen-elemen array multidimensi.
-Representasi dan penggunaan array tiga dimensi dalam pemrograman.

### 3. [Soal]

```C++
#include <iostream>
using namespace std;

// Fungsi untuk mencari nilai maksimum dalam array
int findMax(int arr[], int size) {
    int max = arr[0];
    for (int i = 1; i < size; ++i) {
        if (arr[i] > max) {
            max = arr[i];
        }
    }
    return max;
}

// Fungsi untuk mencari nilai minimum dalam array
int findMin(int arr[], int size) {
    int min = arr[0];
    for (int i = 1; i < size; ++i) {
        if (arr[i] < min) {
            min = arr[i];
        }
    }
    return min;
}

// Fungsi untuk menghitung nilai rata-rata array
double findAverage(int arr[], int size) {
    double sum = 0;
    for (int i = 0; i < size; ++i) {
        sum += arr[i];
    }
    return sum / size;
}

int main() {
    int size;

    // Meminta pengguna untuk memasukkan ukuran array
    cout << "Masukkan jumlah elemen dalam array: ";
    cin >> size;

    // Membuat array dengan ukuran yang dimasukkan oleh pengguna
    int arr[size];

    // Meminta pengguna untuk memasukkan nilai-nilai array
    cout << "Masukkan nilai-nilai array:" << endl;
    for (int i = 0; i < size; ++i) {
        cout << "Nilai ke-" << i + 1 << ": ";
        cin >> arr[i];
    }

    // Menampilkan menu
    cout << "\nMenu:" << endl;
    cout << "1. Cari Nilai Maksimum" << endl;
    cout << "2. Cari Nilai Minimum" << endl;
    cout << "3. Cari Nilai Rata-rata" << endl;

    // Meminta pengguna untuk memilih operasi
    int choice;
    cout << "Pilih operasi (1/2/3): ";
    cin >> choice;

    // Memproses pilihan pengguna
    switch (choice) {
        case 1:
            cout << "Nilai Maksimum: " << findMax(arr, size) << endl;
            break;
        case 2:
            cout << "Nilai Minimum: " << findMin(arr, size) << endl;
            break;
        case 3:
            cout << "Nilai Rata-rata: " << findAverage(arr, size) << endl;
            break;
        default:
            cout << "Pilihan tidak valid!" << endl;
    }

    return 0;
}
```
#### Output:
![Screenshot 2024-03-22 201703](https://github.com/egirizkiyan/tugas-2-praktikum/assets/162097461/6c77ba38-90bf-4af3-a218-3f9f8f429bf8)

#### Full code Screenshot:
![Screenshot 2024-03-22 202104](https://github.com/egirizkiyan/tugas-2-praktikum/assets/162097461/d9128350-6ca3-4f75-9949-5496d357f190)

Program ini adalah sebuah aplikasi sederhana yang memungkinkan pengguna untuk melakukan pencarian nilai maksimum, minimum, dan nilai rata-rata dari sebuah array. Pengguna diminta untuk memasukkan ukuran array dan nilai-nilai elemen array tersebut. Setelah memasukkan nilai-nilai, pengguna diberikan pilihan untuk melakukan salah satu dari tiga operasi, yaitu mencari nilai maksimum, minimum, atau nilai rata-rata.
Setelah pengguna memilih operasi yang diinginkan, program akan menghitung dan menampilkan hasilnya. Operasi-operasi tersebut diimplementasikan melalui tiga fungsi yang tersedia dalam program:
1.Fungsi untuk Mencari Nilai Maksimum: 
2.Fungsi ini memeriksa setiap elemen dalam array untuk mencari nilai yang paling besar. Setelah menemukan nilai maksimum, 
3.fungsi tersebut mengembalikan nilai tersebut.
4.Fungsi untuk Mencari Nilai Minimum: Sama seperti fungsi untuk mencari nilai maksimum, fungsi ini juga memeriksa setiap elemen dalam array, tetapi kali ini mencari nilai yang paling kecil. Setelah menemukan nilai minimum, fungsi tersebut mengembalikan nilai tersebut.
5.Fungsi untuk Menghitung Nilai Rata-rata: Fungsi ini menghitung rata-rata dari semua nilai dalam array dengan menjumlahkan semua nilai dan membaginya dengan jumlah elemen array. Hasil rata-rata kemudian dikembalikan.

## Kesimpulan
Kesimpulan dari ketiga program di atas adalah sebagai berikut:

Program Memisahkan Angka Genap dan Ganjil dalam Array:

Program ini mengilustrasikan cara memisahkan angka-angka dalam sebuah array menjadi dua kategori: angka genap dan angka ganjil.
Penggunaan vektor untuk menyimpan angka genap dan ganjil memungkinkan fleksibilitas dalam menangani data.
Proses pemisahan dilakukan dengan menggunakan loop untuk iterasi melalui setiap elemen array dan mengecek apakah angka tersebut genap atau ganjil.
Hasil pemisahan kemudian ditampilkan sebagai output dalam tiga kategori: array awal, angka genap, dan angka ganjil.
Program Input dan Output Array Tiga Dimensi:
Program ini menunjukkan cara menggunakan array tiga dimensi dalam C++ untuk menyimpan data dalam struktur tiga dimensi.
Pengguna diminta untuk memasukkan ukuran array dalam tiga dimensi serta nilai-nilai elemen array.
Setelah memasukkan nilai-nilai, program menampilkan elemen-elemen array beserta label koordinatnya.
Program juga menampilkan elemen-elemen array tanpa label koordinat untuk tampilan yang lebih sederhana.
Program Pencarian Nilai Maksimum, Minimum, dan Rata-rata dalam Array:
Program ini memungkinkan pengguna untuk memasukkan ukuran array dan nilai-nilai elemen array.
Setelah memasukkan nilai-nilai, pengguna dapat memilih untuk mencari nilai maksimum, minimum, atau nilai rata-rata dari array.
Program menggunakan fungsi-fungsi terpisah untuk melakukan operasi-operasi tersebut, memisahkan logika pencarian nilai maksimum, minimum, dan rata-rata ke dalam fungsi-fungsi tersendiri.
Penggunaan fungsi-fungsi terpisah mempermudah pengelolaan kode dan membuat program lebih mudah dipahami.
Ketiga program tersebut memberikan contoh penggunaan array dalam C++, dengan fokus pada pemahaman konsep array multidimensi, pemisahan elemen array berdasarkan kriteria tertentu, dan operasi sederhana yang dapat dilakukan pada array seperti pencarian nilai maksimum, minimum, dan rata-rata. Dengan memahami dan mengimplementasikan program-program tersebut, pengguna dapat memperdalam pemahaman mereka tentang penggunaan array dalam pemrograman C++.
.
## Referensi
[1] Novi Anisa. (2021). Penggunaan variabel array dalam pengolahan data. Digilib Unila. [PDF] penggunaan variabel array dalam pengolahan data - Digilib Unila
[2] Khotibul Umam. (2023). ALGORITMA DAN PEMROGRAMAN KOMPUTER DENGAN PYTHON. Tujuan dan Capaian Pembelajaran. Setelah mempelajari materi dalam bab ini, mahasiswa diharapkan mampu menjelaskan dan mengimplementasikan tipe data array. b.
[3] Novi Anisa(2020, September 18). Belajar Python: Mengenal Array pada Bahasa Pemrograman Python. DQLab.