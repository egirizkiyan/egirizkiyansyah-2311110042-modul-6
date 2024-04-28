# <h1 align="center">Laporan Praktikum Modul Tipe Data</h1>
<p align="center">Egi Rizkiyansyah</p>

## Dasar Teori
1. Program untuk Menampilkan Output Berdasarkan Input Pengguna:

DLinked List Non Circular 
A. Linked list non circular merupakan linked list dengan node pertama (head) dan  node terakhir (tail) yang tidak saling terhubung. Pointer terakhir (tail) pada Linked  List ini selalu bernilai ‘NULL’ sebagai pertanda data terakhir dalam list-nya. Linked  list non circular dapat digambarkan sebagai berikut
asar Teori: 
B. Linked List Circular 
Linked list circular merupakan linked list yang tidak memiliki akhir karena node  terakhir (tail) tidak bernilai ‘NULL’, tetapi terhubung dengan node pertama (head).  Saat menggunakan linked list circular kita membutuhkan dummy node atau node  pengecoh yang biasanya dinamakan dengan node current supaya program dapat  berhenti menghitung data ketika node current mencapai node pertama (head). 
Linked list circular dapat digunakan untuk menyimpan data yang perlu diakses  secara berulang, seperti daftar putar lagu, daftar pesan dalam antrian, atau  penggunaan memori berulang dalam suatu aplikasi. Linked list circular dapat  digambarkan sebagai berikut. 

## Guided 

### 1. [Program Input Array Tentang linked list non-circular]

