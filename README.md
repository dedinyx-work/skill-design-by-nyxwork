# Design by NyxWork V3

Skill untuk membantu AI coding agent menghasilkan UI yang punya karakter, hierarki UX yang jelas, konsisten dengan brand, dan setia pada referensi visual.

**Versi paket: 3.2.0.** Nama pemanggilan tetap `skill-design-by-nyxwork-v3`.

User cukup memberi tujuan atau contoh tampilan. Agent bertanggung jawab memeriksa proyek, memilih panduan yang relevan, mengambil keputusan desain yang masuk akal, dan memvalidasi hasil sesuai skala pekerjaan.

## Mulai dengan prompt sederhana

```text
Gunakan skill-design-by-nyxwork-v3.
Buat landing page brand parfum saya, ikuti guideline dan referensi terlampir.
```

Atau tanpa referensi:

```text
Gunakan skill-design-by-nyxwork-v3.
Buat halaman pengelolaan pesanan untuk toko kecil, fokus pada scanning
status pesanan dan aksi yang mudah ditemukan. Mendukung desktop dan mobile.
```

Tidak perlu mengisi formulir brief, memilih kategori tugas, membaca semua file, atau menyetujui setiap tahap. Berikan batasan penting bila ada; agent mengisi detail visual yang reversibel. Pertanyaan hanya diperlukan jika informasi yang hilang mengubah workflow utama, interpretasi brand wajib, atau scope secara material.

## Bagaimana skill bekerja

Skill adalah instruksi Markdown dan template untuk agent, bukan engine rendering mandiri.

```text
Pahami tujuan → Periksa proyek dan sumber → Tentukan arah desain
→ Implementasikan → Periksa hasil → Perbaiki selisih penting
```

1. **Pahami tugas pengguna.** Tentukan aksi utama, informasi terpenting, jenis screen, dan kepadatan konten.
2. **Periksa sumber.** Baca komponen, token, brand guideline, aset, serta referensi yang tersedia.
3. **Tentukan arah.** Susun hierarki, komposisi, karakter tipografi, imagery, dan strategi responsive yang koheren.
4. **Implementasikan.** Reuse atau perluas sistem existing; buat yang baru bila diperlukan.
5. **Validasi.** Periksa workflow, aksesibilitas, komposisi, brand, referensi, dan pemeriksaan teknis yang relevan.
6. **Laporkan secara singkat.** Jelaskan perubahan, pemeriksaan yang benar-benar dilakukan, dan gap yang masih ada.

Edit kecil memakai proses kecil. Redesign besar membutuhkan pemeriksaan dan bukti yang lebih mendalam. Dokumen design system dan laporan audit panjang bersifat opsional sesuai kebutuhan.

## Apa yang membuat hasilnya tidak generik?

Anti-slop berarti setiap pilihan punya alasan, bukan semua desain harus minimalis.

- Komposisi dan density mengikuti tugas: halaman editorial berbeda dengan layar operasional.
- Tipografi, gambar, ritme spacing, dan treatment brand membentuk satu bahasa.
- Kartu, chart, badge, efek, serta fitur hanya digunakan jika mendukung tujuan.
- Brand playful tetap boleh ekspresif; brand editorial tetap boleh memakai headline dramatis.
- Kontrol umum tetap mudah dikenali. Keunikan tidak mengharuskan navigasi atau formulir yang membingungkan.
- Agent tidak boleh mengarang klaim bisnis, testimonial, metrik, integrasi, atau fungsi yang seolah sudah bekerja.

Contoh: halaman parfum tidak otomatis menjadi template SaaS dengan KPI grid. Layar pengelolaan pesanan tidak otomatis menjadi kumpulan kartu besar dengan whitespace berlebihan.

## Prinsip hierarki UI/UX

Panduan membantu agent menentukan:

