# Nuvita AI Landing Page — Design Spec
**Tanggal:** 2026-06-01  
**Status:** Approved  
**Stack:** Astro + Vanilla CSS

---

## Konteks

Landing page profesional untuk aplikasi Android **Nuvita AI** — asisten nutrisi berbasis AI yang membantu pengguna tracking kalori dan nutrisi dari foto makanan. Aplikasi sudah live di Google Play Store, gratis, tanpa sosial proof awal.

**Target audiens:** Anak muda 18–30 tahun, aktif medsos, health & fitness-minded (gym-goers, dieters, orang yang ingin hidup lebih sehat).  
**Tujuan utama:** Download aplikasi di Google Play Store.  
**Referensi desain:** riliv.co, diarybunda.co.id, cronometer.com.

---

## Design System

### Warna
| Token | Hex | Penggunaan |
|-------|-----|-----------|
| `--green` | `#10b981` | Primary, CTA, accent |
| `--green-dark` | `#059669` | Gradient pair, hover |
| `--green-ink` | `#064e3b` | Headings, dark text |
| `--green-deep` | `#065f46` | Final CTA background |
| `--orange` | `#f97316` | Accent sekunder, icon highlight |
| `--cream` | `#fffaf0` | Base background |
| `--mint` | `#ecfdf5` | Section background, card fill |
| `--slate-50` | `#f8fafc` | Section background alternatif |
| `--ink` | `#0f172a` | Body text, dark elements |
| `--muted` | `#64748b` | Secondary text |
| `--line` | `rgba(16,185,129,.18)` | Border, separator |

### Tipografi
- **Heading:** Fraunces (serif) — display, emosional, bold
- **Body:** Manrope (sans-serif) — modern, readable
- **Scale:** 11 / 12 / 13 / 14 / 16 / 18 / 20 / 24 / 30 / 38 / clamp(48px,8vw,88px)
- **H1:** `clamp(48px, 8vw, 88px)`, letter-spacing `-0.05em`, line-height `0.95`
- **H2:** `clamp(24px, 4vw, 38px)`, letter-spacing `-0.04em`
- **Body:** `16px`, line-height `1.7`, color `--muted`
- **Eyebrow:** `11px`, uppercase, letter-spacing `.12em`, color `--green-dark`

### Animasi
- **Scroll reveal:** `opacity 0→1` + `translateY 24px→0`, `720ms cubic-bezier(.2,.8,.2,1)`, trigger via `IntersectionObserver`
- **Stagger:** 30–50ms delay per item, maksimum 300ms total
- **Hover button:** `translateY(-2px)`, `200ms ease`
- **Button press:** `scale(0.97)`, `100ms cubic-bezier(.22,1,.36,1)`
- **Float orbs:** `translateY 0→-18px`, `8s ease-in-out infinite`
- **FAQ accordion:** `max-height` expand, `300ms cubic-bezier(.22,1,.36,1)`
- **Semua animasi** respek `prefers-reduced-motion`

### Efek Visual
- Background body: `radial-gradient(circle at top left, #d1fae5, transparent 34rem), var(--cream)`
- Card: `border: 1px solid var(--line)`, `border-radius: 14–20px`, `box-shadow: 0 4px 24px rgba(4,120,87,.06)`
- Phone frame: `border: 6–7px solid #1f2937`, `border-radius: 28–32px`, `box-shadow: 0 32px 64px rgba(0,0,0,.18)`
- CTA primary: `background: linear-gradient(135deg,#10b981,#059669)`, `box-shadow: 0 16px 32px rgba(16,185,129,.28)`

---

## Struktur Halaman (7 Section)

### 1. Hero — Above the fold

**Layout:** Centered, dua phone side-by-side di bawah copy, whitespace luas.

**Komponen:**
- Navbar: Logo + nav links (Fitur, Cara Kerja, FAQ) + tombol Download
- Eyebrow pill: "Gratis · Android · AI-powered"
- H1 (Fraunces): *"Hitung kalori makanan hanya dari foto."*
- Subheadline: *"Nuvita AI scan makananmu, estimasi kalori dan nutrisi secara otomatis. Tidak perlu input manual, tidak perlu cari di database."*
- CTA: Tombol Google Play Store hitam (dengan icon Play Store SVG) — link ke Play Store
- Dua phone mockup side-by-side: phone utama (dashboard kalori + food log) + phone sekunder (scan screen, sedikit di belakang)
- Trust chips di bawah CTA: "✓ Gratis selamanya", "✓ Tanpa input manual", "✓ AI scan dari foto"

**Copy Headline Alternatif:**
1. *"Hitung kalori makanan hanya dari foto."* ← Pilihan utama
2. *"Stop tebak-tebak kalori. Scan aja."*
3. *"Asisten nutrisi AI yang kerja dari foto makananmu."*

**Catatan implementasi:** Phone mockup dibuat dari HTML/CSS dulu, placeholder abu-abu untuk screenshot nyata. User menyediakan screenshot nyata untuk diganti.

