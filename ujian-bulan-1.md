# UJIAN BULANAN PRAKTIK — HTML & CSS

| | |
|---|---|
| **Jenis ujian** | 100% praktik (membuat website) |
| **Materi** | HTML (Bab 1–14) dan CSS (Bab 1–21) |
| **Hari/Tanggal** | Rabu, 30 September 2026 |
| **Waktu** | 09.00 – 22.30 WIB (13,5 jam, sudah termasuk waktu istirahat) |
| **Hasil akhir** | Website statis 3 halaman (HTML + CSS) dalam satu folder |

---

## 1. Tugas

Buatlah **website statis 3 halaman** dengan tema pilihanmu, menggunakan **HTML dan CSS saja**. Tidak ada soal pilihan ganda dan tidak ada soal essay. Seluruh nilaimu berasal dari website yang kamu kumpulkan.

Website harus menunjukkan bahwa kamu menguasai materi HTML dan CSS yang sudah dipelajari, dan tampilannya harus rapi di **layar HP maupun laptop**.

## 2. Pilih Satu Tema

Pilih **salah satu**. Semua tema memakai spesifikasi yang sama, jadi tidak ada tema yang lebih mudah atau lebih sulit.

| Tema | Contoh isi halaman "Katalog" |
|---|---|
| **A. Kafe / Kedai Makanan** | Daftar menu dan harga, jam buka |
| **B. Wisata / Destinasi Daerah** | Paket wisata, jadwal dan tarif |
| **C. Portofolio Kreator** (desainer, fotografer, dll.) | Daftar layanan dan tarif, karya |
| **D. Komunitas / Event** | Rundown acara, jadwal, tiket |

Nama, produk, dan isi boleh fiktif, tetapi **harus ditulis sendiri dan masuk akal**. Jangan mengisi seluruh halaman dengan *Lorem ipsum*.

## 3. Aturan Ujian

**Boleh:**
- Membuka catatan dan materi bab dari kelas.
- Membuka dokumentasi resmi seperti MDN Web Docs dan W3Schools.
- Memakai gambar, audio, dan video bebas hak cipta (Unsplash, Pexels, Pixabay, dll.) atau milik sendiri.
- Memakai ikon FontAwesome dan Google Fonts lewat CDN/link.
- Bertanya kepada pengajar jika ada kendala teknis (bukan untuk menanyakan jawaban).

**Tidak boleh:**
- Memakai **JavaScript** (`<script>` buatan sendiri). Ujian ini hanya HTML dan CSS. Pengecualian: link CDN FontAwesome.
- Memakai **framework/library CSS** seperti Bootstrap atau Tailwind.
- Menyalin **template website jadi**, atau menyalin kode milik teman.
- Memakai **AI/code generator** untuk menghasilkan kode.
- Bekerja sama atau saling membantu antar peserta.

Pelanggaran akan mengurangi nilai (lihat bagian 9) dan bisa berujung pada pemeriksaan lisan.

## 4. Struktur Folder yang Wajib

Beri nama foldermu `UJIAN_NamaLengkap` (contoh: `UJIAN_BudiSantoso`), lalu susun seperti ini:

```
UJIAN_NamaLengkap/
├── index.html        ← Halaman 1: Beranda
├── katalog.html      ← Halaman 2: Katalog
├── kontak.html       ← Halaman 3: Kontak
├── css/
│   └── style.css     ← SATU file CSS untuk semua halaman
├── img/              ← gambar dan favicon
└── media/            ← audio dan video
```

Website harus bisa dibuka **hanya dengan klik dua kali `index.html`**, tanpa server dan tanpa instalasi apa pun. Gunakan nama file huruf kecil dan tanpa spasi.

---

## 5. Spesifikasi Website

### 5.1 Ketentuan Umum (berlaku di ketiga halaman)

- Kerangka HTML5 lengkap: `<!DOCTYPE html>`, `<html lang="id">`, `<head>`, `<body>`.
- Di dalam `<head>` wajib ada:
  - `charset` UTF-8
  - `<title>` yang **berbeda** di tiap halaman
  - `meta description`
  - `meta viewport`
  - **favicon**
  - link ke `css/style.css`
- Setiap halaman memakai elemen **semantik**: `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`. Di halaman tertentu tambahkan `<article>` dan/atau `<aside>` sesuai fungsinya.
- Menu navigasi dibuat dengan `<nav>` + `<ul>` + `<li>` + `<a>`, dan menghubungkan ketiga halaman memakai **relative path**. Menu halaman yang sedang dibuka harus tampil berbeda (mis. class `active`).
- **Satu `<h1>` per halaman**, hierarki heading berurutan (h1 → h2 → h3), tidak melompat level.
- Semua gambar memiliki atribut `alt` yang bermakna.
- Kode ditulis rapi: indentasi konsisten, tag tertutup dengan benar, nilai atribut diberi tanda kutip.

### 5.2 Halaman 1 — Beranda (`index.html`)