- Urutan informasi berdasarkan tugas, bukan dekorasi.
- Aksi dominan per konteks, dengan aksi sekunder yang lebih tenang.
- Pengelompokan melalui proximity, alignment, whitespace, dan heading.
- Tabel untuk perbandingan data, daftar untuk scanning item, dan kartu untuk objek independen bila sesuai.
- Progressive disclosure, feedback, recovery, serta state yang relevan.
- Label form, focus, keyboard, contrast, dan prioritas konten mobile.

Prinsip ini adalah default yang dapat dijelaskan, bukan resep layout yang dipaksakan ke setiap produk.

## Aturan brand dan referensi

### Satu urutan otoritas

1. Requirement eksplisit dan pengecualian terarah yang disetujui user.
2. Brand guideline wajib dan aset identitas yang disetujui.
3. Referensi visual yang disetujui, sesuai dimensi yang dituju.
4. Design system, komponen, token, serta pola produk existing yang koheren.
5. Prinsip NyxWork dan judgment agent.

**Brand mengatur identitas; referensi mengatur aspek visual yang memang diminta; requirement mengatur perilaku.** Urutan inspeksi file tidak mengubah otoritas ini.

### Jika design system sudah tersedia

Design system menjadi batas implementasi default. Asumsi agent atau referensi inspirasi tidak memberikan izin untuk menyimpang. Referensi diadaptasikan ke sistem, kecuali user secara eksplisit meminta perubahan sistem tersebut. Konflik yang memerlukan perubahan kontrak disampaikan untuk keputusan terarah.

Sebelum membuat komponen, agent memetakan struktur aplikasi, layout, theme/token, layer komponen, public exports, batas state/data, serta contoh pemakaian lintas fitur. Pemeriksaan tidak berhenti di file halaman yang sedang diedit, tetapi tetap proporsional tanpa membaca semua file.

- Komponen yang setara sudah ada → **wajib reuse melalui API existing**.
- Variant yang sesuai sudah ada → gunakan variant tersebut.
- Dapat disusun dari primitive existing → komposisikan sesuai arsitektur.
- Ada gap kapabilitas → perluas secara koheren atau buat komponen yang benar-benar belum tersedia.
- Perlu keluar dari kontrak design system → jelaskan konflik dan minta keputusan spesifik.

Menyalin markup, mengganti nama komponen, atau membuat wrapper dengan tanggung jawab yang sama tidak dianggap reuse. Komponen baru yang mengikuti sistem untuk kebutuhan yang belum terwakili tetap boleh dibuat tanpa approval berulang, dengan alasan singkat berdasarkan hasil inspeksi.

Contoh: referensi memakai oranye, tetapi brand mewajibkan biru. Pada mode adaptasi brand, agent mengambil komposisi referensi sambil mempertahankan warna resmi. Konflik material dijelaskan; aturan wajib tidak diubah diam-diam.

### Tiga mode referensi

| Mode | Tujuan |
| --- | --- |
| Faithful reproduction | Mereproduksi komposisi, proporsi, tipografi, imagery, dan karakter screen sedekat mungkin, dengan gap yang dinyatakan. |
| Brand adaptation | Mengadaptasi anchor referensi menggunakan font, warna, aset, dan aturan brand sendiri. |
| Directional inspiration | Mengambil kualitas tertentu seperti density atau mood, tanpa menyalin seluruh struktur. |

Agent menyimpulkan mode dari permintaan. User dapat menyebutkannya jika ingin kontrol lebih spesifik.

### Brand map

Untuk pekerjaan yang membutuhkan dokumentasi, agent mencatat aturan logo, warna, font, imagery, composition, voice, dan motion beserta sumbernya. Aturan dibedakan menjadi **mandatory, flexible, inferred, dan unspecified**.

Jika aset/font tidak tersedia, agent memakai fallback yang dijelaskan. Jika pasangan warna resmi tidak aksesibel, agent mencari pairing resmi yang sesuai sebelum meminta keputusan tentang konflik yang belum terselesaikan.

## Struktur paket

Untuk pekerjaan besar, `references/context-and-delivery.md` menambahkan kontrak konteks dan output yang ringkas. Agent membaca `DESIGN.md` atau sumber arah existing bila tersedia; user tidak wajib membuat file baru. Template `design-context.md` dan `delivery-report.md` bersifat opsional.