---

### 2. Pain — Masalah yang diselesaikan

**Layout:** Centered heading + 3 kartu horizontal (grid 3 kolom).

**Copy heading:** *"Bukan karena kamu malas. Tapi karena prosesnya memang ribet."*  
**Eyebrow:** *"Kenapa tracking gagal?"*

**3 Pain Cards:**
1. ⏱️ **Input manual itu lama** — "Cari nama makanan, pilih porsi, hitung ulang — setiap kali makan. Capek sebelum mulai."
2. 🤔 **Database makanan lokal minim** — "Nasi padang, gado-gado, soto — makanan Indonesia sering tidak ada di aplikasi luar."
3. 📉 **Konsisten itu susah** — "Semangat di minggu pertama, lalu berhenti. Tanpa habit yang mudah, tracking tidak akan bertahan."

**Background:** `#ffffff`

---

### 3. Cara Kerja — 3 Langkah

**Layout:** Centered heading + 3 kolom dengan connector line horizontal.

**Copy heading:** *"Tiga langkah. Itu saja."*

**3 Langkah:**
1. 📷 **Foto makananmu** — "Buka kamera atau pilih foto dari galeri. Tidak perlu setup apapun."
2. 🤖 **AI analisa otomatis** — "Nuvita AI deteksi jenis makanan dan estimasi kalori + nutrisi dalam hitungan detik."
3. 📊 **Pantau progresmu** — "Lihat ringkasan harian, riwayat makanan, dan apakah kamu sudah sesuai target."

**Elemen visual:** Ikon dalam kotak putih border hijau, connector line gradient hijau antar langkah.

**Background:** `#f8fafc`

---

### 4. Fitur Unggulan — Alternating Layout

**Layout:** 2 fitur dengan alternating kiri-kanan (copy + screenshot bergantian).

**Fitur 1 — Scan AI (copy kiri, screenshot kanan):**
- Badge: "01 · Scan AI"
- H3: *"Foto = data nutrisi instan."*
- Body: *"Nuvita AI mengenali ratusan makanan Indonesia — dari nasi padang sampai mie ayam. Tidak perlu database manual."*
- Bullets: Deteksi makanan lokal Indonesia / Estimasi kalori + 4 makronutrien / Hasil dalam < 10 detik
- Screenshot: Scan screen dengan deteksi makanan

**Fitur 2 — Kalori Tracker (screenshot kiri, copy kanan):**
- Badge: "02 · Kalori Tracker"
- H3: *"Pantau kalori harian sesuai target."*
- Body: *"Set target kalori harian — diet, maintenance, atau bulking. Nuvita AI bantu kamu pantau konsumsi dan ingatkan kalau sudah mendekati batas."*
- Bullets: Target kalori personal / Progress bar visual harian / Breakdown makronutrien
- Screenshot: Dashboard kalori harian

**Fitur 3 — Riwayat Makanan (copy kiri, screenshot kanan):**
- Badge: "03 · Riwayat"
- H3: *"Lihat pola makanmu dari hari ke hari."*
- Body: *"Evaluasi progres dengan melihat riwayat 30 hari. Tahu kapan kamu over-eat dan kapan sudah on-track."*
- Screenshot: History screen

**Background:** `#ffffff`  
**Catatan:** Screenshot placeholder diganti dengan screenshot nyata dari user.

---

### 5. Untuk Siapa — Persona Cards

**Layout:** Centered heading + grid 2×2 kartu persona.

**Copy heading:** *"Nuvita AI cocok untuk kamu yang..."*

**4 Persona Cards:**
1. 🏋️ **Sedang diet atau cutting** — "Butuh kontrol kalori ketat tapi tidak mau ribet input manual setiap makan."
2. 💪 **Bulking dan tracking protein** — "Ingin pastikan protein harian cukup untuk mendukung latihan dan pertumbuhan otot."
3. 🍽️ **Penasaran dengan pola makan** — "Tidak sedang diet, tapi ingin tahu berapa kalori yang masuk setiap hari."
4. 🧘 **Gaya hidup sehat jangka panjang** — "Tidak mau diet ekstrem, tapi ingin lebih sadar soal apa yang dimakan setiap hari."

**Background:** `#f8fafc`

---

### 6. FAQ — Accordion

**Layout:** Centered, max-width 640px, accordion interaktif.

**Copy heading:** *"Pertanyaan yang sering muncul"*

**4 FAQ Items:**
1. *"Apakah Nuvita AI benar-benar gratis?"* — "Ya, Nuvita AI sepenuhnya gratis. Tidak ada biaya langganan, tidak ada iklan yang mengganggu."
2. *"Seberapa akurat hasil scan AI-nya?"* — "Hasil scan adalah estimasi berdasarkan AI vision. Akurasi bergantung pada kualitas foto dan jenis makanan. Untuk makanan sederhana, hasilnya cukup akurat sebagai referensi harian."
3. *"Apakah bisa mengenali makanan Indonesia?"* — "Ya. Nuvita AI dirancang untuk mengenali makanan lokal Indonesia seperti nasi padang, gado-gado, mie ayam, soto, dan banyak lagi."
4. *"Apakah data makanan saya tersimpan dengan aman?"* — "Data kamu disimpan lokal di perangkat. Kami berkomitmen menjaga privasi pengguna. Baca kebijakan privasi kami untuk detail lengkap."

