Tugas 1 Pemograman 
nomor 1
#include <stdio.h>

int main() {
    int pilihan;
    long int angka, sisa, biner = 0, basis = 1;
    long int oktal = 0, basis_oktal = 1;

include merupakann file header yang berisi fungsi dasar yang dibutuhkan untuk membuat program.
stdio.h untuk mengimpor fungsi yang sudah didefinisikan di file header.
int dan long int adalah keywords yang sudah didefinisikan oleh compiler c.
angka, sisa, biner adalah variabel untuk menampung sebuah.

printf("Menu:\n");
    printf("1. Desimal ke Biner\n");
    printf("2. Biner ke Desimal\n");
    printf("3. Desimal ke Oktal\n");
    printf("4. Oktal ke Desimal\n");
    printf("Masukkan pilihan Anda: ");
    scanf("%d", &pilihan);

printf digunakan untuk menampilkan semua jenis output. 
scanf digunakan untuk menampilkan inputan.
penggunaan (%d) dikarenakan dalam bentuk integer

switch(pilihan) {
        case 1:
            printf("Masukkan angka desimal: ");
            scanf("%ld", &angka);
            long int desimal = angka;
            while (desimal > 0) {
                sisa = desimal % 2;
                biner += sisa * basis;
                desimal /= 2;
                basis *= 10;
            }
            printf("Nilai biner: %ld\n", biner);
            break;
        case 2:
            printf("Masukkan angka biner: ");
            scanf("%ld", &angka);
            while (angka > 0) {
                sisa = angka % 10;
                biner += sisa * basis;
                angka /= 10;
                basis *= 2;
            }
            printf("Nilai desimal: %ld\n", biner);
            break;
        case 3:
            printf("Masukkan angka desimal: ");
            scanf("%ld", &angka);
            long int nominal = angka;
            while (nominal > 0) {
                sisa = nominal % 8;
                oktal += sisa * basis_oktal;
                nominal /= 8;
                basis_oktal *= 10;
            }
            printf("Nilai oktal: %ld\n", oktal);
            break;
        case 4:
            printf("Masukkan angka oktal: ");
            scanf("%lo", &angka);
            desimal = 0 , basis_oktal= 1;

            while (angka > 0) {
                sisa = angka % 10;
                oktal += sisa * basis_oktal;
                angka /= 10;
                basis_oktal *= 8;
            }
            printf("Nilai desimal: %lo\n", oktal);
            break;
        default:
            printf("Pilihan tidak valid\n");
    }

    return 0;
}

Penggunaan switch case adalah salah satu cara untuk melakukan percabangan dalam pemrograman. dan switch case akan menampilkan kasus yang sesuai permintaan dari inputan, ketikan pilihan diinputan tidak ada dalam kasus maka program akan memunculkan "pilihan tidak valid". 
break digunakan dalam banyak bahasa pemrograman untuk menghentikan eksekusi dari blok kode tertentu.

case 1:
            printf("Masukkan angka desimal: ");
            scanf("%ld", &angka);
            long int desimal = angka;
            while (desimal > 0) {
                sisa = desimal % 2;
                biner += sisa * basis;
                desimal /= 2;
                basis *= 10;
            }
            printf("Nilai biner: %ld\n", biner);
            break;

apabila inputan yang dimasukkan adalah 1, maka akan termasuk pada halaman case 1, dan akan menginput "masukkan angka desimal", long int desimal = angka;: Variabel desimal diinisialisasi dengan nilai yang dimasukkan oleh pengguna. while (desimal > 0) { ... }: Ini adalah loop while yang akan terus berjalan selama desimal lebih besar dari 0. Di dalam loop, sisa = desimal % 2; digunakan untuk menghitung sisa pembagian desimal dengan 2, yang merupakan bit biner yang akan ditambahkan ke representasi biner.biner += sisa * basis;: Ini adalah langkah untuk mengakumulasikan nilai biner. sisa dikalikan dengan basis dan ditambahkan ke biner. desimal /= 2;: Ini adalah langkah untuk membagi desimal dengan 2, karena kita sedang mengonversi ke biner. basis *= 10;: basis digunakan untuk menggeser digit biner ke kiri dengan mengalikannya dengan 10. printf("Nilai biner: %ld\n", biner);: Setelah loop selesai, program mencetak nilai biner yang dihasilkan. break;: Ini adalah pernyataan break yang menghentikan eksekusi dari switch case setelah case 1 selesai dieksekusi.