```text
SKILL.md                         Controller dan aturan otoritas
references/
  ui-decision-framework.md       Hierarki informasi dan keputusan UX
  visual-direction.md            Arah visual non-generik, termasuk brief minim
  brand-guideline-analysis.md    Ekstraksi dan penerapan aturan brand
  visual-reference-analysis.md   Mode fidelity dan pemetaan referensi
  anti-ai-slop.md                Audit visual, struktur, konten, interaksi
  component-governance.md        Reuse dan perluasan komponen
  token-generator.md             Semantic tokens dan mapping existing
  design-system-generator.md     Sistem desain sesuai skala kebutuhan
  responsive-accessibility.md    Transformasi layout dan aksesibilitas
  redesign-migration.md          Migrasi tanpa merusak workflow
  validation.md                  Validasi proporsional berbasis bukti
  context-and-delivery.md         Konteks kerja, check ID, dan format hasil/audit
templates/
  design-brief.md                Catatan arah kerja opsional
  brand-map.md                   Pemetaan aturan brand opsional
  design-system.md               Dokumentasi sistem opsional
  design-tokens.css              Contoh role token CSS
  design-tokens.json             Representasi role contoh yang setara
  validation-notes.md            Catatan bukti opsional
  design-context.md              Konteks lintas screen/session opsional
  delivery-report.md             Tabel status pemeriksaan opsional
openai.yaml                      Metadata integrasi yang disertakan
```

Agent memuat referensi sesuai tugas dan input. Brand yang disediakan memicu panduan brand; referensi visual memicu analisis referensi; perubahan token memicu panduan token. User tidak perlu mengatur routing tersebut.

Template bukan default gaya NyxWork. Nilai warna, font, radius, dan spacing harus disesuaikan dengan proyek. JSON token adalah format contoh sederhana, bukan deklarasi kompatibilitas schema token standar.

## Instalasi

```bash
git clone https://github.com/dedinyx-work/skill-design-by-nyxwork.git
```

Salin package ke folder bernama `skill-design-by-nyxwork-v3`, dengan `SKILL.md`, `references/`, dan `templates/` tetap bersama. Contoh lokasi bergantung pada dukungan agent dan versinya:

| Environment | Contoh lokasi |
| --- | --- |
| Agent dengan discovery `.agents/skills` | `.agents/skills/skill-design-by-nyxwork-v3/` |
| Claude Code | `.claude/skills/skill-design-by-nyxwork-v3/` |
| Cursor dengan dukungan skills | `.cursor/skills/skill-design-by-nyxwork-v3/` |
| OpenCode project-level | `.opencode/skills/skill-design-by-nyxwork-v3/` |
| OpenCode global | `~/.config/opencode/skills/skill-design-by-nyxwork-v3/` |

Restart agent jika discovery terjadi saat startup. Untuk OpenCode, keluar dan buka kembali setelah mengganti skill yang terinstal; session berjalan dapat tetap memakai versi lama.

Jika discovery tidak tersedia, gunakan instruction proyek yang didukung agent, misalnya:

```md
Untuk pekerjaan UI, baca .agents/skills/skill-design-by-nyxwork-v3/SKILL.md
dan ikuti routing referensi serta workflow adaptifnya.
```

Sesuaikan path dengan lokasi sebenarnya. Metadata integrasi yang disertakan tidak menjamin discovery otomatis di semua client; ikuti lokasi metadata yang diminta client tersebut.

## Contoh penggunaan

### Refinement existing
```text
Gunakan skill-design-by-nyxwork-v3.
Rapikan hierarki halaman Tasks dan responsive-nya.
Pertahankan workflow dan design system existing.
```

### Brand adaptation
```text
Gunakan skill-design-by-nyxwork-v3.
Adaptasikan komposisi screenshot ini ke brand guideline terlampir.
Font, logo, dan warna brand wajib dipertahankan.
```

