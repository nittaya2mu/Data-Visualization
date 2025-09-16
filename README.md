# Data-Visualization
# แพ็กการสอน: Introduction to Data Visualization – ออกแบบหน้าเว็บสำหรับ Data Presentation ด้วย **HTML5 + CSS** และการประยุกต์ใช้ **AI**

> เวอร์ชันสรุปพร้อมสอน: โครงสร้างรายคาบ, เนื้อหา, ใบงาน, ตัวอย่างโค้ด, Rubric, และแนวปฏิบัติการใช้ AI อย่างรับผิดชอบ

---

## 1) ผลลัพธ์การเรียนรู้ (CLOs)
เมื่อจบหน่วย/คอร์สนี้ นิสิตจะสามารถ:
1. อธิบายหลักการพื้นฐานของ Data Visualization (purpose, data types, chart selection, perception) และแนวทาง **storytelling with data**
2. ออกแบบและพัฒนา **หน้าเว็บนำเสนอข้อมูล** ด้วย **HTML5 semantic elements + responsive CSS**
3. ใช้ **SVG** และองค์ประกอบเชิงเวกเตอร์สร้างกราฟพื้นฐาน (เช่น bar chart) โดยไม่พึ่งไลบรารีหนัก
4. ประยุกต์ **AI** เพื่อช่วยงานออกแบบ/พัฒนา: สร้างคอนเซปต์, color palette, alt text, ARIA labels, code review, accessibility check, และ data-to-text summary
5. ปรับปรุง **UX/UI, accessibility (WCAG), performance (Lighthouse)** และ **ethics** ในการนำเสนอข้อมูล

---

## 2) แผนการสอนแบบ 3 คาบ (คาบละ ~90 นาที)

### คาบที่ 1: Foundations & Semantic Web Structure
- **Key topics**: Why viz, chart taxonomy, data-ink ratio, Gestalt, cognitive load; HTML5 semantics (`<header> <nav> <main> <section> <article> <aside> <footer>`), responsive layout (Flex/Grid), typography, color theory (sequential/diverging/qualitative scales)
- **Demo**: Wireframe หน้า Landing (Hero + KPI cards + chart area + insight panel)
- **AI boosters**: ให้ AI ช่วยสกัด key message/insight จากชุดข้อมูลตัวอย่าง, สร้าง color palette เข้ากับ branding และมี contrast ดี
- **Mini‑lab**: ตั้งโครง HTML5 + CSS base (mobile-first), ใส่ dummy KPIs และข้อความนำเรื่อง

### คาบที่ 2: Visual Encodings with HTML+CSS+SVG
- **Key topics**: ข้อดี/ข้อจำกัดของ CSS-only vs SVG, สร้าง **SVG bar chart** แบบปรับขนาดได้, สเกลแกนอย่างง่าย, legend, annotation
- **Accessibility**: ARIA, `role="img"` + `aria-labelledby`, alt text ทางเลือก (data summary), color‑blind safe palette
- **AI boosters**: ให้ AI สร้าง caption/annotation สำหรับกราฟ และตรวจ contrast
- **Mini‑lab**: นำข้อมูลชุดเล็ก (เช่นยอดขายรายเดือน 12 จุด) มาวาดกราฟแท่งด้วย SVG + สไตล์ด้วย CSS

### คาบที่ 3: Data Storytelling, QA, Ethics, Delivery
- **Key topics**: Layout narrative, scrollytelling (no heavy JS), microcopy for insights, performance & QA checklist, data ethics (bias, privacy, misleading viz, cherry‑picking)
- **AI boosters**: Code review + Lighthouse hints, สรุปผลอัตโนมัติ (data‑to‑text), ตรวจการอธิบายกราฟให้กระชับไม่ bias
- **Mini‑lab**: ร้อยหน้าเพจให้สมบูรณ์ + Readability + เพิ่มส่วน “Key Takeaways”

---

## 3) โครงงานย่อย (Assignment)
**โจทย์**: เลือกชุดข้อมูลสาธารณะ (เช่น อุตุนิยมวิทยา/พลังงาน/สาธารณสุข) สร้างหน้าเว็บ 1 หน้า เพื่อนำเสนอ “คำถามเดียวที่ชัดเจน” (Single Focus Question) พร้อมกราฟหลัก 1–2 แบบ (เช่น bar/line) + KPI/Highlight และสรุป insight สั้น ๆ

