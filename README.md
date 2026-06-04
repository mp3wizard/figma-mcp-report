# Figma MCP Servers — Interactive Comparison 2026

รายงานเชิงโต้ตอบ (interactive HTML report) เปรียบเทียบ **Figma MCP servers** สำหรับใช้งานร่วมกับ Claude / AI coding agents — รวมตารางเปรียบเทียบแบบ filter/sort, เจาะลึกรายตัว, decision tree และกราฟสรุปในไฟล์ HTML ไฟล์เดียว

> ภาษา: ไทย · อัปเดตข้อมูล: ปี 2026

## MCP ที่เปรียบเทียบ

| MCP Server | ผู้พัฒนา / repo |
|---|---|
| **Figma Official MCP** | Figma (Dev Mode MCP) |
| **Framelink** | GLips/Figma-Context-MCP |
| **Figma Console MCP** | Southleft |
| **Sunnyside Figma Context** | Sunnyside Software |
| **Claude Talk to Figma** | community (WebSocket-based) |

## เนื้อหาในรายงาน

- **ตารางเปรียบเทียบ** — filter + sort ได้ ตามความสามารถแต่ละด้าน
- **เจาะลึกแต่ละ MCP** — จุดเด่น/จุดด้อย, การติดตั้ง, community signals
- **เปรียบเทียบ Commands** — รวม command ของทุก MCP แบบ grouped
- **Decision tree** — ช่วยเลือก MCP ที่เหมาะกับงานภายใน ~30 วินาที
- **กราฟสรุป** — Capability Radar (6 มิติ) และ Bar chart เปรียบเทียบเชิงภาพ

## วิธีเปิดดู

**Local** — เปิดไฟล์ `figma-mcp-comparison-2026.html` ในเบราว์เซอร์ได้เลย

**GitHub Pages** — เปิด Pages บน branch `main` แล้วเข้าผ่าน URL ที่ได้
(ไฟล์ไม่ได้ชื่อ `index.html` ดังนั้นต้องต่อท้าย path: `…/figma-mcp-comparison-2026.html`)

## หมายเหตุ

ตัวรายงานเป็นไฟล์ HTML ไฟล์เดียว เนื้อหา/ข้อมูลฝังอยู่ภายในทั้งหมด แต่ส่วนกราฟและฟอนต์เรียกใช้ผ่าน CDN จึงต้องต่ออินเทอร์เน็ตเพื่อให้แสดงผลครบ:

- [Chart.js 4.4.1](https://www.jsdelivr.com/) (jsDelivr) — สำหรับ radar & bar charts
- Google Fonts — สำหรับ typography

ข้อมูลในรายงานสะท้อนสถานะ ณ ช่วงเวลาที่จัดทำ (2026) — ความสามารถของแต่ละ MCP อาจเปลี่ยนแปลงได้ โปรดตรวจสอบกับ repo ต้นทางก่อนตัดสินใจใช้งานจริง

## Changelog

### อัปเดต 4 มิ.ย. 2026 — มีอะไรเพิ่มเข้ามาให้ Designer บ้าง

รอบนี้เช็ก tool ที่มีจริง ๆ จาก MCP ที่ต่ออยู่ + ดึง source จาก GitHub มาเทียบ ทำให้ตัวเลขและรายการ command ตรงกับของจริงมากขึ้น สรุปแบบเข้าใจง่าย:

**Figma Official MCP — 13 → 17 tools**
ตอนนี้คุยกับ Design System ได้ฉลาดขึ้น เพิ่มความสามารถ "ค้นหา component/token ใน design system", "ดึง library ที่ผูกไว้", และ Code Connect ที่ช่วย *แนะนำ* ให้เองว่า component ใน Figma ควรจับคู่กับไฟล์ code ตัวไหน (ลดงานแมตช์มือ) — เหมาะกับงาน Figma-to-code handoff โดยตรง

**Figma Console MCP — 106 → 108 tools (ตัวที่ครบที่สุด)**
ของเด่นที่เพิ่มเข้ามาและมีประโยชน์กับ DesignOps:
- **ทำงานกับ Figma Slides ได้เต็มรูปแบบ** — สร้าง/ลบ/เรียงสไลด์, ใส่ข้อความ/รูปทรง, ตั้ง transition (gen เด็คจาก outline ได้)
- **Annotation สำหรับ handoff** — แปะ spec ติดกับ node เช่น "ช่องนี้ required, ไม่เกิน 50 ตัวอักษร"
- **Blame node** — ดูว่าใครแก้ layer นี้ล่าสุด คล้าย git blame (ตามรอยเวลาสีปุ่มเพี้ยน)
- **Generate changelog** — สรุปว่าตั้งแต่ส่ง dev รอบก่อน ดีไซน์เปลี่ยนอะไรไปบ้าง
- **Component-set analysis** — ตรวจว่า component ขาด variant ไหน (เช่น Button ลืม state Disabled)

**Claude Talk to Figma — v0.9.2 → v1.0.0 · 54 → 93 tools (เพิ่มเยอะสุด)**
เวอร์ชันเสถียรตัวจริง ขยายฝั่ง "สั่งแก้ดีไซน์ด้วยภาษาธรรมชาติ" ให้ครอบคลุมขึ้นมาก:
- จัดการ **paint / text / effect styles** เป็นชิ้น ๆ ได้ (สร้าง style แล้ว apply)
- **Image filters & transform** — ปรับรูปบน canvas ได้โดยไม่ต้องออกไปแก้ที่อื่น
- **Component set + variant + detach** — ทำงานกับระบบ component ได้ลึกขึ้น
- **Variable modes** — สลับ/ผูก variable mode (เช่น Light/Dark) ได้
- **`set_auto_layout` ตัวเดียวจบ** — เดิมต้องเรียก 5 คำสั่งแยก (mode, padding, align, sizing, gap) ตอนนี้รวมเป็นคำสั่งเดียว สั่งทีเดียวจัด layout ครบ

**Framelink — v0.11.0 → v0.12.0**
ยังคง 2 tools เท่าเดิม (อ่านอย่างเดียว, เน้น token efficiency) — แค่อัปเวอร์ชัน ไม่มีฟีเจอร์ใหม่

**Sunnyside Figma Context — ปรับชื่อ tool ให้ตรงของจริง**
แก้ command ในรายงานที่ชื่อไม่ตรงกับ tool ปัจจุบัน และเพิ่มของที่มีจริง: ดึง **CSS ทุก layer / Basic CSS / raw JSON** ออกมาตรง ๆ, วิเคราะห์โครงหน้า (page structure), และชุด **token simulation** ที่ลองเปลี่ยน token แบบ preview แล้ว apply/rollback ได้

> **หมายเหตุ:** ตัวเลข tool ของ Official / Console / Sunnyside ยึดจาก MCP ที่เชื่อมต่อจริง ส่วน Framelink / ClaudeTalk ยึดจาก source code ใน GitHub repo (`package.json` + tool registration) ณ 4 มิ.ย. 2026
