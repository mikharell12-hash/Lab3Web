# Praktikum 3 - CSS Dasar

Laporan praktikum ini membahas penggunaan CSS pada halaman HTML, meliputi **CSS internal, inline, dan external**, serta penggunaan **ID selector** dan **Class selector**.

## Identitas

| Data | Nilai |
|---|---|
| Nama | ALLEIZANDRO LIM HIANTO PRASETYA |
| Kelas | I252A |
| NIM | 312510395 |

## Isi Praktikum

Praktikum dilakukan menggunakan Visual Studio Code dengan alur utama:

1. Membuka Visual Studio Code untuk mengerjakan praktikum.
2. Membuat file HTML untuk menampilkan halaman dasar.
3. Menambahkan CSS internal melalui tag `<style>`.
4. Menambahkan inline CSS langsung pada elemen HTML.
5. Membuat stylesheet external `style_external.css` dan menghubungkannya menggunakan `<link>`.
6. Menambahkan ID selector dan Class selector untuk mengatur bagian tertentu dari halaman.

## Struktur File

```text
Paktikum/
├── LAPORAN PRAKTIKUM 3 ALLEIZANDRO.pdf
├── Praktikum-3-HTMl
└── style_external.css
```

> File `Praktikum-3-HTMl` berisi kode HTML. Agar mudah dijalankan sebagai dokumen HTML, file tersebut dapat diberi ekstensi `.html`, misalnya `Praktikum-3-HTMl.html`.

## Konsep CSS yang Dipraktikkan

### 1. CSS Internal

CSS internal ditempatkan di dalam tag `<style>` pada bagian `<head>` HTML.

Contoh yang digunakan pada praktikum:

```html
<style>
nav {
    background: #20A759;
    color: #fff;
    padding: 10px;
}

nav a {
    color: #fff;
    text-decoration: none;
    padding: 10px 20px;
}

nav .active,
nav a:hover {
    background: #0B6B3A;
}
</style>
```

### 2. Inline CSS

Inline CSS ditulis langsung pada atribut `style` suatu elemen HTML.

```html
<p style="text-align: center; color: #ccd8e4;">
    Kami sedang belajar HTML dan CSS dasar.
</p>
```

Inline style berguna untuk perubahan yang sangat spesifik pada satu elemen, tetapi sebaiknya tidak dipakai berlebihan agar struktur kode tetap mudah dipelihara.

### 3. CSS External

CSS external disimpan di file terpisah, lalu dipanggil dari HTML dengan `<link>`.

```html
<link rel="stylesheet" href="style_external.css" type="text/css">
```

Contoh selector di `style_external.css`:

```css
#intro {
    background: #418fb1;
    border: 1px solid #099249;
    min-height: 100px;
    padding: 10px;
}

#intro h1 {
    text-align: left;
    border: 0;
    color: #fff;
}

.button {
    padding: 15px 20px;
    background: #bebcbd;
    color: #fff;
    display: inline-block;
    margin: 10px;
    text-decoration: none;
}

.btn-primary {
    background: #E42A42;
}
```

## Jawaban Pertanyaan dan Tugas

### 1. Eksperimen perubahan properti dan nilai CSS

Perubahan properti dan nilai CSS dapat dilakukan dengan mengubah deklarasi pada selector. Contoh:

```css
#intro {
    background: #418fb1;
    padding: 10px;
    border-radius: 8px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.15);
}
```

Hasilnya adalah area `#intro` tetap mempunyai latar belakang dan padding, tetapi sekarang memiliki sudut membulat dan bayangan. Eksperimen seperti ini membantu memahami fungsi setiap properti CSS dan dampaknya terhadap tampilan halaman.

### 2. Perbedaan `h1 { ... }` dan `#intro h1 { ... }`

`h1 { ... }` adalah **element selector** dan berlaku untuk seluruh elemen `<h1>` yang cocok.

`#intro h1 { ... }` adalah selector yang menggabungkan **ID selector** dengan descendant selector. Aturan ini hanya berlaku untuk `<h1>` yang berada di dalam elemen dengan `id="intro"`.

Secara specificity:

| Selector | Specificity |
|---|---|
| `h1` | `0-0-0-1` |
| `#intro h1` | `0-1-0-1` |

Karena memiliki ID, `#intro h1` lebih spesifik.

### 3. CSS internal vs external vs inline

Browser menerapkan prinsip **cascade**. Pada deklarasi normal dengan kondisi yang sebanding, inline style memiliki specificity lebih tinggi daripada selector stylesheet internal/external. Untuk internal dan external, specificity dan urutan penulisan ikut menentukan. Pada file praktikum, stylesheet external dipanggil lebih dahulu dan blok internal muncul setelahnya, sehingga aturan internal dapat menang apabila selector, properti, dan specificity-nya sama.

Contoh inline:

```html
<style>
p { color: blue; }
</style>

<p style="color: red;">Teks</p>
```

Hasilnya merah karena `style="..."` berada pada elemen dan mempunyai prioritas specificity yang lebih tinggi untuk deklarasi normal.

### 4. Konflik selector ID dan Class

Untuk HTML:

```html
<p id="paragraf-1" class="text-paragraph">
    Ini adalah paragraf percobaan.
</p>
```

dan CSS:

```css
#paragraf-1 {
    color: red;
}

.text-paragraph {
    color: blue;
}
```

hasil yang ditampilkan adalah **merah**, karena ID selector lebih spesifik daripada Class selector.

| Selector | Specificity |
|---|---|
| `#paragraf-1` | `0-1-0-0` |
| `.text-paragraph` | `0-0-1-0` |

## Cara Menjalankan

1. Buka folder praktikum di Visual Studio Code.
2. Pastikan file HTML dan `style_external.css` berada pada folder yang sama.
3. Buka file HTML menggunakan Live Server atau browser.
4. Ubah nilai CSS, simpan, lalu refresh halaman untuk melihat hasil eksperimen.

## Kesimpulan

Praktikum 3 memperkenalkan cara kerja CSS dalam mengatur tampilan HTML serta cara browser menentukan style ketika terdapat lebih dari satu aturan yang cocok. Pemahaman tentang **cascade**, **specificity**, **ID**, **Class**, **internal CSS**, **external CSS**, dan **inline CSS** menjadi dasar penting untuk membuat halaman web yang terstruktur dan mudah dikembangkan.

## Dokumen Laporan

Versi laporan yang sudah dilengkapi jawaban tersedia pada file:

`LAPORAN PRAKTIKUM 3 ALLEIZANDRO - TERISI.pdf`