1. **Hero**
   - Berisi `<h1>`, satu paragraf pengantar, dan tombol/link ajakan (CTA) ke halaman Katalog.
   - Memakai **gambar latar** (`background-image`) yang ditumpuk dengan **gradasi** sebagai overlay.
   - Tingginya memakai satuan viewport (`vh`).
   - Teks di hero diberi `text-shadow`.
2. **Tentang**
   - Minimal 2 paragraf.
   - Memakai minimal **4 jenis format teks** yang sesuai makna (mis. `<strong>`, `<em>`, `<mark>`, `<small>`, `<sub>`, `<sup>`, `<del>`).
   - Memakai `<br>` atau `<hr>` secara tepat.
3. **Keunggulan**
   - Minimal **3 kartu**, disusun dengan **Flexbox**.
   - Setiap kartu berisi ikon **FontAwesome**, judul `<h3>`, dan deskripsi.
   - Kartu memiliki padding, border, `border-radius`, dan `box-shadow`.
   - Minimal satu kartu memiliki **badge** (mis. "Baru" atau "Terlaris") yang diletakkan di pojok kartu dengan `position: absolute`.
4. **Galeri**
   - Minimal **6 gambar**, disusun dengan **CSS Grid**.
   - Ada `gap`, dan minimal satu gambar **merentang lebih dari satu kolom atau baris**.
5. **Video**: satu video **YouTube** yang disematkan dengan `<iframe>`.

### 5.3 Halaman 2 — Katalog (`katalog.html`)

Tata letak halaman ini memakai **`grid-template-areas`** dengan minimal area: `intro`, `konten`, dan `sidebar` (`<aside>`).

1. **Tabel** (menu/harga/paket/jadwal/tarif sesuai tema):
   - Minimal 5 baris data, dengan `<thead>`, `<tbody>`, dan `<th>`.
   - Minimal **satu `colspan`** dan **satu `rowspan`**.
   - Baris data berselang-seling warnanya dengan `:nth-child()`.
   - Tabel dibungkus `<div>` yang mencegah halaman melebar di layar kecil (`overflow`).
2. **List**: minimal satu `<ul>` dan satu `<ol>` (mis. di sidebar: tips, syarat, langkah pemesanan).
3. **Gambar**: minimal 3 gambar produk/layanan.
4. **Audio**: satu `<audio>` dengan kontrol.
5. **Video**: satu `<video>` lokal dari folder `media/` dengan kontrol dan `poster` (atau atribut tambahan lain yang relevan).

### 5.4 Halaman 3 — Kontak (`kontak.html`)

1. **Informasi kontak** yang memuat:
   - Link `mailto:` dan link `tel:`.
   - Minimal satu link ke situs luar (mis. media sosial) yang terbuka di **tab baru** (`target="_blank"` beserta `rel="noopener"`).
   - Satu link **anchor internal** (`#id`), mis. "Kembali ke atas".
2. **Formulir** dengan ketentuan:
   - Tag `<form>` memiliki atribut `action` dan `method`. Karena belum ada back-end, `action` boleh diisi `#`.
   - Setiap kolom punya `<label>` yang terhubung lewat `for` dan `id`.
   - Minimal **5 tipe `<input>` berbeda**, mis. `text`, `email`, `tel`, `date`, `number`, `radio`, `checkbox`.
   - Satu `<textarea>`.
   - Satu `<select>` dengan minimal 3 `<option>`.
   - Tombol *submit* dan *reset*.
   - Atribut `required` dan `placeholder` dipakai secukupnya.
3. **Peta**: Google Maps yang disematkan dengan `<iframe>`.

### 5.5 Ketentuan CSS (`css/style.css`)

Semua gaya ditulis di **satu file eksternal**. Inline style dibatasi maksimal 3 tempat. Tunjukkan penguasaan materi dengan memenuhi daftar berikut (sebagian besar akan terpakai sendiri saat kamu membangun halaman di atas):

- **Selektor**: element, class, id, universal (`*`, untuk reset), dan selektor kombinasi (descendant, child `>`, atau grup `,`).
- **Warna**: palet warna yang konsisten. Pakai minimal **3 format warna berbeda** (HEX, RGB/RGBA, HSL/HSLA), dengan kontras yang nyaman dibaca.
- **Ukuran**: `width`, `height`, `max-width`, `min-height`, serta satuan relatif (`%`, `rem`/`em`, `vw`/`vh`).
- **Box model**: `padding`, `margin` (termasuk `margin: 0 auto` untuk memusatkan), `border`, `border-radius`, dan `box-sizing: border-box` secara global.
- **Background**: `background-image` dengan `size`, `position`, dan `repeat` (atau shorthand-nya).
- **Efek**: gradasi (linear atau radial), `box-shadow`, dan `text-shadow`.
- **Tipografi**: `font-family` (dengan fallback), `font-size`, `font-weight`, `line-height`, `text-align`, serta minimal satu dari `letter-spacing`, `text-transform`, atau `text-decoration`.
- **Display & posisi**: `display` sesuai kebutuhan, **navbar menempel di atas** (`position: sticky` atau `fixed`) dengan `z-index` yang benar, dan `overflow` di tempat yang tepat.
- **Layout**: Flexbox (navbar dan kartu, memakai `justify-content`, `align-items`, `flex-wrap`, `gap`) dan CSS Grid (galeri dan `grid-template-areas`).
- **Pseudo-class**:
  - Interaktif: `:hover` pada link, tombol, atau kartu; `:focus` pada input; `:active` pada tombol.
  - Struktural: `:first-child`, `:last-child`, atau `:nth-child()`.
