# Standard Operasional Prosedur (SOP) Pembuatan & Publikasi Artikel Blog Maroon Arsitek

Dokumen ini adalah ATURAN MUTLAK (STRICT RULE) yang WAJIB dipatuhi oleh AI Agent dalam membuat, memperbarui, dan mempublikasikan artikel blog Maroon Arsitek. **DILARANG MENGUBAH, MEMODIFIKASI, ATAU MEMBUAT VARIASI STRUKTUR HTML.** Seluruh cluster artikel (Cluster 1, Cluster 2, Cluster 3, dsb.) harus 100% identik dalam arsitektur HTML, class CSS, penempatan komponen, dan skema JSON-LD.

---

## 1. Template Standar Wajib (Locked Architecture)

Setiap file artikel baru (format: `<slug>.html`) HARUS memiliki struktur persis sebagai berikut:

### A. `<head>`
1. **Meta Dasar**:
   - `charset="utf-8"`, `viewport="width=device-width, initial-scale=1.0"`, `theme-color="#721b2c"`, `http-equiv="Content-Language" content="id"`.
   - Favicons: `assets/img/favicon-logo.webp`.
2. **SEO & GEO**:
   - `<title>[Meta Title] | Maroon Arsitek</title>`
   - `<meta name="description" content="[Meta Description]">`
   - `<meta name="keywords" content="[Focus Keyphrase, Secondary Entities]">`
   - `<meta name="author" content="Erlang Sinatrya">`
   - `<meta name="robots" content="index, follow, max-image-preview:large, max-snippet:-1, max-video-preview:-1">`
   - Canonical & hreflang (`id-ID`, `x-default`) mengarah ke URL canonical lengkap.
   - Open Graph (OG) & Twitter Card lengkap (`assets/img/blog/[image-1].webp`).
   - GEO Meta: `ID-JK`, `Jakarta`, `-6.2088;106.8456`.
3. **Vendor & Main CSS**:
   - Google Fonts (Poppins: 300, 400, 500, 600, 700, 800).
   - `assets/vendor/bootstrap/css/bootstrap.min.css`
   - `assets/vendor/bootstrap-icons/bootstrap-icons.min.css`
   - `assets/vendor/aos/aos.css`
   - `assets/vendor/glightbox/css/glightbox.min.css`
   - `assets/css/main.css?v=1.4`
4. **JSON-LD Schema (`@graph`)**:
   - `LocalBusiness` / `GeneralContractor` / `ProfessionalService` (`#organization`)
   - `WebSite` (`#website`)
   - `Person` (`#/schema/person/erlang-sinatrya`)
   - `Article` (headline, description, mainEntityOfPage, datePublished, dateModified, author, publisher, image, inLanguage="id-ID", articleSection, keywords, speakable=[".summary-box", ".article-faq"])
   - `BreadcrumbList` (Beranda -> Blog -> [Short Title])
   - `FAQPage` (3-4 butir pertanyaan relevan)

---

### B. `<body>` (`class="blog-details-page"`)

1. **Header Standar**:
   - `<header id="header" role="banner">`
   - Navigasi utama dengan brand logo (`assets/img/logo-header.webp`, width=144, height=48).
   - Nav items dengan class dropdown: `<li class="has-dropdown"><a href="#" class="dropdown-trigger"...>Layanan</a><div class="nav-dropdown">...</div></li>`
   - Tombol CTA header: `<a href="#" class="btn-konsultasi nav-cta-desktop" data-wa="hero" id="nav-konsultasi"><i class="bi bi-headset"></i> Hubungi Kami</a>`
   - Tombol Mobile Nav Toggle: `<button class="mobile-nav-toggle" id="mobile-nav-toggle"...>`

2. **Breadcrumb Bar**:
   ```html
   <div class="breadcrumb-bar">
     <div class="container">
       <a href="/">Beranda</a><span class="separator">/</span>
       <a href="blog.html">Blog</a><span class="separator">/</span>
       <span>[Judul Singkat Artikel]</span>
     </div>
   </div>
   ```