**ข้อกำหนดเชิงเทคนิค**:
- ใช้ **HTML5 semantics**, **CSS (Flex/Grid)**, **SVG** สำหรับอย่างน้อย 1 กราฟ
- **Responsive** ≥ 360px, 768px, 1280px
- **Accessibility**: contrast AA, keyboard focus, aria‑label/roles เหมาะสม
- **Performance**: Lighthouse Performance ≥ 80
- **AI usage log**: แนบโน้ตสั้น ๆ ว่าใช้ AI ทำอะไร (prompt + ผลลัพธ์ย่อ + สิ่งที่แก้เอง)

---

## 4) Starter Template (โค้ดตัวอย่าง)
> วางเป็นไฟล์เดียวเพื่อทดลองในคาบ; สำหรับส่งงานให้แยก `index.html` และ `styles.css`

### `index.html`
```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Data Presentation — Demo</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <header class="site-header">
    <h1>Thailand Monthly Sales — 2024</h1>
    <p class="subtitle">Single Focus: Which month leads, and how volatile is demand?</p>
  </header>

  <main>
    <section class="kpis" aria-label="Key performance indicators">
      <article class="kpi">
        <h2>Total</h2>
        <p class="kpi-value" id="kpi-total">฿4.2M</p>
      </article>
      <article class="kpi">
        <h2>Best Month</h2>
        <p class="kpi-value" id="kpi-best">August</p>
      </article>
      <article class="kpi">
        <h2>MoM Δ</h2>
        <p class="kpi-value" id="kpi-mom">+6.4%</p>
      </article>
    </section>

    <section class="chart" aria-labelledby="chart-title">
      <h2 id="chart-title">Monthly Sales (Bar Chart)</h2>
      <!-- Accessible SVG: title + desc + ARIA -->
      <figure role="img" aria-labelledby="fig-title fig-desc">
        <svg viewBox="0 0 640 360" class="barchart">
          <title id="fig-title">Monthly sales in 2024</title>
          <desc id="fig-desc">Bar heights indicate sales per month in Thai Baht, Jan to Dec. Peak in August.</desc>
          <!-- axes -->
          <line x1="60" y1="300" x2="600" y2="300" class="axis"/>
          <line x1="60" y1="40" x2="60" y2="300" class="axis"/>
          <!-- y ticks (simplified) -->
          <g class="ticks">
            <text x="48" y="300">0</text>
            <text x="40" y="240">1M</text>
            <text x="40" y="180">2M</text>
            <text x="40" y="120">3M</text>
            <text x="40" y="60">4M</text>
          </g>
          <!-- bars: sample data (values in millions) -->
          <g class="bars">
            <!-- helper: bar(x,label,valueM) width=36 gap=16 start=80 -->
            <g transform="translate(80,0)"><rect width="36" y="220" height="80"/><text x="18" y="320">Jan</text></g>
            <g transform="translate(132,0)"><rect width="36" y="200" height="100"/><text x="18" y="320">Feb</text></g>
            <g transform="translate(184,0)"><rect width="36" y="160" height="140"/><text x="18" y="320">Mar</text></g>
            <g transform="translate(236,0)"><rect width="36" y="140" height="160"/><text x="18" y="320">Apr</text></g>
            <g transform="translate(288,0)"><rect width="36" y="180" height="120"/><text x="18" y="320">May</text></g>
            <g transform="translate(340,0)"><rect width="36" y="200" height="100"/><text x="18" y="320">Jun</text></g>
            <g transform="translate(392,0)"><rect width="36" y="160" height="140"/><text x="18" y="320">Jul</text></g>
            <g transform="translate(444,0)"><rect width="36" y="100" height="200" class="bar-peak"/><text x="18" y="320">Aug</text></g>
            <g transform="translate(496,0)"><rect width="36" y="150" height="150"/><text x="18" y="320">Sep</text></g>
            <g transform="translate(548,0)"><rect width="36" y="180" height="120"/><text x="18" y="320">Oct</text></g>
          </g>
        </svg>
        <figcaption class="caption">Peak demand occurs in <strong>August</strong>; overall trend slightly upward.</figcaption>
      </figure>
    </section>

    <section class="insights">
      <h2>Key Takeaways</h2>
      <ul>
        <li>Seasonality effect: Aug > Mar/Apr; promotions align with school holidays.</li>
        <li>Recommend inventory buffers +5–8% in Jul–Sep.</li>
        <li>Consider A/B testing for price elasticity in Q3.
      </ul>
    </section>
  </main>

  <footer class="site-footer">
    <small>© 2025 DataViz Demo • Accessible • Mobile‑first</small>
  </footer>
</body>
</html>
```

