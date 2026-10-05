# Lab3Webb
# Laporan Praktikum 3: CSS Dasar

## Langkah-Langkah Praktikum

### 1. Membuat Dokumen HTML
* **Penjelasan**: Langkah pertama adalah membuat file `lab2_css_dasar.html` dengan struktur dasar HTML5 yang mencakup bagian `<header>`, `<nav>`, dan konten utama yang dilengkapi ID `intro` serta class `.button`.
* **Screenshot**:
  *<img width="1366" height="738" alt="Screenshot from 2026-10-05 17-20-44" src="https://github.com/user-attachments/assets/ced39b28-7030-4861-bb6f-bf28cb497dcc" />
*

### 2. Mendeklarasikan CSS Internal
* **Penjelasan**: Menambahkan aturan styling menggunakan tag `<style>` di dalam bagian `<head>` dokumen. CSS Internal ini mengatur jenis font dasar (`body`), batas bawah header (`header`), serta ukuran dan warna judul (`h1`).
* **Screenshot**:
  *<img width="1366" height="738" alt="Screenshot from 2026-10-05 17-30-36" src="https://github.com/user-attachments/assets/d7a483a3-d029-4e38-b5ed-168c612ed82b" />
*

### 3. Menambahkan Inline CSS
* **Penjelasan**: Menerapkan gaya secara langsung pada tag HTML menggunakan atribut `style` (misalnya atribut `style="text-align: center; color: #ccd8e4;"` pada elemen `<p>`). Gaya ini bersifat spesifik dan hanya memengaruhi elemen tersebut.
* **Screenshot**:
  *<img width="1366" height="738" alt="Screenshot from 2026-10-05 17-32-58" src="https://github.com/user-attachments/assets/393f220f-fe21-4588-aefa-05cd424008b7" />
*

### 4. Membuat CSS Eksternal
* **Penjelasan**: Membuat file terpisah `style_eksternal.css` untuk mengatur tampilan navigasi (`nav`), lalu menghubungkannya ke dokumen HTML menggunakan tag `<link rel="stylesheet" href="style_eksternal.css">` pada bagian `<head>`.
* **Screenshot**:
  *<img width="1366" height="738" alt="Screenshot from 2026-10-05 17-43-54" src="https://github.com/user-attachments/assets/3bcce022-ba3e-4913-9d86-e65e9ef24312" />
*

### 5. Menambahkan CSS Selector
* **Penjelasan**: Mengimplementasikan ID Selector (`#intro`) untuk mengatur area konten khusus dan Class Selector (`.button`) untuk mengubah tampilan link menjadi bentuk tombol pada file `style_eksternal.css`[cite: 26, 27].
* **Screenshot**:
  *<img width="1366" height="738" alt="Screenshot from 2026-10-05 17-46-24" src="https://github.com/user-attachments/assets/2caaa462-ef6e-4585-a10c-775be37b56d9" />
*

---

## Jawaban Pertanyaan

1. **Eksperimen CSS**:
   * *Catatan*: Eksperimen telah dilakukan dengan mengubah properti warna, margin, padding, serta font menggunakan panduan CSS Cheat Sheet.

2. **Perbedaan dekalarasi `h1 {...}` dengan `#intro h1 {...}`**:
   * **`h1 {...}`**: Merupakan *Element Selector* biasa. Aturan styling ini akan diterapkan secara global ke **semua** elemen `<h1>` yang ada di dalam dokumen HTML.
   * **`#intro h1 {...}`**: Merupakan *Descendant Selector* yang dikombinasikan dengan ID. Aturan ini **hanya** berlaku untuk elemen `<h1>` yang berada di dalam elemen yang memiliki `id="intro"`.

3. **Urutan prioritas jika elemen yang sama memiliki Internal CSS, Eksternal CSS, dan Inline CSS**
   * **Penjelasan**: Dalam hirarki CSS (*Cascading Priority*), Inline CSS memiliki nilai spesifisitas paling tinggi dibanding Internal maupun Eksternal CSS. Untuk Internal dan Eksternal CSS, jika nilainya setara, maka yang ditulis paling akhir (paling bawah) di bagian `<head>` yang akan memenangkan aturan.
   * **Contoh**:
     ```html
     <!-- File CSS Eksternal: p { color: blue; } -->
     <head>
       <style>
         p { color: green; } /* Internal CSS */
       </style>
     </head>
     <body>
       <!-- Inline CSS memenangkan tampilan (warna teks menjadi merah) -->
       <p style="color: red;">Teks ini akan berwarna merah.</p>
     </body>
     ```

4. **Prioritas antara ID Selector dan Class Selector pada elemen `<p id="paragraf-1" class="text-paragraf">`**:
   * **Hasil yang ditampilkan**: Deklarasi dari **ID Selector (`#paragraf-1`)** yang akan ditampilkan pada browser.
   * **Penjelasan**: ID Selector memiliki bobot spesifisitas yang lebih tinggi (nilai spesifisitas: 1-0-0) dibandingkan dengan Class Selector (nilai spesifisitas: 0-1-0), meskipun urutan penulisan Class berada di posisi akhir.
   * **Contoh**:
     ```css
     /* Class Selector */
     .text-paragraf {
       color: blue;
     }

     /* ID Selector (Menang / Ditampilkan) */
     #paragraf-1 {
       color: red;
     }
     ```
     *Teks pada `<p id="paragraf-1" class="text-paragraf">` akan berwarna **merah**.*