3. **Section Utama Artikel (`<section class="section pt-5 pb-5">`)**:
   - Pembungkus: `<div class="container"><div class="article-layout">`
   - **Area Konten Utama (`<div class="article-main">`)**:
     1. `<h1 class="article-title" data-aos="fade-up">[Judul H1 Artikel]</h1>`
     2. Meta atas: `<div class="article-top-meta" data-aos="fade-up" data-aos-delay="100"><div class="meta-author"><img src="assets/img/person/erlang.webp" alt="Erlang Sinatrya" /><span>Erlang Sinatrya</span></div><span><i class="bi bi-calendar4-week"></i> [Tanggal Artikel, cth: 7 September 2026]</span><span><i class="bi bi-clock"></i> 5 menit baca</span></div>`
     3. Hero Gambar: `<div class="featured-image-wrap" data-aos="zoom-in"><img src="assets/img/blog/[gambar-1].webp" alt="..." loading="lazy" decoding="async" /><div class="featured-caption">[Caption Foto — Maroon Arsitek]</div></div>`
     4. Ringkasan: `<div class="summary-box" data-aos="fade-up"><h3>Ringkasan Inti</h3><p>[Lead Summary]</p><ul>[5 Bullet Points]</ul></div>`
     5. Daftar Isi: `<div class="toc-box"><button class="toc-toggle" onclick="this.classList.toggle('active'); this.nextElementSibling.classList.toggle('show')">Daftar Isi Artikel <i class="bi bi-chevron-right"></i></button><div class="toc-content"><ul id="auto-toc-list"></ul></div></div>`
     6. Body Artikel (`<div class="article-body">`):
        - Paragraf pengantar & internal link.
        - H2 dan H3 terstruktur.
        - Kotak Baca Juga: `<div class="baca-juga-box"><i class="bi bi-bookmark-star"></i><span class="label">Baca Juga:</span><a href="[slug-terkait].html">[Judul Terkait]</a></div>`
        - Gambar Sekunder Artikel: `<figure class="body-figure" data-aos="fade-up"><img src="assets/img/blog/[gambar-2].webp" alt="..." loading="lazy" decoding="async" /><figcaption>[Caption Gambar — Maroon Arsitek]</figcaption></figure>`
        - **Promo Banner (WAJIB di ujung akhir sebelum penutup .article-body)**:
          ```html
          <a href="https://wa.me/62088989643555" target="_blank" class="promo-banner" data-aos="fade-up">
            <img src="assets/img/galeri/[banner-img].webp" alt="Konsultasi Maroon Arsitek via WhatsApp" loading="lazy" />
            <div class="promo-overlay">
              <span class="promo-text">[Pesan Ajakan Konsultasi Sesuai Topik]</span>
              <span class="promo-cta"><i class="bi bi-whatsapp"></i> Konsultasi via WhatsApp</span>
            </div>
          </a>
          ```
     7. FAQ Mini: `<div class="article-faq" data-aos="fade-up"><h3>Pertanyaan Seputar [Topik]</h3><div class="faq-mini-item"><button class="faq-mini-question">[Pertanyaan]<i class="bi bi-plus-lg"></i></button><div class="faq-mini-answer"><p>[Jawaban]</p></div></div>...</div>`
     8. Share Box:
        ```html
        <div class="share-article-box" data-aos="fade-up">
          <h4>Bagikan Artikel Ini</h4>
          <div class="share-buttons-row">
            <a href="#" target="_blank" class="share-btn whatsapp" data-share="whatsapp"><i class="bi bi-whatsapp"></i> WhatsApp</a>
            <a href="#" target="_blank" class="share-btn facebook" data-share="facebook"><i class="bi bi-facebook"></i> Facebook</a>
            <a href="#" target="_blank" class="share-btn twitter" data-share="twitter"><i class="bi bi-twitter-x"></i> Twitter</a>
            <a href="#" target="_blank" class="share-btn linkedin" data-share="linkedin"><i class="bi bi-linkedin"></i> LinkedIn</a>
          </div>
        </div>
        ```
     9. Tag Footer:
        ```html
        <div class="article-tags-footer">
          <a href="blog.html" class="tag-pill">[Tag 1]</a>
          <a href="blog.html" class="tag-pill">[Tag 2]</a>
          <a href="blog.html" class="tag-pill">[Tag 3]</a>
        </div>
        ```
   - **Sidebar Artikel (`<aside class="article-sidebar">`)**:
     1. Author Card:
        ```html
        <div class="sidebar-author-card">
          <img src="assets/img/person/erlang.webp" alt="Erlang Sinatrya" />
          <h4>Erlang Sinatrya</h4>
          <div class="sidebar-social">
            <a href="https://instagram.com" target="_blank" rel="noopener noreferrer" aria-label="Instagram"><i class="bi bi-instagram"></i></a>
            <a href="https://linkedin.com" target="_blank" rel="noopener noreferrer" aria-label="LinkedIn"><i class="bi bi-linkedin"></i></a>
            <a href="https://facebook.com" target="_blank" rel="noopener noreferrer" aria-label="Facebook"><i class="bi bi-facebook"></i></a>
          </div>
          <p class="desc">
            Erlang Sinatrya adalah Penulis &amp; Arsitektur Specialist di Maroon Arsitek yang fokus membahas perancangan arsitektur modern, manajemen konstruksi hunian mewah, dan efisiensi biaya properti di Indonesia.
          </p>
        </div>
        ```
     2. Related Posts:
        ```html
        <div class="sidebar-related">
          <h4>Artikel Terkait dari Erlang Sinatrya</h4>
          <a href="[slug-1].html" class="related-item">
            <img src="assets/img/blog/[thumb-1].webp" alt="..." />
            <div>
              <h5>[Judul Pendek]</h5>
              <span>[Tanggal]</span>
            </div>
          </a>
          <!-- total 3 artikel -->
        </div>
        ```

