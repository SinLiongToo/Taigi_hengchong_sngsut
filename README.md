# 🧭 形數羅盤 (Shape & Number Compass) — 台語數學探索

> 🔗 **線上體驗 (GitHub Pages)**: [https://sinliongtoo.github.io/Taigi_hengchong_sngsut/](https://sinliongtoo.github.io/Taigi_hengchong_sngsut/)

形數羅盤 is a responsive, interactive web application designed to teach kids and language learners geometry and basic math terminology in four representations simultaneously: **Tâi-gí (白話字 POJ)**, **Han characters (漢字)**, **Mandarin (華文)**, and **English**.

Designed for **@史秀里冊房 Tō͘ Sìn-liông 製作 2026**.

---

## 🌟 Key Features

1. **Interactive Compass Wedge Selection**:
   - A custom SVG circular compass divided into five interactive wedges: **形狀 Shapes**, **角 Angles**, **線 Lines**, **數字 Numbers**, and **符號 Symbols**.
   - Tap any wedge to dynamically load vocabulary cards for that theme on the right workspace.

2. **Bidirectional Vocabulary Learn Cards**:
   - Flip cards by clicking them to show diacritic POJ, Han, Mandarin translations, and kid-friendly notes.
   - Master terms by starring them to save progress (saved automatically in LocalStorage).

3. **Dynamic Tone Sandhi Audio Synthesis (台語變調合成)**:
   - Integrates the advanced **Linguistic Tone Sandhi Engine** from the *Lô-má-jī Tone Sandhi Tool*.
   - When playing audio, the engine splits compound POJ terms by hyphens (e.g., `saⁿ-kak-hêng`), parses each syllable, and computes the natural tone sandhi changes:
     - **Standard sandhi**: `1 ➔ 7`, `2 ➔ 1`, `3 ➔ 2`, `5 ➔ 7`, `7 ➔ 3`.
     - **Entering stop codas** (`-p`, `-t`, `-k`): `4 ➔ 8`, `8 ➔ 4`.
     - **Glottal stop codas** (`-h`): `4h ➔ drops -h ➔ 2`, `8h ➔ drops -h ➔ 3`.
     - **Sequential flow**: `Word 1 (sandhi) + Word 2 (sandhi) + ... + Word N (base)`.
   - Queries an embedded database of **1,855 unique syllables** to fetch the corresponding recordings from the Ministry of Education (MoE) database.
   - Includes fallback routines: if a sandhi tone is missing from the database, it falls back to the syllable's base tone (with automatic `-h` restoration for glottal stops), and then to other available tones.

4. **Match Game (配對遊戲)**:
   - Features a self-contained card-matching game, encouraging kids to pair the geometric shape drawings with their POJ names. Includes authentic pronunciation on tile clicks.

5. **Glossary Export**:
   - Supports exporting the full vocabulary list (including starred progress) directly as **Markdown** or **JSON** files.

---

## 🎨 Contrast & Styling Corrections

- **"Lines" wedge contrast fix**: 
  - Changed the category theme color for **線 Lines** from dark slate blue (`#1E3A5F`) to a vibrant sky blue (`#3A9AD9`).
  - This ensures that in **Dark Mode**, the "Lines" wedge remains clearly visible and readable against the dark navy background (`#0F1B2D`), and that the line-drawing icons on cards are well-distinguished.
  - Obsolete CSS overrides (`.compass-text.lines { fill: #FFFFFF !important; }`) were removed to allow text coloring to automatically contrast against active/pressed wedges.

---

## 📂 File Directory

- `taigi-geo-compass.html` - The main, self-contained interactive web page. Open in any modern web browser.
- `chhoetaigi_mappings.json` - Vocabulary translation mappings.
- `audio_mapping.json` - MoE audio mappings for vocabulary terms.
