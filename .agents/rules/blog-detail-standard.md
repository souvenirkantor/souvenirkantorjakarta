# Panduan & Standar Struktur Halaman Blog (Blog Detail Standard)

Semua halaman artikel blog baru di website **Souvenir Kantor Jakarta** WAJIB mengikuti standar struktur, komponen UI, styling, dan SEO schema seperti pada file acuan [`power-bank-custom-logo.html`](file:///c:/PROJECT/souvenirkantorjakarta/power-bank-custom-logo.html).

---

## 1. Aturan Wajib Metadata & SEO (Anti-Halusinasi & Konsistensi)

1. **Title**: Format `[Topik Artikel] [Kata Kunci Turunan] | Souvenir Kantor` atau format benefit/ROI yang memikat.
2. **Meta Description**: 130-160 karakter dengan kalimat persuasif dan CTA ("kunjungi website!", "simak di sini!").
3. **Canonical**: `https://souvenirkantorjakarta.web.id/[slug-tanpa-html]`
4. **Geo Tags**: Region `ID-JI` / `ID-JK`, Placename Surabaya / Jakarta sesuai target geo.
5. **Open Graph & Twitter Cards**: Tipe `article`, mencantumkan judul, deskripsi, image 1200x630, `article:published_time`, `article:modified_time`, `article:author`.
6. **JSON-LD Schema (`@graph`)**:
   - `Organization`
   - `LocalBusiness`
   - `BlogPosting` (lengkap dengan author, publisher, datePublished, dateModified, image, articleSection)
   - `BreadcrumbList` (Beranda > Blog > Judul Artikel)
   - `FAQPage` (pertanyaan & jawaban harus 100% sinkron dengan accordion FAQ di konten)
   - `SpeakableSpecification`

---

## 2. Struktur Anatomi Halaman Artikel

Setiap file artikel blog HTML memiliki struktur wajib berikut:

```html
<!doctype html>
<html lang="id-ID">
<head>
  <!-- 1. Meta Tags SEO, GEO, & Open Graph -->
  <!-- 2. Favicons -->
  <!-- 3. CSS Vendors (Bootstrap 5.3, Bootstrap Icons 1.11, AOS) -->
  <!-- 4. Custom Page CSS (CSS variables, blog layout, toc, sidebar, share) -->
  <!-- 5. JSON-LD Schemas (@graph) -->
</head>
<body class="blog-details-page">
  <!-- Header & Navbar -->
  <!-- Breadcrumb -->
  <main class="main">
    <div class="container py-5">
      <div class="row g-5">
        <!-- Kolom Konten Utama (col-lg-8) -->
        <div class="col-lg-8">
          <article>
            <!-- 1. Blog Header (H1, Blog Meta: Author Avatar, Nama, Tanggal, Estimasi Waktu Baca, Title Line) -->
            <!-- 2. Gambar Utama (blog-img-wrapper, img-caption) -->
            <!-- 3. Ringkasan Box (.ringkasan-box dengan link anchor) -->
            <!-- 4. Lead Paragraph (.lead) & Intro -->
            <!-- 5. Table of Contents (.toc-wrapper collapsible #tocList) -->
            <!-- 6. Konten Sub-bab Awal H2 & H3 -->
            <!-- 7. Box Rekomendasi 1 (.baca-juga-box dengan 1 link rekomendasi) -->
            <!-- 8. Gambar Konten Kedua (.blog-img-wrapper, img-caption) -->
            <!-- 9. Konten Sub-bab Lanjutan H2 & H3 -->
            <!-- 10. Box Rekomendasi 2 (.baca-juga-box dengan 1 link rekomendasi) -->
            <!-- 11. Tabel Perbandingan/Data (.table-responsive dengan header #1a5f7a) -->
            <!-- 12. Promo CTA Box (.blog-promo-cta dengan tombol .btn-wa-cta) -->
            <!-- 13. FAQ Accordion (.faq-section) -->
            <!-- 14. Kesimpulan -->
            <!-- 15. Bio Penulis (.author-bio) -->
            <!-- 16. Tombol Share (.share-buttons: WA, FB, X, LinkedIn) -->
            <!-- 17. Tags (.chip) -->
          </article>
        </div>

        <!-- Kolom Sidebar (col-lg-4) -->
        <aside class="col-lg-4" id="sidebar">
          <!-- 1. CTA Card (.sidebar-card dengan tombol .btn-wa) -->
          <!-- 2. Artikel Terkait (.sidebar-card dengan 4 artikel terkait, thumbnail 75x75) -->
          <!-- 3. Produk Populer (.sidebar-card dengan list link produk) -->
        </aside>
      </div>
    </div>
  </main>
  <!-- Footer -->
  <!-- Floating WhatsApp -->
  <!-- Scroll Top & Vendor JS Scripts -->
</body>
</html>
```

---

## 3. Checklist Wajib Saat Publikasi Artikel Baru

1. **Kotak Baca Juga (1 Blok = 1 Rekomendasi, Total 2 Blok)**:
   - WAJIB memiliki **2 buah box `.baca-juga-box`** yang ditempatkan terpisah di antara sub-bab artikel.
   - Setiap box hanya memuat **1 link rekomendasi artikel**:
     ```html
     <div class="baca-juga-box">
       <i class="bi bi-bookmark-star me-1" style="color: #d4a853"></i>
       Baca Juga:
       <a href="[url-artikel].html">[Judul Artikel Rekomendasi]</a>
     </div>
     ```
2. **Asset Gambar**:
   - Simpan gambar webp di `assets/img/blog/[slug-artikel]-1.webp` dan `assets/img/blog/[slug-artikel]-2.webp`.
   - Pastikan path di meta OG, JSON-LD, konten artikel, card blog, dan sitemap semuanya mengarah ke file yang ADA dan benar.
3. **Card Blog**:
   - Tambahkan card artikel di bagian paling atas grid `blog.html`.
4. **Sitemap XML**:
   - Daftarkan URL artikel di `sitemap.xml` beserta tag `<image:image>` dan perbarui `<lastmod>`.
5. **Internal Linking**:
   - Tambahkan link artikel baru pada sidebar / konten artikel terkait yang relevan.
