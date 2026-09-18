# Skill Design by NyxWork v2

Tutorial penggunaan untuk Codex, Claude Code, Cursor, dan AI coding agent lain.

## 1. Apa fungsi skill ini?

Skill ini bertindak sebagai anti-AI-slop product UI design governance layer untuk frontend.

Tujuannya bukan memaksa semua project memiliki visual yang sama.

Skill akan membantu agent:

- membaca design system existing
- membaca komponen existing
- menganalisis visual reference
- mengubah visual reference menjadi design system
- menyusun semantic design tokens
- mendeteksi dan menghilangkan visual, structural, content, dan interaction AI slop
- menjaga component reuse
- menjaga responsive behavior
- menjaga accessibility
- melakukan validation sebelum task dianggap selesai

Flow utama:

```text
User Request
↓
Detect Existing UI System
↓
Analyze Visual Reference if Available
↓
Generate or Normalize Design System
↓
Generate Semantic Tokens
↓
Map Existing Components
↓
Implement or Migrate UI
↓
Responsive + Accessibility
↓
Validation Gate
↓
Done
```

---

# 2. Struktur Skill

Jangan memisahkan file di dalam package.

Struktur harus tetap seperti ini:

```text
skill-design-by-nyxwork/
├── SKILL.md
├── references/
│   ├── anti-ai-slop.md
│   ├── ui-decision-framework.md
│   ├── visual-reference-analysis.md
│   ├── design-system-generator.md
│   ├── token-generator.md
│   ├── component-governance.md
│   ├── redesign-migration.md
│   ├── responsive-accessibility.md
│   └── validation.md
└── templates/
    ├── design-system.md
    ├── design-tokens.css
    └── design-tokens.json
```

`SKILL.md` adalah controller.

Agent membaca file di `references/` hanya ketika task membutuhkan detail tersebut.

File di `templates/` digunakan untuk menghasilkan design system project-specific.

---

# 3. Cara Install

## Opsi A. Project-Level Skill

Gunakan ini jika skill hanya berlaku untuk satu repository.

Recommended cross-agent structure:

```text
your-project/
├── .agents/
│   └── skills/
│       └── skill-design-by-nyxwork/
│           ├── SKILL.md
│           ├── references/
│           └── templates/
└── src/
```

Copy seluruh folder `skill-design-by-nyxwork` ke:

```text
.agents/skills/skill-design-by-nyxwork/
```

Ini adalah pilihan paling portable jika agent yang digunakan mendukung Agent Skills standard.

---

## Opsi B. Global Skill

Gunakan global installation jika ingin memakai skill di banyak project.

Contoh:

```text
~/.agents/skills/skill-design-by-nyxwork/
```

Dengan global skill, user tidak perlu copy skill ke setiap repository.

Untuk team project, project-level installation biasanya lebih aman karena versi skill dapat ikut di-version-control.

---

# 4. Codex

## Project-Level

Letakkan:

```text
.agents/skills/skill-design-by-nyxwork/
```

Pastikan:

```text
.agents/skills/skill-design-by-nyxwork/SKILL.md
```

tersedia.

Restart atau buka session baru jika agent belum mendeteksi skill.

## Global

Gunakan:

```text
~/.agents/skills/skill-design-by-nyxwork/
```

jika Codex environment yang digunakan mendukung user-level Agent Skills.

## Test

Prompt:

```text
Use the skill-design-by-nyxwork skill.

Inspect this frontend before making changes.
Tell me which existing design system, tokens, and shared components you find.
Do not modify anything yet.
```

Expected behavior:

Agent harus melakukan inspection terlebih dahulu.

Agent tidak boleh langsung redesign.

---

# 5. Claude Code

Untuk project-scoped skill, copy folder ke:

```text
.claude/skills/skill-design-by-nyxwork/
```

Struktur:

```text
.claude/
└── skills/
    └── skill-design-by-nyxwork/
        ├── SKILL.md
        ├── references/
        └── templates/
```

Claude dapat menggunakan skill secara otomatis ketika task relevan.

Skill juga dapat dipanggil secara eksplisit jika environment mendukung invocation by skill name.

Test prompt:

```text
Use the skill-design-by-nyxwork skill.

Audit the current UI system.
Identify design tokens, shared components, typography, spacing, radius, colors,
and recurring frontend patterns.

Do not implement changes yet.
```

---

# 6. Cursor

Untuk portability, gunakan:

```text
.agents/skills/skill-design-by-nyxwork/
```