- **Pseudo-element**:
  - Minimal satu `::before` atau `::after` dengan `content` untuk dekorasi.
  - Minimal satu dari `::first-letter`, `::first-line`, `::selection`, atau `::placeholder`.
- **Komentar CSS** untuk memisahkan bagian-bagian file (mis. `/* ===== Navbar ===== */`).

### 5.6 Responsive

- Gunakan strategi **mobile first**: gaya dasar untuk layar kecil, lalu perlebar dengan `@media (min-width: ...)`.
- Minimal **2 breakpoint** (mis. `768px` dan `1024px`) yang benar-benar mengubah tata letak. Contoh: galeri 1 → 2 → 3 kolom, kartu menumpuk → berjajar, layout Katalog 1 kolom → 2 kolom.
- Pada lebar **375px** (ukuran HP) tidak boleh ada scroll horizontal. Gambar, iframe, dan tabel harus menyesuaikan lebar layar.
- Teks tetap terbaca dan tombol/link cukup besar untuk disentuh di HP.

---

## 6. Pengumpulan

1. Pastikan seluruh isi folder sudah lengkap dan semua gambar/media tampil dengan benar.
2. Kompres folder menjadi `UJIAN_NamaLengkap.zip`. Ukuran total maksimal **50 MB**, jadi kompres gambar dan pilih video yang pendek.
3. Kumpulkan **paling lambat pukul 22.30 WIB**.
4. Keterlambatan mengurangi nilai.

## 7. Checklist Mandiri

Centang sebelum mengumpulkan.

**HTML**
- [ ] Ketiga halaman punya boilerplate lengkap, `title` berbeda, meta description, viewport, dan favicon
- [ ] Elemen semantik terpakai; satu `h1` per halaman
- [ ] Menu navigasi tersambung dan halaman aktif ditandai
- [ ] Format teks (≥ 4 jenis), hyperlink (relative, eksternal tab baru, anchor, `mailto`, `tel`)
- [ ] Gambar (semua ber-`alt`), audio, video lokal
- [ ] List `ul` + `ol`; tabel dengan `colspan` + `rowspan`
- [ ] Form lengkap (label, ≥ 5 tipe input, textarea, select, submit/reset)
- [ ] Iframe YouTube dan Google Maps tampil; ikon FontAwesome tampil

**CSS**
- [ ] Satu file `style.css`, ada komentar pemisah bagian
- [ ] Selektor beragam, 3 format warna, `box-sizing: border-box`
- [ ] Background + gradasi + `box-shadow` + `text-shadow`
- [ ] Navbar sticky/fixed dengan `z-index`; badge `position: absolute`
- [ ] Flexbox (navbar dan kartu); Grid (galeri dan `grid-template-areas`)
- [ ] `:hover`, `:focus`, `:nth-child`, `::before/::after`, dan satu pseudo-element lain
- [ ] Minimal 2 `@media` (mobile first)

**Kualitas**
- [ ] Tidak ada scroll horizontal di lebar 375px
- [ ] Tidak ada gambar rusak / error merah di Console
- [ ] Tidak memakai JavaScript buatan sendiri maupun framework CSS
- [ ] Nama folder dan file sesuai ketentuan, ukuran zip ≤ 50 MB

## 8. Penilaian

Nilai maksimal **100**, dengan rincian bobot sebagai berikut.

| Aspek | Bobot |
|---|---|
| A. Struktur & semantik HTML | 12 |
| B. Konten HTML (teks, link, media, list, tabel, form, iframe, ikon) | 20 |
| C. CSS fundamental (selektor, warna, box model, background, efek, tipografi) | 18 |
| D. Layout & posisi (display, position, z-index, overflow, flexbox, grid) | 15 |
| E. Pseudo-class & pseudo-element | 8 |
| F. Responsive design | 10 |
| G. Kualitas teknis (struktur folder, path, kerapian, konten) | 7 |
| H. Desain & kreativitas | 10 |
| **Total** | **100** |

Pelanggaran aturan (pengumpulan terlambat, memakai framework/JS/template, dll.) dapat mengurangi nilai. Pengajar dapat meminta penjelasan lisan singkat tentang kode yang kamu tulis.

**Selamat mengerjakan, dan semoga berhasil!**
