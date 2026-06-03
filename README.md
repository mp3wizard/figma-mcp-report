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
