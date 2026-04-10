##1.Karakteristik Memori dan Akses Data

Jelaskan mengapa operasi akses elemen pada Array dapat dilakukan dalam waktu konstan
O(1), sedangkan pada Singly Linked List membutuhkan waktu linear O(n). Hubungkan
jawaban Anda dengan konsep alamat memori (kontinu vs non-kontinu).
##Jawaban:
Operasi akses elemen pada Array dapat dilakukan dalam waktu O(1) karena Array disimpan dalam memori yang kontinu (berurutan). Dengan mengetahui alamat awal (base address), posisi elemen ke-i dapat langsung dihitung menggunakan rumus base address + (i × ukuran elemen), sehingga tidak perlu menelusuri elemen lain.
Sebaliknya, pada Singly Linked List, elemen disimpan dalam memori yang non-kontinu (tidak berurutan). Setiap node hanya memiliki pointer ke node berikutnya, sehingga untuk mengakses elemen tertentu harus dilakukan penelusuran dari head secara bertahap hingga mencapai node yang diinginkan. Karena proses ini bergantung pada jumlah elemen yang dilalui, maka kompleksitas waktunya adalah O(n).

##2.Analisis Efisiensi Operasi Manipulasi
Dalam kondisi apa sebuah Linked List lebih diunggulkan dibandingkan Array untuk operasi penyisipan (insertion) dan penghapusan (deletion) data? Berikan alasan teoritisnya.
##Jawaban:
Linked List lebih diunggulkan dibandingkan Array untuk operasi penyisipan (insertion) dan penghapusan (deletion) ketika operasi tersebut sering terjadi, terutama di bagian tengah atau awal struktur data, serta ketika ukuran data bersifat dinamis. Secara teoritis, hal ini disebabkan karena Linked List disimpan dalam memori non-kontinu, sehingga setiap elemen (node) hanya terhubung melalui pointer. Akibatnya, proses penyisipan atau penghapusan cukup dilakukan dengan mengubah pointer tanpa perlu menggeser elemen lain, sehingga dapat dilakukan dalam waktu O(1) jika posisi node sudah diketahui.
Sebaliknya, Array disimpan dalam memori kontinu, sehingga penyisipan atau penghapusan elemen (terutama di tengah) mengharuskan pergeseran elemen-elemen lain untuk menjaga urutan, yang menyebabkan kompleksitas waktu menjadi O(n). Oleh karena itu, Linked List lebih efisien untuk operasi insert dan delete yang sering, sedangkan Array lebih cocok untuk akses data secara langsung (random access).

##3. Konsep Doubly Linked List
Jelaskan struktur anatomi dari sebuah node pada Doubly Linked List. Apa dampak keberadaan pointer tambahan tersebut terhadap penggunaan memori serta fleksibilitas penelusuran dibandingkan dengan Singly Linked List?
##Jawaban