4. **Section Layanan & Portofolio Terkait**:
   ```html
   <section class="related-articles-section" data-aos="fade-up">
     <div class="container">
       <h3 class="related-heading">Layanan &amp; Portofolio Terkait dari Maroon Arsitek</h3>
       <div class="related-grid">
         <article class="related-card">
           <a href="[url-layanan]"><img src="assets/img/..." alt="..." loading="lazy" /></a>
           <div class="related-card-content">
             <h4><a href="[url-layanan]">[Nama Layanan]</a></h4>
             <p>[Deskripsi Singkat]</p>
             <a href="[url-layanan]" class="related-read-more">Lihat Layanan <i class="bi bi-arrow-right"></i></a>
           </div>
         </article>
         <!-- total 3 kartu -->
       </div>
     </div>
   </section>
   ```

5. **Section CTA**:
   ```html
   <section class="cta-section py-5">
     <div class="container text-center" data-aos="fade-up">
       <h2>[Heading CTA]</h2>
       <p class="mb-4">[Deskripsi CTA]</p>
       <a href="https://wa.me/62088989643555" target="_blank" class="btn-gold" style="display: inline-flex; align-items: center; gap: 8px; text-decoration: none; border-radius: 30px;">
         <i class="bi bi-whatsapp"></i> [Teks Tombol WA]
       </a>
     </div>
   </section>
   ```

6. **Footer**:
   - `<footer id="footer" role="contentinfo" aria-label="Footer Maroon Arsitek">`
   - Layout grid 4 kolom: `<div class="row gy-5">` (Brand + Contact, Layanan, Navigasi, Artikel Populer).
   - Bottom bar: `<div class="footer-bottom"><p>&copy; <span id="footer-year"></span> <strong>Maroon Arsitek</strong>. Jasa Arsitek &amp; Kontraktor Profesional di Indonesia.</p></div>`

7. **Floating & Scripts**:
   - WhatsApp float: `<a href="#" class="whatsapp-float" data-wa="cta" id="wa-float" aria-label="Hubungi Maroon Arsitek via WhatsApp"><i class="bi bi-whatsapp" aria-hidden="true"></i></a>`
   - Scroll top: `<button class="scroll-top" id="scroll-top-btn" aria-label="Kembali ke atas"><i class="bi bi-chevron-up" aria-hidden="true"></i></button>`
   - Scripts: Bootstrap 5, AOS, Glightbox, `main.js?v=1.1`, Script Auto-TOC, Script FAQ Accordion, Script Share URLs.

---

## 2. Checklist Sinkronisasi Blog & Sitemap (WAJIB)

Setelah membuat file artikel HTML:
1. **`blog.html`**:
   - Masukkan artikel baru pada urutan teratas (`position: 1`) di skema `ItemList` JSON-LD, lalu geser nomor posisi artikel sebelumnya (`position: idx + 2`).
   - Masukkan kartu artikel baru pada urutan teratas di dalam `#blog-posts .row.gy-4`.
   - Perbarui nomor jumlah artikel pada komentar `<!-- ══ BLOG POSTS SECTION (X ARTIKEL) ══════════════════════════════════════ -->`.
2. **`sitemap.xml`**:
   - Tambahkan entri `<url>` baru dengan `<loc>`, `<lastmod>YYYY-MM-DD</lastmod>`, `<changefreq>weekly</changefreq>`, dan `<priority>0.8</priority>`.
3. **Audit Otomatis**:
   - Jalankan skrip `validate_all.js` (validasi JSON-LD).
   - Jalankan skrip `audit_all_images.js` (memastikan tidak ada gambar yang hilang).
   - Jalankan skrip `case_sensitive_check.js` (memastikan kecocokan case sensitivity huruf file gambar).
