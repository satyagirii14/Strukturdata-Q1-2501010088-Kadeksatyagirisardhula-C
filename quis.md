# 1.Karakteristik Memori dan Akses Data

Jelaskan mengapa operasi akses elemen pada Array dapat dilakukan dalam waktu konstan
O(1), sedangkan pada Singly Linked List membutuhkan waktu linear O(n). Hubungkan
jawaban Anda dengan konsep alamat memori (kontinu vs non-kontinu).
## Jawaban:
Operasi akses elemen pada Array dapat dilakukan dalam waktu O(1) karena Array disimpan dalam memori yang kontinu (berurutan). Dengan mengetahui alamat awal (base address), posisi elemen ke-i dapat langsung dihitung menggunakan rumus base address + (i × ukuran elemen), sehingga tidak perlu menelusuri elemen lain.
Sebaliknya, pada Singly Linked List, elemen disimpan dalam memori yang non-kontinu (tidak berurutan). Setiap node hanya memiliki pointer ke node berikutnya, sehingga untuk mengakses elemen tertentu harus dilakukan penelusuran dari head secara bertahap hingga mencapai node yang diinginkan. Karena proses ini bergantung pada jumlah elemen yang dilalui, maka kompleksitas waktunya adalah O(n).

## 2.Analisis Efisiensi Operasi Manipulasi
Dalam kondisi apa sebuah Linked List lebih diunggulkan dibandingkan Array untuk operasi penyisipan (insertion) dan penghapusan (deletion) data? Berikan alasan teoritisnya.
## Jawaban:
Linked List lebih diunggulkan dibandingkan Array untuk operasi penyisipan (insertion) dan penghapusan (deletion) ketika operasi tersebut sering terjadi, terutama di bagian tengah atau awal struktur data, serta ketika ukuran data bersifat dinamis. Secara teoritis, hal ini disebabkan karena Linked List disimpan dalam memori non-kontinu, sehingga setiap elemen (node) hanya terhubung melalui pointer. Akibatnya, proses penyisipan atau penghapusan cukup dilakukan dengan mengubah pointer tanpa perlu menggeser elemen lain, sehingga dapat dilakukan dalam waktu O(1) jika posisi node sudah diketahui.
Sebaliknya, Array disimpan dalam memori kontinu, sehingga penyisipan atau penghapusan elemen (terutama di tengah) mengharuskan pergeseran elemen-elemen lain untuk menjaga urutan, yang menyebabkan kompleksitas waktu menjadi O(n). Oleh karena itu, Linked List lebih efisien untuk operasi insert dan delete yang sering, sedangkan Array lebih cocok untuk akses data secara langsung (random access).

## 3. Konsep Doubly Linked List
Jelaskan struktur anatomi dari sebuah node pada Doubly Linked List. Apa dampak keberadaan pointer tambahan tersebut terhadap penggunaan memori serta fleksibilitas penelusuran dibandingkan dengan Singly Linked List?
## Jawaban:
Doubly Linked List mengorbankan memori ekstra untuk menyimpan pointer tambahan, tetapi memberikan fleksibilitas lebih besar dalam penelusuran dan manipulasi data. Singly Linked List lebih hemat memori dan sederhana, namun terbatas pada penelusuran satu arah dan operasi tertentu menjadi lebih sulit.
DLL biasanya dipilih untuk aplikasi yang membutuhkan navigasi dua arah, seperti undo-redo, riwayat browser, atau playlist musik.

## 4. Mekanisme Circular Linked List
Apa yang membedakan Circular Linked List dari Linked List biasa secara teoritis? Sebutkan satu contoh skenario penggunaan (use case) di mana struktur melingkar ini lebih efektif digunakan.
## jawaban:
Perbedaan Circular Linked List dengan Linked List Biasa
Secara teoritis, perbedaan utama antara Circular Linked List (CLL) dan Linked List biasa (Singly/Doubly Linked List) terletak pada hubungan node terakhir:
- Linked List biasa
Node terakhir (tail) menunjuk ke null, menandakan akhir dari list.
- Circular Linked List
Node terakhir tidak menunjuk ke null, melainkan kembali ke node pertama (head), sehingga membentuk struktur melingkar.
Akibatnya, dalam CLL:
- Tidak ada node yang benar-benar menjadi akhir, karena traversal bisa berputar terus-menerus.
- Penelusuran bisa dimulai dari node mana saja dan tetap bisa menjangkau seluruh list.
Salah satu skenario penggunaan yang efektif adalah implementasi antrian proses dalam sistem operasi (Round Robin Scheduling).
- Proses-proses ditempatkan dalam Circular Linked List.
- CPU akan mengeksekusi setiap proses secara bergiliran, lalu kembali ke proses pertama setelah mencapai akhir, tanpa perlu reset manual.
- Hal ini memastikan distribusi waktu yang adil dan berulang bagi semua proses.

## 5. Array Dinamis di Python
Python list secara internal diimplementasikan sebagai Dynamic Array. Jelaskan mekanisme yang terjadi ”di balik layar” ketika sebuah Dynamic Array kehabisan kapasitas saat melakukan operasi append.
## jawaban:
Saat append kehabisan kapasitas, Python list tidak sekadar menambah satu slot, melainkan melakukan realokasi memori lebih besar, menyalin elemen lama, lalu menambahkan elemen baru. Strategi ini menjaga keseimbangan antara efisiensi waktu dan penggunaan memori ekstra.

