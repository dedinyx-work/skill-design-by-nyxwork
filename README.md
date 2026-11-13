# Design by NyxWork V3

Skill untuk membantu AI coding agent merancang, memperbaiki, dan memvalidasi frontend berdasarkan kebutuhan produk, referensi visual, serta design system yang konsisten.

Skill ini berisi instruksi Markdown dan template yang dibaca oleh agent. Saat digunakan, agent diarahkan untuk memahami tugas terlebih dahulu, memeriksa proyek, memilih aturan yang relevan, mengimplementasikan UI, lalu memeriksa hasil render.

## Daftar isi

- [Tujuan skill](#tujuan-skill)
- [Bagaimana skill bekerja](#bagaimana-skill-bekerja)
- [Prioritas keputusan desain](#prioritas-keputusan-desain)
- [Aturan utama V3](#aturan-utama-v3)
- [Struktur dan fungsi file](#struktur-dan-fungsi-file)
- [Cara instalasi](#cara-instalasi)
- [Cara menggunakan skill](#cara-menggunakan-skill)
- [Hasil dan laporan akhir](#hasil-dan-laporan-akhir)
- [Cara mengecek skill berjalan](#cara-mengecek-skill-berjalan)
- [Batasan dan troubleshooting](#batasan-dan-troubleshooting)

## Tujuan skill

NyxWork membantu agent membuat keputusan UI yang bisa dijelaskan alasannya. Setiap elemen perlu mendukung tugas pengguna, hierarki informasi, kebutuhan interaksi, bahasa brand, atau konsistensi sistem.

Contoh masalah yang ditangani:

- Agent langsung membuat dashboard generik tanpa memahami workflow.
- Warna, spacing, radius, dan tipografi berubah-ubah antarhalaman.
- Komponen baru dibuat padahal komponen setara sudah tersedia.
- Referensi visual diikuti secara dangkal dan kehilangan karakter utamanya.
- Layout desktop hanya diperkecil untuk mobile.
- Pekerjaan dinyatakan selesai setelah build, tanpa melihat hasil UI.

**AI slop** dalam konteks ini adalah keputusan visual, struktur, konten, atau interaksi yang ditambahkan tanpa alasan produk yang jelas: misalnya metrik palsu, badge berlebihan, nested cards, atau dekorasi yang mengganggu hierarki.

## Bagaimana skill bekerja

`SKILL.md` menjadi controller: menentukan urutan kerja, memilih referensi wajib, dan menetapkan syarat penyelesaian. Detail aturan berada di `references/`; template awal berada di `templates/`.

```text
Permintaan pengguna
  ↓
Pahami intent dan tugas utama pengguna
  ↓
Klasifikasikan pekerjaan dan baca referensi wajib
  ↓
Periksa proyek, design system, komponen, token, dan aset
  ↓
Analisis referensi visual bila tersedia
  ↓
Tentukan hierarki, interaksi, token, dan strategi responsive
  ↓
Implementasikan UI
  ↓
Render → Bandingkan → Temukan selisih → Perbaiki → Render lagi
  ↓
Laporkan validasi dan keterbatasan yang masih ada
```

### 1. Memahami intent sebelum styling

Agent mengidentifikasi siapa pengguna, pekerjaan yang perlu diselesaikan, informasi terpenting, dan aksi utama. Urutan keputusan desain adalah:

```text
Product intent → User job → Information architecture → Interaction model
→ Visual hierarchy → Component selection → Styling → Rendered validation
```

Contohnya, halaman operasional untuk membandingkan banyak transaksi memerlukan struktur yang mendukung scanning dan perbandingan. Pilihan tabel, daftar, atau kartu harus mengikuti kebutuhan tersebut.

### 2. Mengklasifikasikan tugas dan memuat referensi

V3 menetapkan lima kategori. Agent wajib membaca file yang ditentukan sebelum membuat keputusan UI.

Semua nama file pada tabel berikut berada di folder `references/`.

| Kategori | Referensi wajib | Kondisi tambahan |
| --- | --- | --- |
| **A — UI baru dari referensi visual** | `visual-reference-analysis.md`, `ui-decision-framework.md`, `anti-ai-slop.md`, `token-generator.md`, `component-governance.md`, `responsive-accessibility.md`, `validation.md` | Baca `design-system-generator.md` jika sistem yang koheren belum tersedia atau perlu diformalkan. |
| **B — Refinement UI existing** | `anti-ai-slop.md`, `component-governance.md`, `responsive-accessibility.md`, `validation.md` | Baca `visual-reference-analysis.md` jika ada referensi; baca `token-generator.md` jika token, tipografi, spacing, radius, elevation, atau peran warna berubah. |
| **C — Pembuatan design system** | `ui-decision-framework.md`, `token-generator.md`, `design-system-generator.md`, `component-governance.md`, `responsive-accessibility.md`, `validation.md` | Sesuaikan keluasan sistem dengan kebutuhan produk. |
| **D — Redesign / migrasi** | `ui-decision-framework.md`, `redesign-migration.md`, `anti-ai-slop.md`, `token-generator.md`, `component-governance.md`, `responsive-accessibility.md`, `validation.md` | Baca `visual-reference-analysis.md` jika ada referensi. |
| **E — Pekerjaan komponen saja** | `component-governance.md`, `anti-ai-slop.md`, `responsive-accessibility.md`, `validation.md` | Batasi perubahan sesuai kebutuhan komponen. |

### 3. Melewati pre-implementation gate

Sebelum mengedit kode UI, agent harus menetapkan klasifikasi tugas, intent, sumber kebenaran, hierarki informasi, karakter visual, kondisi design system, komponen yang dapat dipakai ulang, dampak token, strategi responsive, kebutuhan aksesibilitas, asumsi yang belum didukung, dan keterbatasan aset.

Untuk proyek existing, pendekatannya adalah **Inspect → Reuse → Extend → Refine**.

### 4. Mengimplementasikan keputusan yang konsisten

Agent memakai semantic tokens dan komponen existing, memperluasnya bila perlu, serta menjaga karakter referensi dan brand. Elemen atau perilaku baru harus punya dasar dari requirement, referensi yang disetujui, pola proyek, atau kebutuhan interaksi dan aksesibilitas.

### 5. Memvalidasi hasil render secara iteratif

Agent membandingkan komposisi, alignment, density, whitespace, tipografi, warna, proporsi komponen dan gambar, hierarki, aset, serta perilaku responsive.

Jika hasil menyimpang secara material, agent kembali memeriksa keputusan desain yang mendasarinya. Pemeriksaan teknis seperti lint, typecheck, test, dan build dijalankan sesuai proyek, bersama pemeriksaan visual.

## Prioritas keputusan desain

Ketika beberapa sumber memberi arahan berbeda, urutan pada V3 adalah:

1. Requirement eksplisit pengguna dan keputusan yang telah disetujui.
2. Referensi visual yang disetujui untuk screen yang diminta.
3. Design system produk existing yang koheren.
4. Komponen reusable dan semantic tokens existing.
5. Pola produk, halaman, dan interaksi existing.
6. Aturan governance NyxWork.
7. Solusi intentional yang paling sederhana.
8. Judgment agent.

Konflik material harus diidentifikasi. Nilai pada template harus diganti dengan keputusan project-specific berdasarkan urutan ini.

## Aturan utama V3

### Anti-invention

Section, navigasi, filter, badge, chart, footer, maupun interaksi harus memiliki dasar kebutuhan. Agent tidak boleh menambahkan fitur hanya agar halaman terlihat lebih lengkap.

### Asset fidelity

Untuk foto, ilustrasi, ikonografi, tekstur, atau lettering yang khas, prioritasnya:

```text
Aset persis dari pengguna → Aset proyek yang mendekati
→ Aset yang sengaja dibuat agar sesuai → Placeholder netral
```

Penggantian aset khas dengan emoji, ikon generik, SVG seadanya, atau stock image yang tidak relevan tidak boleh dilakukan diam-diam. Keterbatasan fidelity harus dilaporkan.

### Token-first

Gunakan token sesuai makna pemakaiannya, misalnya `--color-text-primary` atau `--color-bg-surface`. Sebelum membuat nilai baru, agent memeriksa token existing, menggunakannya kembali, atau menambahkan token semantic yang memiliki alasan jelas. Pengecualian satu kali perlu dijelaskan.

### Component governance

Komponen dibuat atau diperluas berdasarkan pola visual berulang, perilaku, atau peran semantic dalam produk. Agent menghindari duplikasi, komponen monolitik, dan UI kit generik yang belum dibutuhkan.

### Responsive transformation

Setiap region perlu strategi yang disengaja:

| Strategi | Makna |
| --- | --- |
| Preserve | Pertahankan bentuk atau struktur yang masih sesuai. |
| Reflow | Ubah susunan mengikuti ruang yang tersedia. |
| Wrap | Izinkan elemen berpindah baris. |
| Collapse | Ringkas bagian yang memang perlu diringkas. |
| Scroll | Sediakan area scroll yang jelas bila diperlukan. |
| Hide | Sembunyikan elemen hanya dengan alasan yang mendukung tugas pengguna. |
| Reorder | Ubah urutan agar hierarki tetap tepat pada viewport lain. |

Validasi mencakup touch target, overflow, safe area, keterbacaan, crop gambar, keyboard, dan focus. Target interaksi mobile umumnya minimal 44×44 CSS px, kecuali ada alternatif aksesibel yang telah ditetapkan.

### Anti-slop dan typography

Agent mengevaluasi dekorasi berlebihan, filler copy, metrik palsu, whitespace tanpa fungsi, serta interaksi yang tidak dibutuhkan. Tipografi dinilai dari karakter, peran, hierarki, weight, scale, line height, dan letter spacing agar sesuai dengan bahasa visual yang disetujui.

## Struktur dan fungsi file

```text
skill-design-by-nyxwork-v3/
├── README.md
├── SKILL.md
├── references/
│   ├── anti-ai-slop.md
│   ├── component-governance.md
│   ├── design-system-generator.md
│   ├── redesign-migration.md
│   ├── responsive-accessibility.md
│   ├── token-generator.md
│   ├── ui-decision-framework.md
│   ├── validation.md
│   └── visual-reference-analysis.md
└── templates/
    ├── design-system.md
    ├── design-tokens.css
    └── design-tokens.json
```

| File | Fungsi |
| --- | --- |
| `SKILL.md` | Controller, klasifikasi tugas, reference loading gate, execution contract, dan completion gate. |
| `references/ui-decision-framework.md` | Memilih struktur dan interaksi berdasarkan tugas pengguna. |
| `references/visual-reference-analysis.md` | Mengekstrak bahasa visual dan aturan reusable dari referensi. |
| `references/anti-ai-slop.md` | Mengidentifikasi elemen visual, struktur, konten, dan interaksi yang tidak memiliki dasar. |
| `references/token-generator.md` | Menghasilkan atau menormalisasi semantic tokens. |
| `references/design-system-generator.md` | Menyusun design system sesuai kebutuhan produk. |
| `references/component-governance.md` | Mengatur reuse, perluasan, dan pembuatan komponen. |
| `references/responsive-accessibility.md` | Mengarahkan adaptasi layout dan aksesibilitas. |
| `references/redesign-migration.md` | Menjaga batas migrasi dan perilaku produk saat redesign. |
| `references/validation.md` | Menetapkan pemeriksaan visual dan teknis berbasis bukti. |
| `templates/design-system.md` | Kerangka dokumentasi keputusan desain proyek. |
| `templates/design-tokens.css` | Contoh awal token dalam CSS custom properties. |
| `templates/design-tokens.json` | Contoh awal representasi token dalam JSON. |

Repository juga memuat `openai.yaml` sebagai metadata integrasi. Instruksi utama V3 tetap berada di `SKILL.md`.

## Cara instalasi

### 1. Ambil repository

```bash
git clone https://github.com/dedinyx-work/skill-design-by-nyxwork.git
```

### 2. Salin package ke direktori skill agent

Salin `SKILL.md`, `references/`, dan `templates/` bersama-sama. Gunakan nama folder yang sesuai dengan nama skill V3: `skill-design-by-nyxwork-v3`.

Lokasi berikut merupakan contoh; dukungan dan mekanisme discovery bergantung pada agent serta versinya.

| Environment | Contoh lokasi |
| --- | --- |
| Agent yang mendukung `.agents/skills` | `.agents/skills/skill-design-by-nyxwork-v3/` |
| Claude Code, project-level | `.claude/skills/skill-design-by-nyxwork-v3/` |
| Cursor dengan dukungan skills | `.cursor/skills/skill-design-by-nyxwork-v3/` |
| OpenCode, project-level | `.opencode/skills/skill-design-by-nyxwork-v3/` |
| OpenCode, global | `~/.config/opencode/skills/skill-design-by-nyxwork-v3/` |

Contoh struktur hasil instalasi:

```text
your-project/
├── .agents/
│   └── skills/
│       └── skill-design-by-nyxwork-v3/
│           ├── SKILL.md
│           ├── references/
│           └── templates/
└── src/
```

### 3. Aktifkan dan verifikasi

Buka session baru bila agent memerlukannya. Minta agent memakai nama skill yang tercantum pada frontmatter `SKILL.md`:

```text
Gunakan skill-design-by-nyxwork-v3.
Baca SKILL.md, jelaskan klasifikasi tugas, lalu muat referensi wajib
untuk melakukan refinement UI existing. Periksa proyek sebelum mengedit.
```

Jika agent belum mendukung discovery skill, arahkan agent membaca file secara eksplisit melalui instruction proyek yang didukungnya, misalnya `AGENTS.md`:

```md
## Frontend design

Untuk pekerjaan UI, baca:
.agents/skills/skill-design-by-nyxwork-v3/SKILL.md

Ikuti klasifikasi tugas, baca referensi wajib, dan jalankan gate
implementasi serta validasi yang ditetapkan oleh skill.
```

Sesuaikan path dengan lokasi instalasi sebenarnya.

## Cara menggunakan skill

Sertakan tujuan, screen yang dikerjakan, batas perubahan, referensi bila ada, dan perangkat target. Agent kemudian mengikuti gate yang sesuai.

### Membuat UI dari referensi visual

```text
Gunakan skill-design-by-nyxwork-v3.

Buat halaman katalog berdasarkan screenshot terlampir.
Tujuan pengguna: menemukan produk dan membuka detailnya.
Target: desktop dan mobile.

Analisis bahasa visual referensi terlebih dahulu, periksa komponen,
token, dan aset proyek, lalu implementasikan halaman ini.
Validasi hasil render dan laporkan fidelity gap yang masih ada.
```

### Memperbaiki halaman existing

```text
Gunakan skill-design-by-nyxwork-v3.

Refine halaman Tasks agar hierarki dan spacing lebih konsisten.
Pertahankan workflow existing dan design system produk.
Periksa reuse komponen, responsive, keyboard, dan focus.
Batasi perubahan pada halaman dan komponen yang diperlukan.
```

### Membuat design system

```text
Gunakan skill-design-by-nyxwork-v3.

Analisis UI existing dan referensi terlampir.
Susun design system project-specific menggunakan templates/design-system.md.
Dokumentasikan semantic tokens, typography, component rules,
responsive behavior, dan accessibility.
Simpan hasilnya di docs/design-system.md.
```

### Melakukan redesign / migrasi

```text
Gunakan skill-design-by-nyxwork-v3.

Redesign halaman Orders berdasarkan referensi terlampir.
Pertahankan filter, sorting, bulk action, dan workflow existing.
Petakan perubahan token dan komponen sebelum implementasi.
Identifikasi konflik antara referensi dan sistem existing.
Lakukan render comparison setelah implementasi dan perbaiki selisihnya.
```

### Mengerjakan satu komponen

```text
Gunakan skill-design-by-nyxwork-v3.

Perbaiki komponen Dialog existing agar responsive dan aksesibel.
Periksa naming, focus management, keyboard, overflow, dan token.
Gunakan variant existing jika memungkinkan.
```

## Hasil dan laporan akhir

Output mengikuti tugas: perubahan UI, dokumentasi design system, token, komponen, atau hasil audit. File design system dan token yang dihasilkan menjadi milik proyek; tentukan lokasi penyimpanannya dalam prompt bila diperlukan.

Setelah implementasi, laporan V3 mencakup:

- Klasifikasi tugas.
- Referensi yang dibaca.
- Source of truth yang digunakan.
- Token yang digunakan ulang atau dibuat.
- Komponen yang digunakan ulang atau dibuat.
- Strategi responsive.
- Pemeriksaan aksesibilitas.
- Pemeriksaan anti-slop.
- Perbandingan visual yang telah dilakukan.
- Fidelity gap atau keterbatasan yang masih ada.

Validasi juga mencatat viewport, selisih yang diperbaiki, kepatuhan token, dan hasil pemeriksaan teknis yang relevan.

Jika referensi wajib dilewati, statusnya harus dinyatakan:

```text
NyxWork execution = INCOMPLETE
```

Pekerjaan selesai ketika tugas utama pengguna jelas, referensi wajib telah dibaca, keputusan desain konsisten, token dan komponen telah diperiksa, responsive serta aksesibilitas tervalidasi, pemeriksaan visual dan teknis lulus, serta keterbatasan fidelity dilaporkan.

## Cara mengecek skill berjalan

Indikator yang dapat diamati:

- Agent memeriksa proyek sebelum membuat UI baru.
- Agent memilih klasifikasi tugas dan membaca referensi wajib.
- Keputusan layout berangkat dari workflow dan hierarki informasi.
- Token, komponen, dan aset existing diperiksa untuk reuse.
- Referensi diterjemahkan menjadi aturan visual yang konsisten.
- Mobile memiliki strategi adaptasi yang dijelaskan.
- Hasil render diperiksa, dibandingkan, dan diperbaiki.
- Laporan akhir membedakan pemeriksaan yang sudah dilakukan dan gap yang tersisa.

## Batasan dan troubleshooting

### Skill tidak terdeteksi

Pastikan nama file adalah `SKILL.md`, direktori instalasi didukung agent, dan folder pendukung ikut disalin. Gunakan nama `skill-design-by-nyxwork-v3` atau berikan path eksplisit. Buka session baru jika discovery dilakukan saat startup.

### Agent membaca controller tetapi melewati references

Minta agent mengidentifikasi kategori A–E dan membaca referensi wajib pada kategori tersebut sebelum melanjutkan. V3 menerapkan progressive loading dengan kewajiban yang spesifik per tugas.

### Hasil terlihat generik atau menyimpang dari referensi

Minta agent kembali ke analisis referensi: komposisi, density, karakter tipografi, proporsi, aset, dan hierarki. Periksa apakah agent memakai nilai template tanpa menyesuaikannya dengan proyek.

### Browser, runtime, atau screenshot tidak tersedia

Skill adalah instruksi untuk agent; kemampuan render bergantung pada tools dan environment. Agent perlu menyatakan pemeriksaan visual yang belum dilakukan dan tidak boleh mengklaim validasi render selesai tanpa melihat hasilnya.

### Aset atau font referensi tidak tersedia

Gunakan urutan asset fidelity dan laporkan selisih yang tersisa. Klaim pixel-perfect tidak tepat jika aset atau font khas belum tersedia.

### Apakah skill otomatis menjamin hasil bagus?

Kualitas hasil bergantung pada kemampuan agent, kelengkapan requirement, kualitas referensi, akses ke kode dan aset, serta kepatuhan terhadap proses. NyxWork memberi kontrak kerja dan kriteria validasi yang bisa diperiksa sepanjang pengerjaan.