case 2:
            printf("Masukkan angka biner: ");
            scanf("%ld", &angka);
            while (angka > 0) {
                sisa = angka % 10;
                biner += sisa * basis;
                angka /= 10;
                basis *= 2;
            }
            printf("Nilai desimal: %ld\n", biner);
            break;

while (angka > 0) { ... }: Ini adalah loop while yang akan berjalan selama angka lebih besar dari 0. Di dalam loop, sisa = angka % 10; digunakan untuk mendapatkan digit terakhir dari angka biner yang dimasukkan oleh pengguna. biner += sisa * basis;: Langkah ini menambahkan nilai biner yang dihasilkan dari digit biner ke nilai desimal yang diakumulasikan dalam variabel biner. angka /= 10;: Ini adalah langkah untuk menghapus digit terakhir dari angka biner yang diakses pada iterasi sebelumnya. basis *= 2;: basis digunakan untuk mengalikan dua setiap iterasi, karena kita sedang mengonversi dari biner ke desimal. printf("Nilai desimal: %ld\n", biner);: Setelah loop selesai, program mencetak nilai desimal yang dihasilkan. break;: Pernyataan break ini menghentikan eksekusi dari switch case setelah case 2 selesai dieksekusi.

case 3:
            printf("Masukkan angka desimal: ");
            scanf("%ld", &angka);
            long int nominal = angka;
            while (nominal > 0) {
                sisa = nominal % 8;
                oktal += sisa * basis_oktal;
                nominal /= 8;
                basis_oktal *= 10;
            }
            printf("Nilai oktal: %ld\n", oktal);
            break;

printf("Masukkan angka desimal: ");: Pernyataan ini mencetak pesan yang meminta pengguna untuk memasukkan angka dalam format desimal. scanf("%ld", &angka);: Program membaca input dari pengguna dan menyimpannya dalam variabel angka. Dikarenakan format desimal menggunakan angka dari 0 hingga 9, maka tipe data yang digunakan adalah long int. while (nominal > 0) { ... }: Ini adalah loop while yang akan berjalan selama nominal lebih besar dari 0. Di dalam loop, sisa = nominal % 8; digunakan untuk mendapatkan sisa pembagian nominal dengan 8, yang akan menjadi digit oktal.oktal += sisa * basis_oktal;: Langkah ini menambahkan nilai oktal yang dihasilkan dari digit oktal ke nilai akumulasi dalam variabel oktal. nominal /= 8;: Ini adalah langkah untuk membagi nominal dengan 8, karena kita sedang mengonversi dari desimal ke oktal. basis_oktal *= 10;: basis_oktal digunakan untuk mengalikan 10 setiap iterasi, karena kita sedang menggeser digit oktal ke kiri. printf("Nilai oktal: %ld\n", oktal);: Setelah loop selesai, program mencetak nilai oktal yang dihasilkan. break;: Pernyataan break ini menghentikan eksekusi dari switch case setelah case 3 selesai dieksekusi.

case 4:
            printf("Masukkan angka oktal: ");
            scanf("%lo", &angka);
            desimal = 0 , basis_oktal= 1;

            while (angka > 0) {
                sisa = angka % 10;
                oktal += sisa * basis_oktal;
                angka /= 10;
                basis_oktal *= 8;
            }
            printf("Nilai desimal: %lo\n", oktal);
            break;

  printf("Masukkan angka oktal: ");: Pernyataan ini mencetak pesan yang meminta pengguna untuk memasukkan angka dalam format oktal.