```C++
#include <iostream>
using namespace std;

///PROGRAM SINGLE LINKED LIST NON-CIRCULAR
//Deklarasi Struct Node
struct Node{
    //komponen/member
    int data;
    Node *next;
};
    Node *head;
    Node *tail;
//Inisialisasi Node
void init(){
    head = NULL;
    tail = NULL;
}
// Pengecekan
bool isEmpty(){
    if (head == NULL)
    return true;
    else
    return false;
}
//Tambah Depan
void insertDepan(int nilai){
    //Buat Node baru
    Node *baru = new Node;
    baru->data = nilai;
    baru->next = NULL;
    if (isEmpty() == true){
        head = tail = baru;
        tail->next = NULL;
    }
    else{
        baru->next = head;
        head = baru;
    }
}
//Tambah Belakang
void insertBelakang(int nilai){
    //Buat Node baru
    Node *baru = new Node;
    baru->data = nilai;
    baru->next = NULL;
    if (isEmpty() == true){
        head = tail = baru;
        tail->next = NULL;
    }
    else{
    tail->next = baru;
    tail = baru;
    }
}
//Hitung Jumlah List
int hitungList(){
    Node *hitung;
    hitung = head;
    int jumlah = 0;
    while( hitung != NULL ){
        jumlah++;
        hitung = hitung->next;
    }
    return jumlah;
}
//Tambah Tengah
void insertTengah(int data, int posisi){
    if( posisi < 1 || posisi > hitungList() ){
        cout << "Posisi diluar jangkauan" << endl;
    }
    else if( posisi == 1){
        cout << "Posisi bukan posisi tengah" << endl;
    }
    else{
        Node *baru, *bantu;
        baru = new Node();
        baru->data = data;
        // tranversing
            bantu = head;
            int nomor = 1;
        while( nomor < posisi - 1 ){
            bantu = bantu->next;
            nomor++;
        }
        baru->next = bantu->next;
        bantu->next = baru;
    }
}
//Hapus Depan
void hapusDepan() {
    Node *hapus;
    if (isEmpty() == false){
        if (head->next != NULL){
            hapus = head;
            head = head->next;
            delete hapus;
        }
        else{
            head = tail = NULL;
        }
    }
    else{
        cout << "List kosong!" << endl;
    }
}
//Hapus Belakang
void hapusBelakang() {
    Node *hapus;
    Node *bantu;
    if (isEmpty() == false){
        if (head != tail){
            hapus = tail;
            bantu = head;
            while (bantu->next != tail){
                bantu = bantu->next;
            }
            tail = bantu;
            tail->next = NULL;
        delete hapus;
        }
        else{
            head = tail = NULL;
        }
    }
    else{
        cout << "List kosong!" << endl;
    }
}
//Hapus Tengah
void hapusTengah(int posisi){
    Node *hapus, *bantu, *bantu2;
    if( posisi < 1 || posisi > hitungList() ){
        cout << "Posisi di luar jangkauan" << endl;
    }
    else if( posisi == 1){
        cout << "Posisi bukan posisi tengah" << endl;
    }
    else{
        int nomor = 1;
        bantu = head;
        while( nomor <= posisi ){
            if( nomor == posisi-1 ){
                bantu2 = bantu;
            }
            if( nomor == posisi ){
                hapus = bantu;
            }
            bantu = bantu->next;
            nomor++;
        }
        bantu2->next = bantu;
    delete hapus;
    }
}
//Ubah Depan
void ubahDepan(int data){
    if (isEmpty() == false){
        head->data = data;
    }
    else{
        cout << "List masih kosong!" << endl;
    }
}
//Ubah Tengah
void ubahTengah(int data, int posisi){
    Node *bantu;
    if (isEmpty() == false){
        if( posisi < 1 || posisi > hitungList() ){
            cout << "Posisi di luar jangkauan" << endl;
        }
        else if( posisi == 1){
            cout << "Posisi bukan posisi tengah" << endl;
        }
        else{
            bantu = head;
            int nomor = 1;
            while (nomor < posisi){
                bantu = bantu->next;nomor++;
            }
            bantu->data = data;
        }
    }
    else{
        cout << "List masih kosong!" << endl;
    }
}
//Ubah Belakang
void ubahBelakang(int data){
    if (isEmpty() == false){
        tail->data = data;
    }
    else{
        cout << "List masih kosong!" << endl;
    }
}
//Hapus List
void clearList(){
    Node *bantu, *hapus;
    bantu = head;
    while (bantu != NULL){
        hapus = bantu;
        bantu = bantu->next;
        delete hapus;
    }
    head = tail = NULL;
    cout << "List berhasil terhapus!" << endl;
}
//Tampilkan List
void tampil(){
    Node *bantu;
    bantu = head;
    if (isEmpty() == false){
        while (bantu != NULL){
            cout << bantu->data << ends;
            bantu = bantu->next;
        }
        cout << endl;
    }
    else{
        cout << "List masih kosong!" << endl;
    }
}
int main(){
    init();
    insertDepan(3);tampil();
    insertBelakang(5);
    tampil();
    insertDepan(2);
    tampil();
    insertDepan(1);
    tampil();
    hapusDepan();
    tampil();
    hapusBelakang();
    tampil();
    insertTengah(7,2);
    tampil();
    hapusTengah(2);
    tampil();
    ubahDepan(1);
    tampil();
    ubahBelakang(8);
    tampil();
    ubahTengah(11, 2);
    tampil();
    return 0;
}
```
#### Full code Screenshot:
![Screenshot 2024-04-28 230549](https://github.com/egirizkiyan/egi-anak-baik/assets/162097461/6b3b8cc3-0b89-4e29-b9c8-396eea3066d1)

#### Output:
![Screenshot 2024-04-28 230720](https://github.com/egirizkiyan/egi-anak-baik/assets/162097461/f3b297c6-1638-49c9-8e8f-a19900a88a8b)

Kesimpulan dari kode tersebut adalah:

1. Program merupakan implementasi dari sebuah single linked list non-circular.
2. Terdapat struct Node yang memiliki dua member: data untuk menyimpan nilai dan next untuk menunjukkan ke node selanjutnya.
3. Ada fungsi-fungsi untuk melakukan inisialisasi, pengecekan apakah list kosong, penambahan elemen di depan, di belakang, di tengah, penghitungan jumlah elemen, penghapusan elemen di depan, di belakang, di tengah, serta untuk mengubah nilai elemen di depan, di belakang, di tengah, dan untuk membersihkan seluruh list.
4. Fungsi tampil() digunakan untuk menampilkan semua elemen dalam list.
5. Pada main(), terdapat contoh penggunaan dari fungsi-fungsi tersebut untuk menambah, menghapus, mengubah, dan menampilkan elemen-elemen dalam list.

### 2. [Program Mencari Single linked list circular]

```C++
#include <iostream>
using namespace std;

/// PROGRAM SINGLE LINKED LIST CIRCULAR

// Deklarasi Struct Node
struct Node {
    string data;
    Node *next;
};

Node *head, *tail, *baru, *bantu, *hapus;

void init() {
    head = NULL;
    tail = head;
}

// Pengecekan
int isEmpty() {
    if(head == NULL)
       return 1; // true
    else
       return 0; // false     
}

// Buat Node Baru
void buatNode(string data) {
    baru = new Node;
    baru->data = data;
    baru->next = NULL;
}

// Hitung List
int hitungList() {
    bantu = head;
    int jumlah = 0;

    while (bantu != NULL) {
        jumlah++;
        bantu = bantu->next;
    }

    return jumlah;
}

// Tambah Depan
void insertDepan(string data) {
    // Buat Node baru
    buatNode(data);

    if (isEmpty() == 1) {
        head = baru;
        tail = head;
        baru->next = head;
    } else {
        while (tail->next != head) {
            tail = tail->next;
        }

        baru->next = head;
        head = baru;
        tail->next = head;
    }
}

// Tambah Belakang
void insertBelakang(string data) {
    // Buat Node Baru
    buatNode(data);

    if (isEmpty() == 1) {
        head = baru;
        tail = head;
        baru->next = head;
    } else {
        while (tail->next != head) {
            tail = tail->next;
        }

        tail->next = baru;
        baru->next = head;
    }
}

// Tambah Tengah
void insertTengah(string data, int posisi) {
    if (isEmpty() == 1) {
        head = baru;
        tail = head;
        baru->next = head;
    } else {
        baru->data = data;

        // transversing
        int nomor = 1;
        bantu = head;

        while (nomor < posisi -1) {
            bantu = bantu->next;
            nomor++;
        }

        bantu->next = bantu->next;
        bantu->next = baru;
    }
}

// Hapus Depan
void HapusDepan() {
    if (isEmpty() == 0) {
        hapus = head;
        tail = head;
        
        if (hapus->next == head) {
            head = NULL;
            tail = NULL;
            delete hapus;
        } else {
            while (tail->next != hapus) {
                tail = tail->next;
            }

            head = head->next;
            tail->next = head;
            hapus->next = NULL;
            delete hapus;
        }
    } else {
        cout << "List masih kosong!" << endl;
    }
}

// Hapus Belakang
void hapusBelakang() {
    if (isEmpty() == 0) {
        hapus = head;
        tail = head;

        if (hapus->next == head) {
            head = NULL;
            tail = NULL;
            delete hapus;
        } else {
            while (hapus->next != head) {
                hapus = hapus->next;
            }

            while (tail->next != hapus) {
                tail = tail->next;
            }
            
            tail->next = head;
            hapus->next = NULL;
            delete hapus;
        }
    } else {
        cout << "List masih kosong!" << endl;
    }
}

// Hapus Tengah
void hapusTengah(int posisi) {
    if (isEmpty() == 0) {
        // transversing
        int nomor = 1;
        bantu = head;
        
        while (nomor < posisi - 1) {
            bantu = bantu->next;
            nomor++;
        }

        hapus = bantu->next;
        bantu->next = hapus->next;
        delete hapus;
    } else {
        cout << "List masih kosong!" << endl;
    }
}

// Hapus List
void clearList() {
    if (head != NULL) {
        hapus = head->next;

        while (hapus != head) {
            bantu = hapus->next;
            delete hapus;
            hapus = bantu;
        }
        delete head;
        head = NULL;
    }
    cout << "List berhasil terhapus!" << endl;
}

// Tampilan List
void tampil() {
    if (isEmpty() == 0) {
        tail = head;

        do {
            cout << tail->data << ends;
            tail = tail->next;
        } while (tail != head);

        cout << endl;
    } else {
        cout << "List masik kosong!" << endl;
    }
}

int main() {
    init();
    insertDepan("Ayam");
    tampil();
    insertDepan("Bebek");
    tampil();
    insertBelakang("Cicak");
    tampil();
    insertBelakang("Domba");
    tampil();
    hapusBelakang();
    tampil();
    HapusDepan();
    tampil();
    insertTengah("Sapi", 2);
    tampil();
    hapusTengah(2);
    tampil();
    return 0;
}
```
#### Full code Screenshot:
![Screenshot 2024-04-28 231358](https://github.com/egirizkiyan/egi-anak-baik/assets/162097461/dbeb3f85-56d7-496d-8a08-a3848a0f0082)

#### Output:
![Screenshot 2024-04-28 231647](https://github.com/egirizkiyan/egi-anak-baik/assets/162097461/6ac5b02c-87fb-4d4f-8dd2-069b7751381c)

Kesimpulan dari kode tersebut adalah:

1. Program merupakan implementasi dari single linked list circular.
2. Terdapat struct Node yang memiliki dua member: data untuk menyimpan nilai dan next untuk menunjukkan ke node selanjutnya.
3. Variabel global head dan tail digunakan untuk menandai awal dan akhir dari linked list, dengan tail menunjuk kembali ke head untuk membentuk sirkularitas.
4. Fungsi-fungsi yang tersedia meliputi inisialisasi, pengecekan apakah list kosong, pembuatan node baru, penghitungan jumlah elemen dalam list, penambahan elemen di depan, di belakang, di tengah, penghapusan elemen di depan, di belakang, di tengah, penghapusan seluruh list, dan penampilan elemen-elemen dalam list.
5. Pada main(), terdapat contoh penggunaan dari fungsi-fungsi tersebut untuk menambah, menghapus, dan menampilkan elemen-elemen dalam list.

## Unguided 
### 1. [Soal]

```C++

#include <iostream> 
#include <string> 
using namespace std;

struct Node {
    string nama;
    string nim;
    Node* next;
};

Node* head = NULL;
Node* tail = NULL;
void init() {
    head = NULL;
    tail = NULL;
}
bool isEmpty() {
    return head == NULL;
}
void insertDepan(string nama, string nim) {
    Node* baru = new Node;
    baru->nama = nama;
    baru->nim = nim;
    baru->next = NULL;

    if (isEmpty()) {
        head = tail = baru;
    } else {
        baru->next = head;
        head = baru;
    }
}

void insertBelakang(string nama, string nim) {
    Node* baru = new Node;
    baru->nama = nama;
    baru->nim = nim;
    baru->next = NULL;

    if (isEmpty()) {
        head = tail = baru;
    } else {
        tail->next = baru;
        tail = baru;
    }
}

void insertTengah(string nama, string nim, int posisi) {
    if (isEmpty()) {
        cout << "List masih kosong!" << endl;
    } else {
        Node* baru = new Node;
        baru->nama = nama;
        baru->nim = nim;
        baru->next = NULL;

        Node* bantu = head;
        int nomor = 1;

        while (bantu != NULL && nomor < posisi - 1) {
            bantu = bantu->next;
            nomor++;
        }

        if (bantu == NULL) {
            cout << "Posisi diluar jangkauan" << endl;
        } else {
            baru->next = bantu->next;
            bantu->next = baru;
        }
    }
}

void ubahData(string& namaBaru, string& nimBaru, int posisi) {
    Node* bantu = head;
    int nomor = 1;

    while (bantu != NULL && nomor < posisi) {
        bantu = bantu->next;
        nomor++;
    }

    if (bantu == NULL) {
        cout << "Posisi diluar jangkauan" << endl;
    } else {
        cout << "Masukkan nama : ";
        cin >> namaBaru;
        cout << "Masukkan NIM : ";
        cin >> nimBaru;
        bantu->nama = namaBaru;
        bantu->nim = nimBaru;
    }
}

void hapusNode(int posisi) {
    if (isEmpty()) {
        cout << "List masih kosong!" << endl;
        return;
    }

    Node* hapus;
    if (posisi == 1) {
        hapus = head;
        head = head->next;
    } else {
        Node* bantu = head;
        int nomor = 1;

        while (bantu != NULL && nomor < posisi - 1) {
            bantu = bantu->next;
            nomor++;
        }

        if (bantu == NULL || bantu->next == NULL) {
            cout << "Posisi diluar jangkauan" << endl;
            return;
        }

        hapus = bantu->next;
        bantu->next = hapus->next;
        if (hapus == tail) {
            tail = bantu;
        }
    }

    cout << "Data " << hapus->nama << " berhasil dihapus" << endl;
    delete hapus;
}

void hapusList() {
    Node* bantu = head;
    Node* hapus;

    while (bantu != NULL) {
        hapus = bantu;
        bantu = bantu->next;
        delete hapus;
    }

    head = tail = NULL;
    cout << "List berhasil terhapus!" << endl;
}

int hitungList() {
    Node* hitung = head;
    int jumlah = 0;

    while (hitung != NULL) {
        jumlah++;
        hitung = hitung->next;
    }

    return jumlah;
}

void tampil() {
    Node* bantu = head;
    if (isEmpty()) {
        cout << "List masih kosong!" << endl;
    } else {
        cout << "DATA MAHASISWA" << endl;
        cout << "NAMA\tNIM" << endl;
        while (bantu != NULL) {
            cout << bantu->nama << "\t" << bantu->nim << endl;
            bantu = bantu->next;
        }
    }
}

void menu() {
    cout << "PROGRAM SINGLE LINKED LIST NON-CIRCULAR" << endl;
    cout << "1. Tambah Depan" << endl;
    cout << "2. Tambah Belakang" << endl;
    cout << "3. Tambah Tengah" << endl;
    cout << "4. Ubah Depan" << endl;
    cout << "5. Ubah Belakang" << endl;
    cout << "6. Ubah Tengah" << endl;
    cout << "7. Hapus Depan" << endl;
    cout << "8. Hapus Belakang" << endl;
    cout << "9. Hapus Tengah" << endl;
    cout << "10. Hapus List" << endl;
    cout << "11. Tampilkan" << endl;
    cout << "0. Keluar" << endl;
    cout << "Pilih Operasi : ";
}

int main() {
    init();
    int pilihan;
    string nama, nim;
    int posisi;

    do {
        menu();
        cin >> pilihan;

        switch (pilihan) {
            case 1:
                cout << "Masukkan Nama : ";
                cin >> nama;
                cout << "Masukkan NIM : ";
                cin >> nim;
                insertDepan(nama, nim);
                cout << "Data telah ditambahkan" << endl;
                break;
            case 2:
                cout << "Masukkan Nama : ";
                cin >> nama;
                cout << "Masukkan NIM : ";
                cin >> nim;
                insertBelakang(nama, nim);
                cout << "Data telah ditambahkan" << endl;
                break;
            case 3:
                cout << "Masukkan Nama : ";
                cin >> nama;
                cout << "Masukkan NIM : ";
                cin >> nim;
                cout << "Masukkan Posisi : ";
                cin >> posisi;
                insertTengah(nama, nim, posisi);
                cout << "Data telah ditambahkan" << endl;
                break;
            case 4:
                ubahData(nama, nim, 1);
                cout << "Data telah diubah" << endl;
                break;
            case 5:
                ubahData(nama, nim, hitungList());
                cout << "Data telah diubah" << endl;
                break;
            case 6:
                cout << "Masukkan posisi : ";
                cin >> posisi;
                ubahData(nama, nim, posisi);
                cout << "Data telah diubah" << endl;
                break;
            case 7:
                hapusNode(1);
                break;
            case 8:
                hapusNode(hitungList());
                break;
            case 9:
                cout << "Masukkan posisi : ";
                cin >> posisi;
                hapusNode(posisi);
                break;
            case 10:
                hapusList();
                break;
            case 11:
                tampil();
                break;
            case 0:
                cout << "Program selesai." << endl;
                break;
            default:
                cout << "Pilihan tidak valid!" << endl;
        }
    } while (pilihan != 0);

    return 0;
}
```
#### Output:
![Screenshot 2024-04-28 232025](https://github.com/egirizkiyan/egi-anak-baik/assets/162097461/16977ce2-f604-4eed-b508-5fba38a3b09a)

#### Full code Screenshot:
![Screenshot 2024-04-28 232025](https://github.com/egirizkiyan/egi-anak-baik/assets/162097461/16977ce2-f604-4eed-b508-5fba38a3b09a)


Kode tersebut merupakan implementasi dari single linked list non-circular untuk menyimpan data mahasiswa. Berikut adalah kesimpulan dari kode tersebut:

1. Terdapat struct Node yang memiliki dua string nama dan nim, serta pointer next untuk menunjukkan ke node selanjutnya.
2. Variabel global head dan tail digunakan untuk menandai awal dan akhir dari linked list.
3. Fungsi-fungsi yang tersedia meliputi inisialisasi, pengecekan apakah list kosong, penambahan data di depan, di belakang, di tengah, pengubahan data di depan, di belakang, di tengah, penghapusan data di depan, di belakang, di tengah, penghapusan seluruh list, penghitungan jumlah elemen dalam list, dan penampilan data dalam list.
4. Terdapat fungsi menu() yang menampilkan pilihan operasi yang dapat dilakukan pada linked list.
5. Di dalam main(), terdapat loop do-while yang meminta input pilihan operasi dari pengguna dan menjalankan fungsi yang sesuai dengan pilihan tersebut.
6. Program akan berhenti jika pengguna memilih pilihan 0 untuk keluar.
7. Seluruh operasi yang dilakukan pada linked list akan memberikan feedback kepada pengguna mengenai berhasil atau tidaknya operasi tersebut dilakukan.

## Kesimpulan
Dari kode yang disediakan, kita memiliki implementasi dari single linked list non-circular dalam bahasa C++. Berikut adalah kesimpulan dari kode tersebut:

1. Struktur Data dan Variabel Global: Kode dimulai dengan deklarasi struct Node yang memiliki dua variabel string nama dan nim, serta pointer next untuk menunjukkan ke node selanjutnya. Variabel global head dan tail digunakan untuk menandai awal dan akhir dari linked list.
2. Fungsi-Fungsi Dasar:
   - init(): Menginisialisasi head dan tail menjadi NULL.
   - isEmpty(): Memeriksa apakah linked list kosong.
   - insertDepan(), insertBelakang(), insertTengah(): Menambahkan node baru ke depan, belakang, atau di tengah - - - linked list sesuai dengan posisi yang ditentukan.
   - ubahData(): Mengubah data (nama dan nim) pada node tertentu.
   - hapusNode(): Menghapus node pada posisi tertentu.
   - hapusList(): Menghapus seluruh isi linked list.
   - hitungList(): Menghitung jumlah node dalam linked list.
   - tampil(): Menampilkan seluruh data mahasiswa dalam linked list.
3. Fungsi menu() dan main(): menu() digunakan untuk menampilkan pilihan operasi kepada pengguna, sedangkan main() merupakan fungsi utama yang meminta input dari pengguna dan menjalankan operasi yang sesuai.
4. Loop do-while: Program berjalan dalam loop do-while, dimana pengguna diminta untuk memilih operasi yang ingin dilakukan pada linked list. Program akan terus berjalan hingga pengguna memilih untuk keluar (pilihan 0).
5. Feedback Pengguna: Setiap operasi yang dilakukan pada linked list memberikan feedback kepada pengguna, baik itu berhasil atau gagal. Misalnya, ketika sebuah node berhasil ditambahkan, diubah, atau dihapus, pesan akan ditampilkan memberitahu pengguna bahwa operasi tersebut berhasil dilakukan.
6. Penanganan Kasus Khusus: Kode juga menangani kasus khusus, seperti ketika linked list masih kosong, atau ketika posisi yang diminta untuk operasi tidak valid.
Dengan demikian, kode tersebut menyediakan penggunaan lengkap dari linked list untuk mengelola data mahasiswa, dengan dukungan operasi dasar seperti penambahan, penghapusan, pengubahan, dan penampilan data.
## Referensi
[1] Novi Anisa. (2021). Penggunaan variabel array dalam pengolahan data. Digilib Unila. [PDF] penggunaan variabel array dalam pengolahan data - Digilib Unila
[2] Khotibul Umam. (2023). ALGORITMA DAN PEMROGRAMAN KOMPUTER DENGAN PYTHON. Tujuan dan Capaian Pembelajaran. Setelah mempelajari materi dalam bab ini, mahasiswa diharapkan mampu menjelaskan dan mengimplementasikan tipe data array. b.
[3] Novi Anisa(2020, September 18). Belajar Python: Mengenal Array pada Bahasa Pemrograman Python. DQLab.