# ✦ ResumeForge — Resume Builder

A fully client-side, single-file HTML resume builder with live preview, ATS scoring, and PDF export. No backend required.

---

## 🚀 Features

- **Live Preview** — Resume updates in real-time as you type
- **3 Templates** — Classic (dark header), Modern (green), Bold (red accent)
- **ATS Score Checker** — Analyses your resume and gives a score out of 100
- **PDF Export** — Print-to-PDF via the browser
- **Auto Save** — Saves to `localStorage` every 30 seconds
- **Dark / Light Theme** — Toggle with the ☀️ button
- **Zoom Controls** — Zoom in/out on the preview panel

---

## 📁 File Structure

```
ResumeForge/
├── index.html        # Landing / login page
└── builder.html      # Main resume builder (this file)
```

> The entire builder is a **single self-contained HTML file** — no external JS/CSS dependencies except Google Fonts.

---

## 🖥️ How to Use

### 1. Open the Builder
Open `builder.html` directly in any modern browser (Chrome, Edge, Firefox).

### 2. Fill in Your Details

Use the left panel tabs:

| Tab | What to fill |
|-----|-------------|
| **Info** | Name, job title, email, phone, location, LinkedIn, summary |
| **Work** | Work experience and projects |
| **Edu** | Education / qualifications |
| **Skills** | Technical skills (tags) and languages |
| **ATS ✦** | Run ATS analysis on your resume |

### 3. Choose a Template
Click one of the three buttons in the header:
- 🖤 **Classic** — Dark navy header with gold accents
- 🌿 **Modern** — Green-themed, sidebar on the left
- ❤️ **Bold** — White header with red accents

### 4. Export as PDF
Click **⬇ PDF** in the top-right. The browser print dialog opens — choose "Save as PDF".

---

## 🤖 ATS Score

Click the **ATS ✦** tab → **Check ATS Score** to analyse your resume.

The checker evaluates:

| Check | Points |
|-------|--------|
| Full name present | 10 |
| Valid email | 10 |
| Phone number | 5 |
| Detailed summary (50+ chars) | 15 |
| Work experience added | 15 |
| Experience descriptions | 10 |
| Education section | 10 |
| 5+ skills listed | 10 |
| Projects added | 10 |
| LinkedIn URL | 5 |
| **Total** | **100** |

**Score guide:**
- 🎉 90–100 — Excellent
- 👍 75–89 — Very Good
- ⚠️ 50–74 — Needs Improvement
- ❌ 0–49 — Poor, fix issues

---

## 💾 Save & Load

- **Manual save:** Click **💾 Save** in the header
- **Auto save:** Every 30 seconds automatically
- Data is stored in `localStorage` under the key `rf_resume_<userId>` (or `rf_resume_guest` if not logged in)
- Data persists across page refreshes in the same browser

---

## 👤 User / Auth

- User data is read from `localStorage` key `rf_user` (set by `index.html` login page)
- If no user is found, the builder still works in **guest mode**
- Click your name chip (top-right) to **logout** — clears `rf_user` and redirects to `index.html`

---

## ⚙️ Customisation

### Adding a New Template
1. Add a new CSS block `.T4 .rh { ... }` following the pattern of T1/T2/T3
2. Add a button in the header: `<button class="tmpl-btn" onclick="setT(4,this)">🆕 New</button>`
3. The `setT()` function handles switching automatically

### Changing Auto-Save Interval
Find this line near the bottom of the `<script>` tag and change `30000` (ms):
```js
setInterval(saveResume, 30000); // auto-save every 30s
```

### Fonts
Two Google Fonts are used:
- **Playfair Display** — headings and resume name
- **DM Sans** — body text and UI

---

## 🌐 Browser Compatibility

Works in all modern browsers. Recommended: **Chrome** or **Edge** for best PDF export quality.

> ⚠️ Does **not** require a server. Open directly as a local file (`file://`) or host on any static hosting (GitHub Pages, Netlify, etc.).

---

## 📄 License

This project is for personal/educational use. No external libraries or frameworks — pure HTML, CSS, and vanilla JavaScript.
