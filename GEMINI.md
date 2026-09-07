# GEMINI.MD - PANDUAN KERJA DAN ATURAN STANDAR MAROON ARSITEK

Seluruh asisten AI dan agen pemrograman WAJIB mematuhi panduan dan aturan berikut dalam setiap interaksi, modifikasi file, atau publikasi artikel di repositori Maroon Arsitek.

---

## 1. Aturan Pembuatan Artikel Blog (STRICT TEMPLATE LOCK)

Semua artikel blog (baik Cluster 1, Cluster 2, Cluster 3, atau cluster harian lainnya) HARUS memiliki arsitektur, komponen, dan nama class CSS yang 100% IDENTIK dan KONSISTEN.

Daftar spesifikasi baku:
1. **Header & Navbar**: Menggunakan `<header id="header" role="banner">` dengan class `.has-dropdown` untuk menu Layanan, tombol CTA `.btn-konsultasi` dengan `data-wa="hero"`, dan tombol `.mobile-nav-toggle`.
2. **Breadcrumb**: Menggunakan `<div class="breadcrumb-bar"><div class="container"><a href="/">Beranda</a><span class="separator">/</span><a href="blog.html">Blog</a><span class="separator">/</span><span>[Judul Singkat]</span></div></div>`.
3. **Struktur Konten Utama**:
   - `<section class="section pt-5 pb-5"><div class="container"><div class="article-layout">`
   - Bagian kiri (`.article-main`):
     - `<h1 class="article-title" data-aos="fade-up">`
     - `.article-top-meta` (Foto Erlang Sinatrya, tanggal artikel, waktu baca)
     - `.featured-image-wrap` (Gambar featured + `.featured-caption`)
     - `.summary-box` (`<h3>Ringkasan Inti</h3>`, lead paragraph, 5 bullet list)
     - `.toc-box` (Tombol `.toc-toggle` + `<ul id="auto-toc-list">`)
     - `.article-body` (Paragraf, H2, H3, `.baca-juga-box`, `<figure class="body-figure">`, dan **`.promo-banner`** di akhir konten)
     - `.article-faq` (Mini accordion dengan `.faq-mini-item`, `.faq-mini-question`, `.faq-mini-answer`)
     - `.share-article-box` (Heading "Bagikan Artikel Ini", tombol share WhatsApp, Facebook, Twitter, LinkedIn)
     - `.article-tags-footer` (Kumpulan tag dengan link `.tag-pill`)
   - Bagian kanan (`.article-sidebar`):
     - `.sidebar-author-card` (Avatar, Erlang Sinatrya, `.sidebar-social` dengan ikon IG/LinkedIn/FB, deskripsi bio)
     - `.sidebar-related` (Heading "Artikel Terkait dari Erlang Sinatrya", 3 item `.related-item`)
4. **Section Layanan & Portofolio**: Menggunakan `<section class="related-articles-section" data-aos="fade-up">` dengan 3 kartu `.related-card` di dalam `.related-grid`.
5. **Section CTA**: Menggunakan `<section class="cta-section py-5">` dengan tombol `.btn-gold`.
6. **Footer**: Menggunakan `<footer id="footer" role="contentinfo" aria-label="Footer Maroon Arsitek">` dengan layout 4 kolom `<div class="row gy-5">` dan copyright `.footer-bottom`.
7. **Floating Buttons**: Menggunakan `.whatsapp-float` (`#wa-float`) dan `.scroll-top` (`#scroll-top-btn`).
8. **JSON-LD Schema**: Wajib memuat `@graph` lengkap (`LocalBusiness`, `WebSite`, `Person`, `Article`, `BreadcrumbList`, `FAQPage`).

---

## 2. Alur Publikasi Artikel

Setiap kali mengunggah artikel:
1. Periksa ketersediaan file gambar di folder `assets/img/blog/` dan `assets/img/galeri/`.
2. Buat file HTML artikel sesuai template baku di atas.
3. Perbarui `blog.html`:
   - Sisipkan item di posisi 1 pada `ItemList` JSON-LD schema (geser posisi item yang ada).
   - Sisipkan kartu artikel di bagian teratas grid `#blog-posts .row.gy-4`.
   - Perbarui angka jumlah artikel pada komentar section.
4. Perbarui `sitemap.xml`:
   - Tambahkan entri `<url>` baru dengan `<lastmod>` yang sesuai.
5. Jalankan audit otomatis:
   - Validasi schema JSON-LD (`validate_all.js`)
   - Validasi ketersediaan gambar (`audit_all_images.js`)
   - Validasi case sensitivity (`case_sensitive_check.js`)