scanf("%lo", &angka);: Program membaca input dari pengguna dan menyimpannya dalam variabel angka. Format %lo digunakan karena kita mengharapkan input dalam format oktal, sehingga nilai akan disimpan dalam bentuk oktal. desimal = 0, basis_oktal = 1;: Variabel desimal diinisialisasi dengan 0 dan basis_oktal diinisialisasi dengan 1. basis_oktal akan digunakan untuk menghitung nilai desimal yang dihasilkan dari digit oktal.
while (angka > 0) { ... }: Ini adalah loop while yang akan berjalan selama angka lebih besar dari 0. Di dalam loop, sisa = angka % 10; digunakan untuk mendapatkan digit terakhir dari angka oktal yang dimasukkan oleh pengguna. oktal += sisa * basis_oktal;: Langkah ini menambahkan nilai desimal yang dihasilkan dari digit oktal ke nilai akumulasi dalam variabel oktal. angka /= 10;: Ini adalah langkah untuk menghapus digit terakhir dari angka oktal yang diakses pada iterasi sebelumnya. basis_oktal *= 8;: basis_oktal digunakan untuk mengalikan 8 setiap iterasi, karena kita sedang mengonversi dari oktal ke desimal. printf("Nilai desimal: %lo\n", oktal);: Setelah loop selesai, program mencetak nilai desimal yang dihasilkan. break;: Pernyataan break ini menghentikan eksekusi dari switch case setelah case 4 selesai dieksekusi.

default:
            printf("Pilihan tidak valid\n");
    }

    return 0;

default, pernyataan ini akan dieksekusi jika tidak ada case yang cocok dengan nilai yang dimasukkan oleh pengguna. Ini adalah bagian terakhir dari blok switch case dan sering digunakan untuk menangani kasus di luar pilihan.

nomor 2
#include <stdio.h>

int main() {
  char input[10];
  int tahun;

  while (1) {
        // Meminta pengguna untuk memasukkan tahun
        printf("Masukkan tahun (4 digit): ");
        scanf("%s", input );

        // Memeriksa panjang input
        int inputan = 0;
        while (input[inputan] != '\0') {
            inputan++;
        }
        if (inputan != 4) {
            printf("Masukan harus terdiri dari 4 digit.\n");
            continue;
        }

        // Memeriksa apakah masukan berupa bilangan
        int bilangan = 1;
        for (int i = 0; i < 4; i++) {
            if (input[i] < '0' || input [i] > '9') {
                bilangan = 0;
                break;
            }
        }
        if (!bilangan) {
            printf("Masukan harus berupa bilangan.\n");
            continue;
        }

        // Mengonversi masukan ke dalam bentuk integer
        tahun = 0;
        for (int i = 0; i < 4; i++) {
            tahun = tahun * 10 + (input [i] - '0');
        }

        // Memeriksa apakah tahun kabisat atau bukan
        if ((tahun % 4 == 0 && tahun % 100 != 0) || tahun % 400 == 0) {
            printf("%d adalah tahun kabisat.\n", tahun);
        } else {
            printf("%d bukan tahun kabisat.\n", tahun);
        }

        break;
    }

    return 0;
}
Program meminta pengguna untuk memasukkan tahun (4 digit).
Program memeriksa panjang input yang dimasukkan pengguna. Jika input tidak terdiri dari 4 digit, program akan mencetak pesan kesalahan dan meminta pengguna untuk memasukkan kembali.
Program memeriksa apakah input yang dimasukkan pengguna terdiri dari bilangan. Jika input tidak berupa bilangan, program akan mencetak pesan kesalahan dan meminta pengguna untuk memasukkan kembali.
Program mengonversi input yang dimasukkan pengguna ke dalam bentuk integer.
Program memeriksa apakah tahun yang dimasukkan pengguna merupakan tahun kabisat atau bukan dengan mengikuti aturan bahwa tahun kabisat adalah tahun yang habis dibagi 4, kecuali tahun yang habis dibagi 100 tetapi tidak habis dibagi 400.
Program mencetak hasil, apakah tahun tersebut adalah tahun kabisat atau bukan, ke layar.
Program kemudian berakhir.


