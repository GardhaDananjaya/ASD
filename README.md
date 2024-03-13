SOURCE CODE

  #include <stdio.h>
  #include <stdlib.h>
  #include <string.h>
  
  #define MAX_LENGTH 100
  #define MIN_LENGTH 5
  
  void lessThanRequired (int* lengthOfText){
      // TODO
      printf("The length of your text is less than specified, please update your text");
      
      *lengthOfText = MIN_LENGTH;
  
  }
  
  void equalThanRequired (){
      // TODO
      printf("Thank you, Your text length is correct");
  }
  
  void moreThanRequired (int* lengthOfText){
      // TODO
      printf("Your text is to long, please reduce the text");
      *lengthOfText = MIN_LENGTH;
  }
  
  int checkLenghtRequirement(char* text){
      int length = strlen(text);
      if (length < MIN_LENGTH)
          return 0;
      else if (length == MIN_LENGTH)
          return 1;
      else
          return 2;
  }
  
  int main() {
      int lengthOfText, selectOption;
      
      FILE *fptr = NULL;
      char text[MAX_LENGTH];
  
      fptr = fopen("file.txt", "r");
  
      if(fptr == NULL){
          printf("Error");
          exit(1);
      }
  
      fgets(text, MAX_LENGTH, fptr);
  
      fclose(fptr);
  
      selectOption = checkLenghtRequirement(text);
  
      // TODO
      // Pada fungsi checkLenghtRequirement akan mengembalikan sebuah angka
      // angka tersebut digunakan untuk memilih secara otomatis salah satu fungsi yang harus diisi
      // jika fungsi checkLenghtRequirement() mengembalikan nilai 0, maka
      //      tampilkan - > The length of your text is less than specified, please update your text
      
      //      update nilai lengthOfText ke minimum requirement melalui pointer menggunakan operasi aritmatika
  
      // jika fungsi checkLenghtRequirement() mengembalikan nilai 1, maka
      //      tampilkan - > Thank you, Your text length is correct
      
  
      // jika fungsi checkLenghtRequirement() mengembalikan nilai 2, maka
      //      tampilkan - > Your text is to long, please reduce the text
      //      update nilai lengthOfText ke minimum requirement melalui pointer menggunakan operasi aritmatika
      //
      // Catatan :
      //      - tidak diperkenankan menggunakan if atau switch dalam perpindahan fungsi
      //        sesuai dengan requirement diatas.
      //      - baris kode tidak lebih dari 100 (include comment ini)
      //      - tidak diperkenankan mengganti yang tertera pada starter code dalam alasan apapun
  
      void (*functions[3])(int*) = {lessThanRequired, equalThanRequired, moreThanRequired};
      (*functions[selectOption])(&lengthOfText);
      
      printf("\nThe Lenght is updated to %d", lengthOfText);
  
      return 0;
  }
  

Penjelasan : 

  1. #define MAX_LENGTH 100: Mendefinisikan konstanta MAX_LENGTH yang menyimpan panjang maksimum dari teks yang dapat diterima.
  
  2. #define MIN_LENGTH 5: Mendefinisikan konstanta MIN_LENGTH yang menyimpan panjang minimum dari teks yang diharapkan.
  
  3. void lessThanRequired (int* lengthOfText): sebuah fungsi yang mengambil pointer ke variabel (lengthoftext) untuk pemberitahuan jika karakter dalam file kurang.
  
  4. void equalThanRequired (int* lengthOfText): sebuah fungsi yang mengambil pointer ke variabel (lengthoftext) untuk pemberitahuan jika karakter dalam file cukup.
  
  4. void moreThanRequired (int* lengthOfText): sebuah fungsi yang mengambil pointer ke variabel (lengthoftext) untuk pemberitahuan jika karakter dalam file lebih.
  
  5. int checkLengthRequirement(char* text): Mendefinisikan fungsi checkLengthRequirement yang mengambil string sebagai argumen dan mengembalikan nilai berdasarkan panjang string tersebut. Jika panjangnya kurang dari MIN_LENGTH, kembali 0. Jika sama dengan MIN_LENGTH, kembali 1. Jika lebih besar dari MIN_LENGTH, kembali 2.
  
  int main() {...}: Fungsi utama dari program.
  
  int lengthOfText, selectOption;: Deklarasi dua variabel integer lengthOfText dan selectOption.
  
  FILE *fptr = NULL;: Deklarasi pointer ke objek FILE dan inisialisasi dengan NULL.
  
  char text[MAX_LENGTH];: Deklarasi array karakter text dengan panjang maksimum MAX_LENGTH.
  
  fptr = fopen("file.txt", "r");: Membuka file "file.txt" untuk dibaca.
  
  if(fptr == NULL){...}: Memeriksa apakah file berhasil dibuka atau tidak. Jika tidak, mencetak pesan kesalahan dan keluar dari program.
  
  fgets(text, MAX_LENGTH, fptr);: Membaca isi file ke dalam array text.
  
  fclose(fptr);: Menutup file setelah selesai membacanya.
  
  selectOption = checkLengthRequirement(text);: Memanggil fungsi checkLengthRequirement untuk memeriksa apakah panjang teks sesuai dengan persyaratan.
  
  void (*functionArray[3])(int*) = {lessThanRequired, equalThanRequired, moreThanRequired};: Mendefinisikan array dari pointer fungsi yang masing-masing menunjuk ke fungsi yang sesuai. Ada tiga elemen dalam array ini, masing-masing untuk kasus panjang teks kurang dari, sama dengan, dan lebih dari yang diharapkan.
  
  functionArray[selectOption](&lengthOfText);: Memanggil fungsi yang sesuai dari array functionArray berdasarkan nilai selectOption.
  
  printf("\nThe Length is updated to %d", lengthOfText);: Mencetak panjang teks yang telah diubah, baik itu menjadi nilai minimum atau tidak.

OUTPUT 

  <img width="500" alt="Screenshot 2024-03-14 051423" src="https://github.com/GardhaDananjaya/ASD/assets/147383942/3cd9870d-e63b-45c4-909d-37ee81d3bae1">
  <img width="360" alt="Screenshot 2024-03-14 052245" src="https://github.com/GardhaDananjaya/ASD/assets/147383942/71c26e47-2a7e-4759-b553-fc0943757f29">