### Reproduksi referensi
```text
Gunakan skill-design-by-nyxwork-v3.
Recreate screen ini sedekat mungkin menggunakan aset yang saya berikan.
Laporkan bagian yang belum bisa sama karena aset atau font yang hilang.
```

### Design system
```text
Gunakan skill-design-by-nyxwork-v3.
Susun sistem desain dari UI dan brand guideline yang tersedia.
Reuse naming token existing dan dokumentasikan di docs/design-system.md.
```

## Validasi dan batasan

Untuk perubahan visual material, agent memeriksa hasil render jika tools tersedia, memperbaiki selisih penting, lalu memeriksa ulang setelah perbaikan. Pemeriksaan dilakukan dari workflow dan aksesibilitas, komposisi, tipografi/aset, proporsi, hingga detail.

Hasil akhir tidak perlu laporan panjang. Cukup perubahan utama, keputusan penting, pemeriksaan yang dilakukan, dan gap. Pekerjaan brand/reference yang besar dapat menambahkan sumber, mode fidelity, dan bukti viewport/state.

- Browser/runtime tidak tersedia: agent menyelesaikan pekerjaan yang memungkinkan dan menyatakan bagian yang belum diverifikasi.
- Font/aset hilang: fallback dan dampak fidelity dijelaskan.
- Screenshot hanya membuktikan tampilan; interaksi perlu pemeriksaan terpisah.
- Skill tidak menjamin pixel-perfect, kelulusan WCAG menyeluruh, atau hasil usability research tanpa bukti.
- Kualitas bergantung pada model, konteks, aset, tools, dan kepatuhan agent. Uji hasil pada proyek nyata.

## Perubahan utama 3.1

- Workflow adaptif menggantikan gate seremonial dan laporan wajib panjang.
- Dukungan eksplisit untuk UI baru tanpa referensi.
- Aturan otoritas tunggal dan analisis brand yang dapat ditelusuri.
- Tiga mode fidelity serta panduan arah visual yang tetap kreatif.
- Prinsip hierarki UI/UX yang lebih operasional.
- Validasi berbasis bukti dan skala dampak, dengan fallback jujur.
- Template token CSS/JSON selaras dan template dokumentasi opsional.

Identitas V3 tetap dipertahankan; metadata paket dinaikkan ke 3.1.0 untuk menandai perubahan workflow.

### Patch 3.1.1

Mempertegas batas design system existing, kewajiban reuse komponen setara, inspeksi arsitektur lintas fitur, dan justifikasi gap sebelum membuat atau memperluas komponen.

### Versi 3.2.0: konteks dan output yang dapat diperiksa

Pekerjaan besar dimulai dengan ringkasan tujuan, sumber otoritatif, arah visual, reuse komponen, mode referensi, dan asumsi material. Agent menyusunnya dari konteks yang tersedia, tanpa formulir atau pertanyaan mode wajib.

Output menggunakan check ID **NW-01 sampai NW-09** untuk arsitektur, reuse, brand/system, hierarki, karakter visual, fidelity, kejujuran konten/interaksi, responsive/aksesibilitas, dan validasi. Status dibedakan menjadi **PASS, FAIL, UNVERIFIED, dan N/A** agar keterbatasan tools tidak disamakan dengan kelulusan.

Contoh output ringkas:

```text
Implemented: halaman Orders mengikuti sistem existing.
Decisions: reuse DataTable, StatusBadge, dan FilterBar; tanpa UI kit baru.
Checks: NW-02 PASS melalui import komponen canonical;
        NW-09 UNVERIFIED karena runtime tidak tersedia.
Remaining: pemeriksaan render desktop/mobile dan interaksi filter.
```

Untuk audit-only, agent memberikan temuan bernomor dengan lokasi, bukti, dampak, dan saran tanpa mengedit. Permintaan memperbaiki tetap dijalankan langsung dalam scope yang diminta.

NyxWork menyatukan arah desain, aturan anti-slop, governance brand dan design system, architecture-aware reuse, serta validasi berbasis bukti dalam satu workflow adaptif.