### `styles.css`
```css
:root{
  --bg:#0b0b0c; --fg:#eaeaf0; --muted:#b7b8c3; --accent:#7cd3ff; --peak:#ffd166;
}
*{box-sizing:border-box}
body{margin:0;font-family:Inter,system-ui,-apple-system,Segoe UI,Roboto,Arial,sans-serif;color:var(--fg);background:var(--bg);line-height:1.5}
.site-header{padding:2rem 1rem 1rem;max-width:1100px;margin:auto}
.site-header h1{margin:0 0 .25rem;font-weight:800}
.subtitle{margin:0;color:var(--muted)}
main{max-width:1100px;margin:auto;padding:1rem}
.kpis{display:grid;grid-template-columns:repeat(3,1fr);gap:1rem;margin:1rem 0}
.kpi{background:#16161a;border:1px solid #222;border-radius:14px;padding:1rem}
.kpi h2{margin:.25rem 0;color:var(--muted);font-weight:600}
.kpi-value{font-size:2rem;font-weight:800}
.chart{background:#111;border:1px solid #222;border-radius:14px;padding:1rem;margin:1rem 0}
.barchart{width:100%;height:auto}
.axis{stroke:#3a3b45;stroke-width:2}
.ticks text{fill:#8c8ea1;font-size:12px}
.bars rect{fill:var(--accent);rx:6}
.bars text{fill:#8c8ea1;font-size:12px;text-anchor:middle}
.bar-peak{fill:var(--peak)}
.caption{color:var(--muted);margin-top:.5rem}
.insights{background:#16161a;border:1px solid #222;border-radius:14px;padding:1rem}
.site-footer{padding:1rem;color:#8c8ea1;text-align:center}
@media (max-width:768px){.kpis{grid-template-columns:1fr}}
```

**หมายเหตุสอน**: ค่าน้ำหนักแกน/ความสูงแท่งใน SVG ถูก “ฮาร์ดโค้ด” เพื่อการสาธิตเร็ว ๆ ในคาบแรก ก่อนค่อยสอนการทำสเกลอัตโนมัติภายหลัง (เช่น คำนวณ `y = yBase - value * scale`).

---

## 5) ใบงานในคาบ (Worksheets)

### Worksheet A (คาบ 1): Semantic Layout & Mobile‑first
1) วาด wireframe (มือถือ/แท็บเล็ต/เดสก์ท็อป) 3 ระดับ
2) เขียน `index.html` ใส่ header, KPI, chart placeholder, insights
3) สร้าง CSS base: ตัวอักษร, grid KPIs, สีพื้นหลัง/ข้อความ

**Checkpoint**: หน้าเพจต้องอ่านชัดเจนบนมือถือ 360px

### Worksheet B (คาบ 2): SVG Bar Chart & Accessibility
1) แปลงข้อมูล 10 เดือน เป็นความสูงแท่ง (คำนวณ scale อย่างง่าย)
2) เพิ่ม `<title>` และ `<desc>` ใน `<svg>` + ใส่ `role="img"`
3) ใช้สี **bar‑peak** กับค่ามากสุด + ใส่คำอธิบายใต้รูป

**Checkpoint**: ผู้ใช้คีย์บอร์ดสามารถอ่านลำดับหัวข้อ/คำอธิบายได้

### Worksheet C (คาบ 3): Storytelling & QA
1) เขียน **Key Takeaways** 3–5 bullet บนฐานข้อมูลจริง/กึ่งจริง
2) รัน Lighthouse (หรือ Web Vitals) ตรวจคะแนน Performance/Accessibility
3) Log การใช้ AI: ระบุ prompt 2–3 อัน + สิ่งที่ปรับแก้เอง

---

## 6) Rubric ประเมิน (100%)
- **Story & Clarity (20%)**: คำถามหลักชัด, insight สั้น คม, ไม่ฟุ้ง
- **Design & Layout (20%)**: hierarchy ดี, ระยะห่าง/typography, responsive 3 breakpoints
- **Chart Quality (20%)**: encodings เหมาะ, legend/annotation, peak/exception เน้นถูกต้อง
- **Accessibility (15%)**: contrast ≥ AA, aria/semantics ครบ, keyboard-friendly
- **Performance (10%)**: Lighthouse ≥ 80, โหลดเร็ว (ฟอนต์/ภาพเหมาะสม)
- **AI Use & Documentation (10%)**: ใช้ AI อย่างมีเหตุผล, log โปร่งใส, ไม่ลอกทั้งดุ้น
- **Code Quality (5%)**: โครงสร้างสะอาด, ตั้งชื่อ class/ไฟล์สื่อความหมาย

