# ZidanAliZaqi_Homework_MapReduce

Untuk file yang saya peroleh untuk identifikasi MapReduce ini dari link https://www.gutenberg.org/cache/epub/73525/pg73525.txt 

MapReduce adalah paradigma pemrograman yang digunakan untuk memproses data besar melalui algoritma terdistribusi di banyak komputer dalam kluster. Ini membantu dalam pengolahan data skala besar dengan memecah tugas menjadi lebih kecil, yang kemudian diproses secara paralel. Konsep utama di balik MapReduce melibatkan dua fungsi utama: **Map** dan **Reduce**.

### Map Function
Dalam konteks tugas yang kamu berikan, yaitu mengidentifikasi jumlah kalimat yang mengandung kata "me" termasuk kata-kata seperti "something", "name", "agreement", fungsi Map bertugas untuk menganalisis dan memproses input (misalnya, dokumen atau teks). Untuk setiap dokumen, fungsi Map akan:
- Membagi teks menjadi kalimat.
- Memeriksa setiap kalimat untuk menemukan apakah mengandung kata "me" atau variasi kata yang mengandung "me" seperti "something", "name", atau "agreement".
- Menghasilkan pasangan kunci-nilai, di mana kunci mungkin kata "me" dan nilai adalah jumlah kalimat yang mengandung "me" atau variasinya dalam dokumen tersebut.

### Reduce Function
Setelah semua pasangan kunci-nilai dihasilkan oleh fungsi Map dari semua dokumen yang diproses, fungsi Reduce akan mengambil alih. Fungsi Reduce mengagregasi hasil:
- Mengumpulkan semua nilai yang terkait dengan kunci yang sama (dalam hal ini, "me") dari output fungsi Map.
- Menjumlahkan nilai-nilai ini untuk mendapatkan total jumlah kalimat di semua dokumen yang mengandung kata "me" atau variasinya.

### Keseluruhan Proses
Proses MapReduce berlangsung dalam beberapa tahap:
1. **Input dan Pembagian**: Data besar dibagi menjadi potongan-potongan yang lebih kecil, dan masing-masing potongan diberikan kepada berbagai tugas Map.
2. **Map**: Setiap tugas Map memproses potongan data secara independen dan menghasilkan pasangan kunci-nilai berdasarkan kriteria yang ditetapkan (misalnya keberadaan "me" dan variasinya dalam teks).
3. **Shuffling**: Data yang di-output oleh Map diorganisir oleh sistem MapReduce sehingga semua nilai dari kunci yang sama berada bersama, siap untuk diproses oleh Reduce.
4. **Reduce**: Setiap tugas Reduce mengambil kunci dan daftar nilai yang terkait, menggabungkannya untuk membentuk sebuah nilai akumulatif yang menggambarkan seluruh dataset.
5. **Output**: Hasil akhir disimpan kembali ke sistem penyimpanan, memberikan ringkasan yang diinginkan (misalnya, jumlah total kalimat dengan "me" dan variasinya).

Berikut Screenshot Ouput yang menampilkan kalimat dan jumlah kalimat ![Output SS](Output%20SS.png)