Cursor juga dapat menggunakan project-specific skill location:

```text
.cursor/skills/skill-design-by-nyxwork/
```

Untuk skill yang ingin dipakai lintas agent, prefer:

```text
.agents/skills/
```

Test prompt:

```text
Use the skill-design-by-nyxwork skill to review this page.

First inspect the existing project patterns.
Then identify what is inconsistent before proposing changes.
```

---

# 7. Agent yang Belum Mendukung Agent Skills

Skill tetap dapat digunakan.

Simpan package misalnya di:

```text
.ai/skills/skill-design-by-nyxwork/
```

Kemudian tambahkan instruction project-level seperti:

```text
For frontend UI tasks, always read:
.ai/skills/skill-design-by-nyxwork/SKILL.md

Follow referenced files only when the task requires them.
Treat this skill as the frontend design governance source.
```

Instruction tersebut dapat diletakkan pada file instruction yang memang dibaca
agent, misalnya:

```text
AGENTS.md
CLAUDE.md
project rules
system instructions
```

sesuai kemampuan agent tersebut.

---

# 8. Cara Pakai Normal

User tidak perlu menyebut semua rules.

Prompt biasa sudah cukup.

Example:

```text
Create an employee dashboard for this application.
```

Expected skill behavior:

```text
Inspect project
↓
Find existing components
↓
Find tokens
↓
Understand product style
↓
Reuse existing patterns
↓
Build dashboard
↓
Validate
```

Agent tidak seharusnya otomatis membuat visual style baru.

---

# 9. Cara Pakai dengan Visual Reference

Ini salah satu use case utama skill.

User memberikan:

- screenshot
- Figma
- competitor reference
- UI inspiration
- existing product screenshot

Prompt:

```text
The current frontend looks generic and inconsistent.

Use the attached visual reference as the target design direction.

Before coding:

1. inspect the current frontend
2. analyze the visual reference
3. extract its visual language
4. generate a project design system
5. generate semantic design tokens
6. map existing components to the new system
7. propose the migration plan

Do not blindly copy the screenshot.
Preserve the existing product workflow.
```

Skill akan menggunakan:

```text
references/visual-reference-analysis.md
references/design-system-generator.md
references/token-generator.md
references/redesign-migration.md
```

---

# 10. Expected Reference Analysis

Agent seharusnya mengekstrak:

```text
Density
Typography hierarchy
Spacing rhythm
Surface hierarchy
Color roles
Border treatment
Radius
Shadow behavior
Navigation style
Component proportions
Iconography
Interaction states
Responsive implications
```

Contoh hasil analisis:

```text
Visual Direction:
Structured enterprise SaaS.

Density:
Medium-high.

Surface:
Mostly white with cool gray application background.

Separation:
Border-driven rather than shadow-driven.

Radius:
Restrained, approximately small to medium.

Typography:
Compact sans-serif hierarchy.

Primary Accent:
Single strong blue accent.

Status:
Muted semantic colors.

Controls:
Compact rectangular controls.

Avoid:
Large floating cards, gradients, glow, oversized radius, decorative UI.
```

Agent lalu mengubah hasil tersebut menjadi system rules.

---

# 11. Generate Design System

Prompt:

```text
Use the skill-design-by-nyxwork skill.

Analyze the current product and attached references.

Create a project-specific design system using:
templates/design-system.md

The design system must be derived from the current product and reference,
not from arbitrary default styling.

Do not implement the frontend yet.
```

Recommended output location:

```text
docs/design-system.md
```

atau:

```text
design-system/design-system.md
```

Setelah user approve, file tersebut menjadi source of truth tambahan.

---

# 12. Generate Design Tokens

Prompt:

```text
Now generate semantic design tokens from the approved design system.

Use:
templates/design-tokens.css
templates/design-tokens.json

Avoid one-off values.
Avoid near-duplicate colors.
Preserve existing brand colors when possible.
```

Recommended output:

```text
design-system/
├── design-tokens.css
└── design-tokens.json
```

Jika project sudah punya token system, agent harus melakukan mapping.

Jangan membuat token system paralel tanpa alasan.

---

# 13. Redesign UI yang AI Slop

Prompt recommended:

```text
Use the skill-design-by-nyxwork skill.

The current page looks AI-generated and visually inconsistent.

Use the attached reference as the design direction.

Process:

1. audit the current page
2. identify AI-slop patterns
3. analyze the reference
4. define the target visual language
5. reuse or normalize existing design tokens
6. map existing components
7. redesign this page only
8. preserve the existing workflow and functionality
9. validate responsive behavior and accessibility

Do not redesign unrelated pages.
Do not add arbitrary gradients, shadows, radius, colors, or new UI libraries.
```