> **นโยบาย AI**: อนุญาตให้ใช้ช่วยคิด/ตรวจ/แก้ แต่ต้อง **อธิบายสิ่งที่ทำเอง** และอ้างถึง prompt/ผลลัพธ์แบบย่อ ๆ

---

## 7) Prompt ตัวอย่าง (ให้นิสิตใช้กับ AI)
1. **Color Palette**: “Generate a color palette for a dark UI data dashboard with one highlight color for peaks; ensure WCAG AA contrast for body text.”
2. **Alt/ARIA**: “Write an accessible `<title>` and `<desc>` for an SVG bar chart showing monthly sales, with emphasis on August peak.”
3. **Copywriting**: “Draft 3 punchy key takeaways (≤15 words each) from these 12 monthly values [แนบข้อมูล]. Avoid overclaiming.”
4. **Code Review**: “Review my HTML/CSS for responsiveness and accessibility; suggest 5 specific improvements with code snippets.”
5. **Ethics Check**: “Given this dataset and chart, list 3 potential misinterpretations and how to fix them.”

---

## 8) Checklist ก่อนส่งงาน
- [ ] โฟกัสคำถามเดียว (single focus) + หลีกเลี่ยงหลายกราฟพร่ากล
- [ ] ใช้ semantic tags ครบ + mobile‑first
- [ ] กราฟหลักอย่างน้อย 1 แบบด้วย **SVG**
- [ ] Contrast AA, aria labels, keyboard focus
- [ ] Lighthouse ≥ 80 (Performance & Accessibility)
- [ ] แนบ **AI usage log** (≤1 หน้า)

---

## 9) ขยายผล (สำหรับอาจารย์)
- **ทางเลือกไม่ใช้ JS**: CSS bar chart (ใช้ `linear-gradient` / CSS custom properties)
- **ต่อยอดด้วย JS (เสริม)**: ดึง CSV/JSON, สร้างสเกล, เติม animation (prefer CSS‑first)
- **Lib ภายหลัง**: ถ้าต้องใช้ library แนะนำเริ่มจาก **lightweight**/SVG‑first
- **Assessment extension**: ให้ทำ A/B layout หรือเปลี่ยนธีม (light/dark) + report ผล usability mini‑test

---

## 10) เกณฑ์ให้คะแนนแบบย่อย (ใช้ในคาบ)
- Wireframe & Semantic (10%)
- SVG Chart Build (10%)
- Accessibility Fixes (10%)
- Storytelling Copy (5%)
- QA & Lighthouse (5%)

---

## 11) แนวคำถามสะท้อนคิด (Reflection)
- กราฟของคุณ “ตอบคำถาม” ได้เร็วภายใน 5 วินาทีหรือไม่? ทำไม
- สี/ตัวอักษรที่เลือกสอดคล้องกับ tone & purpose หรือไม่
- จุดหลอกตา/ความเสี่ยงการตีความผิดอยู่ตรงไหน และคุณบรรเทาอย่างไร

---

### ภาคผนวก A: โค้ด CSS-only Bar (Bonus)
```html
<div class="bars-css" style="--v1:0.8;--v2:1.0;--v3:0.6;--v4:1.2">
  <div class="bar" style="--v:var(--v1)">Jan</div>
  <div class="bar" style="--v:var(--v2)">Feb</div>
  <div class="bar" style="--v:var(--v3)">Mar</div>
  <div class="bar" style="--v:var(--v4)">Apr</div>
</div>
<style>
.bars-css{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;align-items:end;height:200px}
.bars-css .bar{background:linear-gradient(to top,var(--accent),transparent 120%);height:calc(var(--v)*100%);border-radius:8px;color:#8c8ea1;text-align:center}
</style>
```

### ภาคผนวก B: Lighthouse Quick Wins
- Inline critical CSS, ลดฟอนต์น้ำหนักที่ไม่ใช้, รูปภาพใช้ขนาดพอดี, เปิด `font-display: swap` หากใช้ @font-face
- ลด DOM depth, ใช้ CSS Grid/Flex แทนตารางเมื่อไม่จำเป็น
- หลีกเลี่ยงเงา/ฟิลเตอร์หนัก ๆ บนมือถือ

---

> พร้อมสอนทันที: เปิดเทมเพลต, แจกใบงาน A–C, ใช้ rubric, ปิดคาบด้วย reflection 3 คำถาม

