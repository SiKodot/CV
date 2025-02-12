
# Tutorial & Lab Praktikum Proyek 1 - POLBAN: Membuat Website Biografi/CV dengan HTML dan Scraping Menggunakan Python

Selamat datang di tutorial dan lab praktikum Proyek 1 - 2025!  
Di sini, kamu akan mempelajari dasar-dasar HTML dengan sangat detail, mulai dari struktur dokumen, metadata, konten, elemen inline dan blok, hingga form dan tabel. Selain itu, kita juga akan membuat sebuah website sederhana (biografi/CV) dan mempelajari cara melakukan *web scraping* menggunakan Python.



---

## Daftar Isi

1. [Pendahuluan](#pendahuluan)
2. [Bagian 1: Dasar-dasar Struktur HTML](#bagian-1-dasar-dasar-struktur-html)
   - [1.1. Document Metadata](#11-document-metadata)
   - [1.2. Content Sections](#12-content-sections)
   - [1.3. Block Text Content](#13-block-text-content)
   - [1.4. List: Ordered dan Unordered](#14-list-ordered-dan-unordered)
   - [1.5. Preformatted Text](#15-preformatted-text)
   - [1.6. Elemen Inline](#16-elemen-inline)
   - [1.7. Tag Gambar](#17-tag-gambar)
   - [1.8. Tabel](#18-tabel)
   - [1.9. Formulir (Forms)](#19-formulir-forms)
3. [Bagian 2: Membuat Website Biografi/CV](#bagian-2-membuat-website-biograficv)
   - [2.1. Struktur Dasar Website](#21-struktur-dasar-website)
   - [2.2. Menambahkan Konten dan Gaya](#22-menambahkan-konten-dan-gaya)
4. [Bagian 3: Scraping Website Menggunakan Python](#bagian-3-scraping-website-menggunakan-python)
5. [Deploy ke GitHub Pages](#deploy-ke-github-pages)
6. [Kesimpulan](#kesimpulan)

---

## Pendahuluan

Pada tutorial dan lab praktikum ini, kamu akan belajar:
- **Dasar-dasar HTML:** Memahami struktur dokumen HTML mulai dari metadata hingga konten.
- **Membuat Website Sederhana:** Kita akan membuat sebuah website biografi/CV sederhana.
- **Scraping dengan Python:** Belajar cara mengambil data dari website menggunakan library Python seperti `requests` dan `BeautifulSoup`.

---

## Bagian 1: Dasar-dasar Struktur HTML

### 1.1. Document Metadata

Metadata adalah bagian dari dokumen HTML yang memberikan informasi tentang halaman web, seperti judul halaman dan link ke file CSS. Metadata ditempatkan di dalam tag `<head>`.

**Contoh:**
```html
<!DOCTYPE html>
<html lang="id">
  <head>
    <!-- Judul yang akan muncul pada tab browser -->
    <title>Intro to HTML</title>
    
    <!-- Link ke file CSS eksternal -->
    <link rel="stylesheet" href="./style.css" />
    
    <!-- CSS internal (inline) -->
    <style>
      hr {
        margin: 40px;
      }
    </style>
  </head>
```

**Penjelasan:**
- `<!DOCTYPE html>`: Menyatakan jenis dokumen dan versi HTML.
- `<html lang="id">`: Membuka dokumen HTML dan menyetel bahasa menjadi Bahasa Indonesia.
- `<head>`: Tempat menaruh metadata seperti judul dan link ke stylesheet.
- `<title>`: Menentukan judul halaman yang tampil di tab browser.
- `<link rel="stylesheet">`: Menghubungkan halaman dengan file CSS eksternal.
- `<style>`: Menyisipkan aturan CSS secara langsung.

---

### 1.2. Content Sections

Bagian konten yang terlihat di browser ditempatkan di dalam tag `<body>`. HTML5 menyediakan elemen semantik untuk mengorganisir konten.

**Struktur Dasar:**
```html
<body>
  <!-- Header: Biasanya untuk judul, logo, dan navigasi -->
  <header>
    <h1>Heading 1</h1>
    <h2>Heading 2</h2>
    <h3>Heading 3</h3>
    <h4>Heading 4</h4>
    <h5>Heading 5</h5>
    <h6>Heading 6</h6>

    <nav>
      <!-- Menu navigasi akan diletakkan di sini -->
    </nav>
  </header>

  <!-- Main: Konten utama halaman -->
  <main>
    <!-- Article: Konten utama seperti artikel atau biografi -->
    <article>
      <!-- Isi artikel -->
    </article>
    
    <!-- Aside: Konten tambahan, seperti sidebar atau info sampingan -->
    <aside>
      <!-- Isi aside -->
    </aside>
  </main>

  <!-- Footer: Informasi tambahan, seperti kontak atau hak cipta -->
  <footer>
    <!-- Isi footer -->
  </footer>
</body>
</html>
```

**Penjelasan:**
- `<header>`: Berisi elemen judul dan navigasi.
- `<main>`: Tempat konten utama halaman.
- `<article>`: Konten yang berdiri sendiri (misal, artikel, posting blog, atau biografi).
- `<aside>`: Konten tambahan atau sampingan.
- `<footer>`: Informasi penutup seperti hak cipta dan kontak.

---

### 1.3. Block Text Content

Block elements digunakan untuk mengelompokkan teks dan konten dalam blok besar. Contoh yang umum digunakan adalah `<div>` dan `<p>`.

**Contoh Penggunaan `<div>` dan `<p>`:**
```html
<div>
  <p>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Quo et quod odio velit, hic qui autem dolores magni earum ducimus dolorem modi, numquam laborum accusamus adipisci eius excepturi doloremque vero.
  </p>
  <p>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolore voluptatum maiores vitae? Architecto amet provident labore error officia accusantium reiciendis, vero perspiciatis.
  </p>
  <p>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium nobis ex optio, minus in, eum ratione magnam aut distinctio, aliquid libero eaque nihil provident nemo est adipisci repellendus nisi numquam?
  </p>
</div>
```

**Penjelasan:**
- `<div>`: Elemen generik untuk mengelompokkan konten blok.
- `<p>`: Menandai paragraf teks.

---

### 1.4. List: Ordered dan Unordered

HTML memiliki dua jenis list: **Ordered List** (berurutan/nomor) dan **Unordered List** (tidak berurutan/bulet).

**Ordered List (Daftar Berurutan):**
```html
<ol>
  <li>Item list pertama</li>
  <li>Item list kedua</li>
  <li>Item list ketiga</li>
</ol>
```

**Unordered List (Daftar Tidak Berurutan):**
```html
<ul>
  <li>Item list pertama</li>
  <li>Item list kedua</li>
  <li>Item list ketiga</li>
</ul>
```

---

### 1.5. Preformatted Text

Tag `<pre>` digunakan untuk menampilkan teks dengan format aslinya, termasuk spasi dan baris baru.

**Contoh:**
```html
<pre>
  // Ini adalah contoh penggunaan tag pre -- spasi dan tab akan dipertahankan
  
  <ul>
    <li>Unordered</li>
    <li>list</li>
    <li>items</li>
  </ul>
  
  // Untuk menampilkan kode HTML secara literal, lakukan escape:
  &lt;ul&gt;
    &lt;li&gt;Unordered&lt;/li&gt;
    &lt;li&gt;list&lt;/li&gt;
    &lt;li&gt;items&lt;/li&gt;
  &lt;/ul&gt;
</pre>
```

---

### 1.6. Elemen Inline

Elemen inline digunakan untuk memformat teks di dalam satu baris tanpa membuat baris baru.

**Contoh Elemen Inline:**
- **Anchor (`<a>`)**: Membuat hyperlink.
- **Span (`<span>`)**: Container inline generik.
- **Bold (`<b>`)**, **Emphasis (`<em>`)**, **Italic (`<i>`)**: Untuk penekanan teks.
- **Subscript (`<sub>`)** dan **Superscript (`<sup>`)**: Untuk teks bawah atau atas.
- **Code (`<code>`)**: Untuk menampilkan potongan kode.

**Contoh:**
```html
<p>
  Kunjungi <a href="https://www.example.com">Example Website</a> untuk informasi lebih lanjut.
  Berikut teks <span style="color: blue;">berwarna biru</span> dan teks <strong>tebal</strong>.
  Kamu juga dapat menuliskan <em>teks yang ditekankan</em> atau kode seperti <code>console.log('Hello');</code>.
</p>
```

---

### 1.7. Tag Gambar

Tag `<img>` digunakan untuk menyisipkan gambar ke halaman web.  
**Selalu sertakan atribut `alt` untuk aksesibilitas.**

**Contoh:**
```html
<img src="fabric-logo.png" alt="Fabric Logo" />
```

**Penjelasan:**
- `src`: Menunjukkan lokasi atau path gambar.
- `alt`: Menyediakan deskripsi alternatif jika gambar tidak dapat ditampilkan.

---

### 1.8. Tabel

Tabel digunakan untuk menyusun data dalam bentuk baris dan kolom.

**Contoh Tabel:**
```html
<table border="1">
  <thead>
    <tr>
      <th>Header Kolom 1</th>
      <th>Header Kolom 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Isi tabel baris 1, kolom 1</td>
      <td>Isi tabel baris 1, kolom 2</td>
    </tr>
    <tr>
      <td colspan="2">Baris yang menggabungkan dua kolom</td>
    </tr>
  </tbody>
</table>
```

**Penjelasan:**
- `<thead>`: Mengelompokkan bagian header dari tabel.
- `<tbody>`: Mengelompokkan isi utama tabel.
- `colspan`: Menggabungkan dua atau lebih kolom dalam satu sel.

---

### 1.9. Formulir (Forms)

Forms digunakan untuk mengumpulkan input dari pengguna, seperti teks, tanggal, pilihan, dan lain-lain.

**Contoh Formulir:**
```html
<form action="#" method="post">
  <!-- Input Teks -->
  <label for="name">Masukkan nama kamu:</label>
  <input type="text" id="name" name="name" /><br /><br />

  <!-- Dropdown / Select -->
  <label for="options">Pilih opsi:</label>
  <select id="options" name="option">
    <option value="option1">Option 1</option>
    <option value="option2">Option 2</option>
  </select><br /><br />

  <!-- Color Picker -->
  <label for="color">Pilih warna:</label>
  <input type="color" id="color" name="color" /><br /><br />

  <!-- Input Tanggal -->
  <label for="start">Tanggal Mulai:</label>
  <input type="date" id="start" name="start" value="2018-07-22" /><br /><br />

  <!-- Radio Button -->
  <fieldset>
    <legend>Pilih salah satu:</legend>
    <input type="radio" id="r1" name="radio" value="Radio 1" />
    <label for="r1">Radio 1</label>
    <input type="radio" id="r2" name="radio" value="Radio 2" />
    <label for="r2">Radio 2</label>
    <input type="radio" id="r3" name="radio" value="Radio 3" />
    <label for="r3">Radio 3</label>
  </fieldset>
  <br />

  <!-- Tombol Submit -->
  <button type="submit">Submit</button>
</form>
```

**Penjelasan:**
- `<form>`: Elemen pembungkus yang mengelompokkan semua input.
- `<input>`: Berbagai tipe input (teks, warna, tanggal, radio, dll).
- `<select>` dan `<option>`: Membuat menu dropdown.
- `<fieldset>` dan `<legend>`: Mengelompokkan elemen form yang berhubungan (misalnya radio button).

---

## Bagian 2: Membuat Website Biografi/CV

Pada bagian ini, kamu akan membuat website biografi/CV sederhana menggunakan elemen-elemen HTML yang telah kita pelajari.

### 2.1. Struktur Dasar Website

Buat sebuah file HTML (misalnya `index.html`) dengan isi berikut. Salin dan tempel kode di bawah ini, lalu simpan:

```html
<!DOCTYPE html>
<html lang="id">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Biografi Saya</title>
    <link rel="stylesheet" href="./style.css" />
    <style>
      hr {
        margin: 40px;
      }
    </style>
  </head>
  <body>
    <!-- Header: Judul dan Navigasi -->
    <header>
      <h1>Nama Saya</h1>
      <h2>Profesi atau Pekerjaan</h2>
      <nav>
        <ul>
          <li><a href="#tentang">Tentang</a></li>
          <li><a href="#pengalaman">Pengalaman</a></li>
          <li><a href="#kontak">Kontak</a></li>
        </ul>
      </nav>
    </header>

    <!-- Konten Utama -->
    <main>
      <!-- Bagian Tentang (Biografi) -->
      <article id="tentang">
        <h3>Tentang Saya</h3>
        <p>
          Halo, saya adalah seorang [profesi]. Saya memiliki minat dalam pengembangan web, pemrograman, dan desain.
        </p>
        <div>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Quo et quod odio velit, hic yang...
          </p>
        </div>
      </article>

      <!-- Bagian Pengalaman -->
      <article id="pengalaman">
        <h3>Pengalaman</h3>
        <ul>
          <li>Perusahaan A: Posisi X (2018-2020)</li>
          <li>Perusahaan B: Posisi Y (2020-Sekarang)</li>
        </ul>
      </article>

      <!-- Bagian Keterampilan: Tabel Keterampilan -->
      <article id="keterampilan">
        <h3>Keterampilan</h3>
        <table border="1">
          <thead>
            <tr>
              <th>Keterampilan</th>
              <th>Proficiency</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>HTML/CSS</td>
              <td>Advanced</td>
            </tr>
            <tr>
              <td>Python</td>
              <td>Advanced</td>
            </tr>
          </tbody>
        </table>
      </article>
    </main>

    <!-- Aside: Informasi Tambahan -->
    <aside>
      <h4>Fakta Menarik</h4>
      <p>Saya suka coding, mendaki, dan fotografi.</p>
    </aside>

    <!-- Footer: Kontak -->
    <footer id="kontak">
      <h3>Hubungi Saya</h3>
      <form action="#" method="post">
        <label for="name">Masukkan nama kamu:</label>
        <input type="text" id="name" name="name" /><br /><br />

        <label for="options">Pilih opsi:</label>
        <select id="options" name="option">
          <option value="option1">Option 1</option>
          <option value="option2">Option 2</option>
        </select><br /><br />

        <label for="color">Pilih warna:</label>
        <input type="color" id="color" name="color" /><br /><br />

        <label for="start">Tanggal Mulai:</label>
        <input type="date" id="start" name="start" value="2018-07-22" /><br /><br />

        <fieldset>
          <legend>Pilih salah satu:</legend>
          <input type="radio" id="r1" name="radio" value="Radio 1" />
          <label for="r1">Radio 1</label>
          <input type="radio" id="r2" name="radio" value="Radio 2" />
          <label for="r2">Radio 2</label>
          <input type="radio" id="r3" name="radio" value="Radio 3" />
          <label for="r3">Radio 3</label>
        </fieldset>
        <br />

        <button type="submit">Submit</button>
      </form>
    </footer>
  </body>
</html>
```

**Penjelasan:**
- File `index.html` di atas menggabungkan seluruh elemen HTML yang telah kita bahas, seperti metadata, header, main (article dan aside), serta footer.
- Kamu dapat mengganti teks dan konten sesuai dengan identitas dan informasi pribadimu.

### 2.2. Menambahkan Konten dan Gaya

Untuk menambahkan gaya pada tampilan website, buat file CSS (misalnya `style.css`) di folder yang sama. Contoh isinya:

```css
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}

header, footer {
  background-color: #f2f2f2;
  padding: 20px;
}

nav ul {
  list-style: none;
  padding: 0;
}

nav ul li {
  display: inline;
  margin-right: 10px;
}

main, aside {
  padding: 20px;
}
```

**Penjelasan:**
- File CSS ini mengatur tampilan dasar website agar lebih menarik dan mudah dibaca.

---

## Bagian 3: Scraping Website Menggunakan Python

Setelah website sederhana kamu selesai, kita akan belajar cara mengambil data dari website menggunakan Python.

### 3.1. Menyiapkan Lingkungan Python

Pastikan Python sudah terinstall di komputer kamu. Kemudian, install library yang diperlukan dengan perintah:
```bash
pip install requests beautifulsoup4
```

### 3.2. Membuat Skrip Python untuk Scraping

Buat file baru (misalnya `scrape.py`) dan salin kode berikut:

```python
import requests
from bs4 import BeautifulSoup

# URL website yang telah kamu buat (jika dijalankan secara lokal, gunakan localhost, misalnya http://localhost:8000/index.html)
url = 'http://localhost:8000/index.html'

# Mengambil konten halaman menggunakan requests
response = requests.get(url)

if response.status_code == 200:
    # Parsing HTML menggunakan BeautifulSoup
    soup = BeautifulSoup(response.text, 'html.parser')
    
    # Contoh 1: Mengambil heading utama (h1)
    h1 = soup.find('h1')
    print('Heading Utama:', h1.get_text() if h1 else 'Tidak ditemukan')

    # Contoh 2: Mengambil semua heading (h1 hingga h6)
    for level in range(1, 7):
        for heading in soup.find_all(f'h{level}'):
            print(f'H{level}:', heading.get_text())

    # Contoh 3: Mengambil semua paragraf dalam <article id="tentang">
    tentang = soup.find('article', id='tentang')
    if tentang:
        paragraphs = tentang.find_all('p')
        for idx, p in enumerate(paragraphs, 1):
            print(f'Paragraf {idx} dalam Tentang:', p.get_text())

    # Contoh 4: Mengambil semua link dalam navigasi
    nav = soup.find('nav')
    if nav:
        links = nav.find_all('a')
        for link in links:
            print('Link Navigasi:', link.get('href'), '-', link.get_text())

    # Contoh 5: Mengambil input pada formulir di footer
    footer = soup.find('footer')
    if footer:
        inputs = footer.find_all('input')
        for inp in inputs:
            tipe = inp.get('type')
            nama = inp.get('name')
            print('Input Form:', nama, 'Tipe:', tipe)
else:
    print("Gagal mengambil halaman. Status Code:", response.status_code)
```

**Penjelasan:**
- **Requests:** Library untuk mengambil konten halaman web.
- **BeautifulSoup:** Library untuk parsing HTML agar lebih mudah mencari dan mengekstrak elemen.
- Skrip ini memberikan contoh cara mengambil heading, paragraf, link navigasi, dan input dari formulir.

### 3.3. Menjalankan Skrip Python

Jalankan skrip dengan perintah berikut di terminal:
```bash
python scrape.py
```

Lihat output di terminal untuk memastikan data telah diambil dengan benar.

---

## Deploy ke GitHub Pages

Setelah selesai membuat website dan menguji scraping, kamu dapat mempublikasikan website di GitHub Pages. Berikut langkah-langkah singkatnya:

1. **Buat Repository Baru:**  
   Buat repository baru di GitHub, misalnya dengan nama `website-biografi`.

2. **Push Kode:**  
   Push file `index.html`, `style.css`, dan file README.md (file ini) ke repository tersebut.

3. **Aktifkan GitHub Pages:**  
   - Masuk ke *Settings* repository.
   - Gulir ke bagian *GitHub Pages*.
   - Pilih branch (misalnya `main`) dan folder root sebagai source, lalu simpan.
   
4. **Akses Website:**  
   Setelah beberapa menit, website kamu akan tersedia pada URL yang disediakan oleh GitHub Pages.

---

## Kesimpulan

Pada tutorial dan lab praktikum ini, kamu telah:
- Mempelajari **struktur dasar HTML** secara mendetail, mulai dari metadata, konten, hingga elemen teks, list, tabel, dan form.
- Membuat sebuah website **biografi/CV sederhana** menggunakan HTML.
- Mempelajari cara melakukan **web scraping** dengan Python menggunakan `requests` dan `BeautifulSoup`.
- Mempersiapkan website untuk **deploy ke GitHub Pages**.


Selamat belajar dan semoga sukses!