Typical AI-slop patterns yang harus ditemukan:

```text
Random gradients
Large rounded cards everywhere
Strong shadows
Glow effects
Excessive whitespace
Too many cards
Too many badges
Oversized headings
Random colors
Decorative icon backgrounds
Unnecessary charts
Duplicate components
Inconsistent spacing
Inconsistent control height
```

---

# 14. Redesign Seluruh Product

Jangan langsung berkata:

```text
Redesign the entire app.
```

Untuk product besar, gunakan staged migration.

Prompt:

```text
Use the skill-design-by-nyxwork skill.

We are redesigning this product using the attached visual references.

First create a migration plan.

Order the work by:

1. design tokens
2. typography
3. buttons and form controls
4. surfaces and cards
5. navigation
6. tables and lists
7. dialogs and overlays
8. high-traffic screens
9. remaining screens

Do not implement everything in one pass.
```

Tujuannya mengurangi visual fragmentation dan regression.

---

# 15. Existing Design System Harus Menang

Jika project sudah punya design system:

```text
Existing coherent system
>
Default style inside this skill
```

Prompt:

```text
Use the skill-design-by-nyxwork skill.

Preserve our existing design system.
Only use the skill for governance, consistency, responsive behavior,
accessibility, and component reuse.

Do not replace our brand or visual identity.
```

Ini penting.

Default blue SaaS tokens di template adalah fallback.

Bukan style wajib.

---

# 16. Reference Harus Menang atas Fallback Style

Jika user memberikan reference visual:

```text
User Requirement
+
Existing Product
+
Visual Reference
>
Fallback Design Tokens
```

Agent harus membuat token project-specific.

Jangan memaksakan warna default dari template.

---

# 17. Approval Workflow yang Direkomendasikan

Untuk redesign besar, gunakan dua tahap.

## Stage 1. Design System

Prompt:

```text
Do not code yet.

Analyze the project and references.

Return:

1. UI audit
2. target visual direction
3. proposed design system
4. proposed semantic tokens
5. component migration map
6. risks and conflicts
```

Review hasil.

## Stage 2. Implementation

Setelah approve:

```text
The proposed design system is approved.

Implement the redesign using the approved tokens and component rules.

Do not introduce new visual decisions unless required by real implementation
constraints.
```

Ini jauh lebih stabil daripada meminta agent redesign dan coding dalam satu prompt.

---

# 18. Recommended Repository Structure

Setelah design system terbentuk:

```text
project/
├── .agents/
│   └── skills/
│       └── skill-design-by-nyxwork/
│
├── design-system/
│   ├── design-system.md
│   ├── design-tokens.css
│   └── design-tokens.json
│
├── src/
│   ├── components/
│   ├── pages/
│   └── styles/
│
└── AGENTS.md
```

Bedakan:

```text
Skill
=
cara agent berpikir dan bekerja

Project Design System
=
keputusan visual project tersebut

Design Tokens
=
nilai implementasi yang digunakan frontend
```

Jangan mencampur ketiganya.

---

# 19. Recommended AGENTS.md Instruction

Jika repository menggunakan `AGENTS.md`, tambahkan instruction ringan:

```text
## Frontend Design

For meaningful frontend UI work, use the skill-design-by-nyxwork skill.

Before creating new UI:
- inspect the existing design system
- inspect shared components
- inspect design tokens
- preserve established product patterns

If visual references are provided:
- analyze them as a visual system
- do not blindly copy screenshots
- translate them into reusable design rules and semantic tokens

Use the project design system in:
design-system/design-system.md

Use existing components and tokens before creating new ones.
```

Jangan copy seluruh `SKILL.md` ke `AGENTS.md`.

Biarkan skill tetap modular.

---

# 20. Prompt untuk Membuat UI Baru

```text
Use the skill-design-by-nyxwork skill.

Create the new Projects page.

Requirements:
- follow the current product design system
- reuse existing components
- reuse existing tokens
- maintain current information density
- support desktop and tablet
- handle loading, empty, and error states

Do not introduce a new visual style.
```

---

# 21. Prompt untuk Refine Existing Page

```text
Use the skill-design-by-nyxwork skill.

Refine this existing Tasks page.

Focus on:
- hierarchy
- spacing consistency
- component consistency
- responsive behavior
- accessibility

Keep the workflow unchanged.

Do not redesign unrelated components.
```

