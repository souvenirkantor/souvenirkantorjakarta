# Standar & Aturan Pengembangan Website Souvenir Kantor Jakarta

## 1. Aturan Halaman Artikel Blog (Blog Details)
Setiap kali membuat artikel blog baru, WAJIB menggunakan struktur, gaya CSS, komponen UI, metadata SEO, dan JSON-LD schema yang sama persis seperti pada file acuan:
**[`power-bank-custom-logo.html`](file:///c:/PROJECT/souvenirkantorjakarta/power-bank-custom-logo.html)**

### Komponen Wajib Halaman Artikel:
1. **Header Artikel**:
   - Judul `<h1>`
   - `.blog-meta` (Author avatar `assets/img/person/person-f-3.webp`, Nama penulis `Arinda Zakia (rnd)`, Tanggal terbit, Estimasi waktu baca, `.title-line`)
2. **Media & Ringkasan**:
   - Gambar Utama `.blog-img-wrapper` + `.img-caption` (`assets/img/blog/[slug]-1.webp`)
   - `.ringkasan-box` dengan anchor link ke brand/layanan
   - Intro `<p class="lead">`
3. **Navigasi & Isi**:
   - `.toc-wrapper` (Table of Contents interaktif collapsible `#tocList`)
   - Sub-bab `<h2>` dan `<h3>` ber-ID yang sinkron dengan TOC
   - **Box Rekomendasi 1** `.baca-juga-box` (1 box berisi tepat 1 link rekomendasi, ditempatkan setelah sub-bab awal)
   - Gambar Kedua `.blog-img-wrapper` + `.img-caption` (`assets/img/blog/[slug]-2.webp`)
   - **Box Rekomendasi 2** `.baca-juga-box` (1 box berisi tepat 1 link rekomendasi, ditempatkan setelah sub-bab tengah/kemasan/spesifikasi)
   - Tabel Data / Spesifikasi `.table-responsive` dengan header `#1a5f7a`
   - Box Penawaran `.blog-promo-cta` dengan tombol WhatsApp `.btn-wa-cta`
   - Accordion FAQ `.faq-section`
   - Kesimpulan
4. **Author & Interaksi**:
   - Box Profil Penulis `.author-bio`
   - Tombol Share Sosial Media `.share-buttons` (WhatsApp, Facebook, X, LinkedIn)
   - Tag Kategori `.chip`
5. **Sidebar Kanan (`aside#sidebar`)**:
   - Kotak CTA Konsultasi `.sidebar-card` + tombol `.btn-wa`
   - Kotak Artikel Terkait `.sidebar-card` (4 item dengan thumbnail 75x75 `.card-img-side`, judul, dan tanggal)
   - Kotak Produk Populer `.sidebar-card`
6. **SEO & Schema**:
   - Metadata lengkap (title, description, canonical, keywords, geo tags, OG tags, Twitter tags)
   - Schema JSON-LD `@graph` (`Organization`, `LocalBusiness`, `BlogPosting`, `BreadcrumbList`, `FAQPage`, `SpeakableSpecification`)

### Aturan Khusus Box "Baca Juga":
- Memiliki **2 buah box `.baca-juga-box`** yang tersebar di dalam konten artikel.
- Format setiap box: **1 box = 1 link rekomendasi** dengan format:
  ```html
  <div class="baca-juga-box">
    <i class="bi bi-bookmark-star me-1" style="color: #d4a853"></i>
    Baca Juga:
    <a href="[url-artikel-terkait].html">[Judul Artikel Terkait]</a>
  </div>
  ```

### Setiap Artikel Baru Wajib:
- Ditambahkan ke card teratas di [`blog.html`](file:///c:/PROJECT/souvenirkantorjakarta/blog.html).
- Didaftarkan ke [`sitemap.xml`](file:///c:/PROJECT/souvenirkantorjakarta/sitemap.xml) beserta tag `<image:image>`.
- Menggunakan nama asset gambar yang riil dan ada di folder `assets/img/blog/`.
