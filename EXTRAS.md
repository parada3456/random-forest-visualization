# Requirements Check & Extras Beyond the Brief

ไฟล์นี้สรุปว่า `index.html` ตรงตามโจทย์หรือไม่ และมีอะไรที่ทำ **เพิ่มเกินโจทย์** บ้าง
(ตรวจจากโค้ดใน `index.html` ณ branch `feature/setup`)

## 1. สถานะตามข้อกำหนดของโจทย์

| ข้อกำหนด | สถานะ | หลักฐานใน `index.html` |
|---|---|---|
| ไฟล์ HTML เดียว (HTML + CSS + JS embedded) | ✅ | ฟอนต์ฝังเป็น base64 ใน `<style id="embedded-fonts">` ไม่มีไฟล์ภายนอก |
| Deploy GitHub Pages ได้ | ✅ | static ล้วน, ไม่มี build step, `index.html` อยู่ root |
| เนื้อหาเป็นภาษาอังกฤษ | ✅ | UI/คำอธิบายเป็นอังกฤษทั้งหมด (ยกเว้นรายชื่อสมาชิกใน footer ซึ่งเป็นชื่อไทย) |
| พื้นหลังสีดำ, Professional | ✅ | `--bg: #070706` |
| Header: หัวข้อ + หลักการสั้นๆ | ✅ | `<h1>Random Forest, Step by Step</h1>` + lede |
| Footer: รายชื่อสมาชิก + CE KMITL | ✅ | `<footer class="site-footer">` สมาชิก 5 คน + `CE KMITL` |
| Body 2 ฝั่ง floating, scrollbar แนวตั้งแยกกัน | ✅ | `.column-left` / `.column-right` แต่ละฝั่ง scroll เอง |
| ซ้ายบน: Data Canvas (random + คลิกสร้าง/ลบ) | ✅ | ปุ่ม Add/Erase, `New sample` (สุ่มข้อมูล) |
| ซ้ายล่าง: Hyperparameters + Step-by-step + Play until Convergence | ✅ | `btnStep`, `btnPlay`, `checkConverged()` |
| ขวาบน: Model State | ✅ | Tree Detail (โครงสร้างต้นไม้), Bootstrap Weights, Forest Overview |
| ขวาล่าง: Loss Graph | ✅ | "Error Curve" แสดง OOB error / Training error ต่อจำนวนต้นไม้ |
| Canvas อัปเดตเมื่อโมเดลเปลี่ยน (Decision Boundary) | ✅ | วาด boundary/สีพื้นที่หลังเพิ่มต้นไม้ |
| พ่นสเปรย์ตามขนาดหัวสเปรย์แบบสุ่ม (และลบได้) | ✅ | Brush size + `addDensity` สุ่มจุดในวงกลม; Erase ลบจุดในวงกลมได้ |

### ข้อสังเกต / ข้อที่ควรตรวจเอง
- **Loss Graph**: โจทย์ว่า "Loss ลดลงทีละ step/epoch" — Random Forest ไม่มี loss แบบ gradient จึงใช้ OOB/Training error เป็นตัวแทน (อาจไม่ monotonic ลดลงเสมอ)
- **README.md** มีแค่หัวข้อเดียว (และเป็น UTF-16) — ยังไม่มีคำอธิบายโปรเจกต์/ลิงก์ Pages
- **PRODUCT.md** ระบุว่าฟอนต์โหลดจาก Google Fonts แต่ในโค้ดจริงฝังแบบ offline แล้ว (เอกสารไม่ตรงกับโค้ด)
- `.github/` (Mermaid/Copilot instructions) ยัง untracked และไม่เกี่ยวกับ Pages deploy — ยังไม่มี workflow

## 2. สิ่งที่ทำเพิ่มนอกเหนือโจทย์

### โหมดและเนื้อหา
1. **Regression mode** (แท็บ Classification / Regression ที่มุมขวาบนของ header) — โจทย์ไม่ได้ระบุ มีทั้ง Data Canvas, Hyperparameters, Model State และ Error Curve (RMSE) ของตัวเอง
2. **Multi-class (A / B / C)** ใน classification มากกว่า 2 คลาส
3. **Dataset patterns**: Blobs / Moons / Circles / XOR / Spiral (classification) และ Sine / Linear / Quadratic / Step / Wave (regression) พร้อมไอคอนตัวอย่าง
4. **ตัวปรับ Noise** และโหมด Points แบบ Total / Per Class

### เครื่องมือบน Canvas
5. **Pan tool, Zoom (+ / − / fit, scroll wheel) และ zoom badge**
6. **Undo** และ **Clear all**
7. **Place an exact point** — กรอกพิกัด x, y เอง
8. **ตัวเลือกความหนาแน่น (density) ของสเปรย์** แยกจากขนาดหัวสเปรย์
9. **Keyboard control บน canvas** (ลูกศร, Enter/Space, +/−, 1/2/3 เลือกคลาส)

### Hyperparameters
10. **Bootstrap sample size**, **Random feature subset toggle**, **Max depth**, **Min samples to split** (โจทย์ให้ปรับ hyperparameter แต่ไม่ได้กำหนดชุดนี้)
11. **Reset Forest** ปุ่มที่สาม
12. Status line บอกสถานะ และข้อความ "Converged" เมื่อ OOB error คงที่ 5 ต้นล่าสุด

### Model State / Visualization
13. **Forest Overview tab**: grid ของทุกต้นไม้ + Final Majority-Vote / Average prediction + viewer ขยายต้นไม้
14. **Tree tabs** เลือกดูทีละต้น
15. **Bootstrap Weights map** (in-bag / out-of-bag ต่อต้นไม้) พร้อม legend และ summary
16. **Stat tiles**: Trees Built, OOB Error, Training Error
17. **Chart extras**: tooltip, ควบคุมด้วยคีย์บอร์ด/ทัช, ตารางข้อมูลแบบ `details` ใต้กราฟ

### UX และการสอน
18. **Guided tour** ปุ่ม "How to use" (แยกชุดสำหรับ classification และ regression)
19. **"Show more" expanders** และ **ⓘ tooltips** อธิบายคณิตศาสตร์ทีละส่วน
20. **Empty states** พร้อมปุ่มนำทาง

### Accessibility / Polish / Engineering
21. ARIA roles/labels, `aria-live`, ข้อความ screen-reader only, focus ring
22. รองรับ `prefers-reduced-motion`, ขยาย touch target บนจอสัมผัส (`pointer: coarse`)
23. **Responsive layout** (breakpoint 900px / 520px)
24. **ฟอนต์ self-hosted (IBM Plex Mono / Sans Thai / Newsreader) ฝัง base64** ให้ใช้งาน offline — ทำให้ไฟล์ใหญ่ ~570 KB
25. สไตล์ scrollbar, design tokens (spacing/type scale), ธีมโทนอุ่นพร้อมสีเน้น
26. เอกสารออกแบบ: `PRODUCT.md`, `DESIGN.md`, `.impeccable/design.json`