**Behavior:** Satu item terbuka sekaligus. Animasi expand smooth.

**Background:** `#ffffff`

---

### 7. Final CTA

**Layout:** Full-width, background `linear-gradient(135deg, #064e3b, #065f46)`, centered.

**Copy:**
- Eyebrow: *"Mulai sekarang, gratis"*
- H2: *"Satu foto. Semua yang perlu kamu tahu soal makan."*
- Body: *"Bergabung dengan pengguna yang sudah tracking nutrisi lebih mudah bersama Nuvita AI."*
- CTA: Tombol Google Play Store putih (background putih, text hijau gelap, icon Play Store)
- Microcopy: "Gratis · Android · Tanpa iklan"

---

### Footer

**Layout:** 3 kolom (brand, navigasi app, legal) + bottom bar.

**Kolom:**
- **Nuvita AI:** Logo + deskripsi singkat
- **Aplikasi:** Fitur, Cara Kerja, FAQ
- **Legal:** Kebijakan Privasi, Syarat & Ketentuan, Disclaimer Nutrisi

**Bottom bar:** Copyright + email hello@nuvita.my.id

**Background:** `#0f172a`

---

## SEO Strategy

### On-Page SEO
- **Title:** `Nuvita AI — Aplikasi Penghitung Kalori & Asisten Nutrisi AI`
- **Meta description:** `Scan makanan dari foto, hitung kalori otomatis dengan AI. Nuvita AI — aplikasi penghitung kalori gratis untuk Android. Tracking nutrisi tanpa input manual.`
- **H1:** `Hitung kalori makanan hanya dari foto.`
- **Canonical:** `https://nuvita.my.id/`

### Schema Markup (JSON-LD) — pertahankan yang sudah ada
- `SoftwareApplication` — name, category (HealthApplication), OS (Android), price (0 IDR)
- `FAQPage` — semua 4 FAQ items
- Tambahkan `WebSite` schema dengan `SearchAction` jika memungkinkan

### Target Keywords
| Keyword | Intent | Section |
|---------|--------|---------|
| aplikasi penghitung kalori | Informational/Download | Hero, Meta |
| scan makanan AI | Informational | Hero, Fitur |
| calorie tracker Indonesia | Download | SEO content |
| aplikasi diet AI Android | Download | Meta, Fitur |
| hitung kalori dari foto | Informational | H1, Hero |
| aplikasi nutrisi gratis | Download | Trust chips, FAQ |

### SEO Content Block (pertahankan section existing)
Tambahkan 1 paragraf ekstra: penekanan pada kata kunci "hitung kalori dari foto makanan" dan "tracking nutrisi Indonesia".

---

## Komponen yang Perlu Dibangun/Diperbarui

| Komponen | Status | Catatan |
|----------|--------|---------|
| `BaseLayout.astro` | Update | Tambah preload font, OG image |
| `src/pages/index.astro` | Full rewrite | Semua 7 section baru |
| `src/styles/global.css` | Full rewrite | Design system baru + animasi |
| `public/images/` | Tambah | Screenshot app (disediakan user) |
| IntersectionObserver script | Baru | Scroll reveal untuk semua `.reveal` |
| FAQ accordion script | Baru | Toggle open/close |

---

## Accessibility Checklist
- [ ] Kontras teks minimum 4.5:1 (semua body text)
- [ ] Alt text bermakna untuk semua gambar
- [ ] Tombol dan link punya `aria-label` jika perlu
- [ ] FAQ accordion menggunakan `<details>/<summary>` atau ARIA proper
- [ ] `prefers-reduced-motion` menonaktifkan semua animasi
- [ ] Urutan heading sekuensial (H1 → H2 → H3)
- [ ] Skip-to-main-content link
- [ ] Touch target minimum 44×44px

---

## Catatan Implementasi

1. **Screenshot nyata** — user perlu menyediakan screenshot aplikasi (PNG/WebP). Gunakan sebagai `<img>` di dalam phone frame HTML/CSS.
2. **Play Store link** — perlu URL Play Store yang nyata untuk dipasang di semua tombol CTA.
3. **Phone frame** — dibuat dari HTML/CSS, bukan gambar statis, agar bisa update konten tanpa edit aset.
4. **Font loading** — preload Fraunces + Manrope critical variants. `font-display: swap`.
5. **Image optimization** — semua screenshot di-convert ke WebP, set `width`/`height` untuk menghindari CLS.
6. **Ikon** — emoji (🏋️, 💪, dst.) di spec ini hanya placeholder. Implementasi menggunakan inline SVG dari Lucide atau Heroicons — konsisten stroke, scalable, mendukung dark mode.