---

# 22. Prompt untuk Reference-Driven Redesign

```text
Use the skill-design-by-nyxwork skill.

I attached the current UI and the target visual reference.

Current UI:
needs redesign.

Reference:
use as visual direction.

Before implementation:
- compare both
- extract the reference design language
- identify conflicts with the existing product
- generate design-system decisions
- generate semantic token changes
- map existing components to the new system

Then redesign the current screen.

Do not copy branding or proprietary assets from the reference.
```

---

# 23. Prompt untuk Audit

```text
Use the skill-design-by-nyxwork skill.

Audit the frontend without modifying files.

Report:

- design-system consistency
- arbitrary styling
- duplicate components
- token problems
- spacing inconsistencies
- typography inconsistencies
- color inconsistencies
- responsive issues
- accessibility issues
- AI-slop patterns

Prioritize issues by impact.
```

---

# 24. Prompt untuk Validation

```text
Use the skill-design-by-nyxwork validation process.

Review the changes we just made.

Check:

- product consistency
- visual hierarchy
- token usage
- component reuse
- interaction states
- loading and empty states
- responsive behavior
- accessibility
- overflow
- long content
- unnecessary visual effects
- engineering quality

Fix critical issues before finishing.
```

---

# 25. Cara Tahu Skill Berjalan

Skill kemungkinan berjalan dengan benar jika agent:

- melakukan inspection sebelum redesign
- menyebut existing tokens dan components
- tidak langsung membuat UI random
- membaca reference sebagai system
- menghasilkan semantic tokens
- menggunakan existing component variants
- menjaga scope
- melakukan responsive check
- melakukan accessibility check
- menjalankan validation sebelum selesai

Skill kemungkinan tidak aktif jika agent langsung:

- menambah gradient
- membuat card radius random
- menambah library UI baru
- membuat warna random
- mengabaikan component existing
- mengubah unrelated pages
- hanya meniru screenshot pixel-by-pixel

---

# 26. Troubleshooting

## Agent Tidak Mendeteksi Skill

Check:

```text
folder-name/
└── SKILL.md
```

Pastikan nama file tepat:

```text
SKILL.md
```

bukan:

```text
skill.md
skills.md
Skill.md
```

Restart session jika diperlukan.

---

## Agent Membaca SKILL.md tetapi Tidak Membaca References

Gunakan prompt:

```text
Use skill-design-by-nyxwork.

For this task, read the relevant reference files linked by SKILL.md before
making design decisions.
```

Agent tidak harus membaca semua reference setiap saat.

Progressive loading memang tujuan struktur ini.

---

## Agent Masih Menghasilkan UI Random

Gunakan staged workflow.

Jangan meminta:

```text
Redesign everything and code it.
```

Gunakan:

```text
Step 1:
Audit and generate the design system.

Step 2:
Wait for approval.

Step 3:
Implement using only the approved design system and tokens.
```

---

## Agent Memaksa Default Blue Style

Prompt:

```text
The default tokens in the skill are fallback only.

Use the existing brand and attached visual references as the source of truth.

Generate project-specific tokens before implementation.
```

---

## Agent Terlalu Banyak Membuat Component Baru

Prompt:

```text
Before continuing, run the component-governance process.

Search the repository for reusable equivalents.

List which existing components should be reused or extended before creating
anything new.
```

---

# 27. Best-Practice Workflow

Untuk hasil paling stabil:

```text
1. Install skill
2. Audit project
3. Provide visual references
4. Generate target design system
5. Review design system
6. Generate semantic tokens
7. Map existing components
8. Approve migration plan
9. Implement foundation
10. Implement screens
11. Run validation
```

Untuk task kecil:

```text
Request
→ Skill
→ Inspect
→ Implement
→ Validate
```

Tidak perlu generate design system baru setiap kali.

---

# 28. Rule of Thumb

Gunakan skill sebagai governance.

Gunakan project design system sebagai visual source of truth.

Gunakan design tokens sebagai implementation source of truth.

Gunakan components sebagai reusable execution layer.

Struktur mentalnya:

```text
Skill Design by NyxWork
        ↓
Project Design System
        ↓
Semantic Design Tokens
        ↓
Shared Components
        ↓
Screens
```

Jika layer di atas konsisten, AI agent memiliki ruang yang jauh lebih kecil
untuk menghasilkan frontend yang liar.
