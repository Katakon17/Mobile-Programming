# Mobile-Programming
2. Karena Flutter menggunakan bahasa dart yang mana adalah bahasa pemrograman yang dibuat dan dioptimalisasi sedemikian rupa oleh google untuk mobile development yang mana menggunakan flutter sebagai framework dan UI tool kitnya 
3. - Di Dart, operator tidak lebih dari method yang didefinisikan dalam class dengan sintaks khusus.
     Jadi, ketika Anda menggunakan operator seperti x == y, seolah-olah Anda sedang memanggil
     x.==(y) metode untuk melakukan perbandingan kesetaraan.
     Seperti yang mungkin telah Anda catat, kita menggunakan method pada x. Untuk semua tipe data, tidak seperti bahasa Java yang memiliki data primitif, x selalu           berupa turunan dari kelas yang memiliki method. Ini berarti bahwa operator dapat diganti sesuai logika yang Anda inginkan.
   - ~/ untuk pembagian bilangan bulat. Di Dart, setiap pembagian sederhana dengan / menghasilkan nilai double. Untuk mendapatkan nilai bilangan bulat, Anda perlu           membuat semacam transformasi (yaitu, typecast) dalam bahasa pemrograman lain; namun Dart sudah mendukung untuk operasi ini.
   - -expression untuk negasi (yang membalikkan suatu nilai).
   - Beberapa operator memiliki perilaku yang berbeda tergantung pada jenis operan di sisi kiri; Misalnya, operator + dapat digunakan untuk menjumlahkan variabel           dari tipe num, tetapi juga dapat digunakan untuk menggabungkan string. Karena method yang dirujuk diimplementasikan secara berbeda pada kelas yang berbeda.
   - Dart juga menyediakan shortcut operator untuk menggabungkan variabel setelah operasi lainnya. Operator aritmatika atau shortcut operator adalah +=, -=, *=, /=,        dan ~/=.
   - ++var atau var++ untuk menambah nilai variabel var sebesar 1
   - --var atau var-- untuk mengurangi nilai variabel var sebesar 1
   - !expression negasi atau kebalikan hasil ekspresi—yaitu, true menjadi false dan false menjadi true.
   - || menerapkan operasi logika OR antara dua ekspresi.
   - && menerapkan operasi logika AND antara dua ekspresi.

4. Null safety :
Bayangkan variabel sebagai ruang kelas, sedangkan variabel null adalah ruang kelas yang kosong tidak ada mahasiswa, ketika kita mendeklarasikan sebagai contoh String string itu seperti melabeli ruang kelasnya "ruang kelas tidak boleh kosong", jadi ruang kelasnya harus terisi oleh mahasiswa (String) di dalamnya, function "isEmpty" itu seperti dosen yang mengecek ruang kelas, ia akan masuk ke ruang kelas dan menghitung berapa banyak mahasiswanya, jika kita mengeksekusi kode berikut
<br>bool isEmpty(String string) => string.length == 0;<br>
dosen akan melihat bahwa ruang kelas kosong sedangkan dosen tidak ekspek ruang kelas akan kosong tapi ia tetap menghitung berapa banyak mahasiswanya tapi, karena tidak ada mahasiswa yang bisa dihitung ia marah dan berteriak "runtime error". Solusinya ada dua yaitu, menerapkan non-nullable sehingga compiler tidak akan menyerahkan ruang kelas kosong(variabel null) ke dosen. Yang kedua ada "String?", disini kita melabeli ruang kelas "kelas boleh kosong boleh tidak" jika kelas kosong maka dosen akan mengatakan "kelas kosong, ok", jika di ruang kelas ada mahasiswa maka ia akan mulai menghitung. contoh kode :
<br>// safechecker!
<br>bool isEmpty(String? string) {
<br>  if (string == null) {
<br>    return true; // ruang kelas sedang kosong!
<br>  }
<br>  return string.length == 0; // sekarang aman untuk mengecek ruang kelas
<br>}
   Late Variable :
bayangkan kamu menulis sebuat catatan yang mana kamu berjanji akan mengisi catatan itu nanti sebelum ada yang membaca catatan itu tapi, kamu belum mengisi catatan itu.
<br> late String myBestFriend; <br>
aturannya sederhana, catatan itu harus di-isi sebelum ada yang membacanya, jika tidak maka akan ada error (LateInitializationError) ini seperti ada temanmu bertanya siapa teman terbaikmu? tapi kamu bingung karena belum menulisnya.
<br>late String myBestFriend;
<br>print(myBestFriend); // ❌ OH NO! You read it before filling it in!
<br>// ERROR: LateInitializationError
<br>
ini adalah contoh kode yang tidak aman
<br>
late String myBestFriend; // Write the note
<br>void decideBestFriend() {
<br>  myBestFriend = "Liam"; // ✅ You filled in the blank first!
<br>}
<br>void main() {
<br>  decideBestFriend();
<br>  print(myBestFriend); // ✅ Now it's safe to read it! It says "Liam"
<br>}<br>
Ini adalah contoh kode yang aman
