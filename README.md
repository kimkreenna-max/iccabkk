# ICCA Thailand — MICE Cities Dashboard

แดชบอร์ดแผนที่ 13 เมืองไมซ์ของไทยที่ติดอันดับการจัดประชุมสมาคมนานาชาติ (ICCA Rankings) พ.ศ. 2559–2569

**ฟีเจอร์**
- 🗺️ **แผนที่** — แผนที่เวกเตอร์เฉพาะประเทศไทย ระบายสีจังหวัดตามจำนวนงาน (choropleth) ซูมเข้าเห็นหมุดสถานที่จริงพร้อมกล่องรายละเอียด แผงรายชื่อเมืองแบบ accordion
- 📖 **เรื่องราว** — Scrollytelling 10 บท แผนที่บินพาเที่ยวทีละเมืองตามการเลื่อนอ่าน
- 🏆 **อันดับเมือง** — ตารางอันดับพร้อมกราฟเปรียบเทียบและสถิติย้อนหลัง
- 📍 **สถานที่จัดงาน** — การ์ดศูนย์ประชุม โรงแรม มหาวิทยาลัย พร้อมพิกัด
- 🕐 **ไทม์ไลน์** — ประวัติไทยบนเวที ICCA ตั้งแต่ปี 2517–2569

เป็นไฟล์ HTML ไฟล์เดียว (`index.html`) ไม่ต้อง build ไม่ต้องติดตั้งอะไรเพิ่ม — ภาพพื้นหลังฝังเป็น base64 เรียบร้อยแล้ว

---

## วิธี Deploy ขึ้น GitHub Pages

### วิธีที่ 1 — ผ่านหน้าเว็บ GitHub (ง่ายสุด ไม่ต้องใช้ command line)

1. สร้าง repository ใหม่ที่ [github.com/new](https://github.com/new) เช่นชื่อ `icca-thailand-dashboard` (เลือก **Public**)
2. กด **uploading an existing file** แล้วลากไฟล์ทั้งหมดในโฟลเดอร์นี้ขึ้นไป → **Commit changes**
3. ไปที่ **Settings → Pages**
4. ตรง **Source** เลือก **GitHub Actions** (workflow ในโฟลเดอร์ `.github/workflows/` จะ deploy ให้อัตโนมัติ)
   - หรือเลือก **Deploy from a branch** → branch `main` → folder `/ (root)` → **Save** ก็ได้เช่นกัน
5. รอ 1–2 นาที เว็บจะออนไลน์ที่:
   ```
   https://<username>.github.io/icca-thailand-dashboard/
   ```

### วิธีที่ 2 — ผ่าน Git command line

```bash
cd icca-thailand-dashboard
git init
git add .
git commit -m "ICCA Thailand MICE dashboard"
git branch -M main
git remote add origin https://github.com/<username>/icca-thailand-dashboard.git
git push -u origin main
```

จากนั้นเปิด **Settings → Pages → Source: GitHub Actions** ใน repository

---

## โครงสร้างไฟล์

```
icca-thailand-dashboard/
├── index.html                    # แดชบอร์ดทั้งหมด (ไฟล์เดียวจบ)
├── .github/workflows/deploy.yml  # Auto-deploy ขึ้น GitHub Pages
└── README.md
```

## เทคโนโลยี

- HTML/CSS/JS ล้วน — ไม่มี build step
- [Leaflet 1.9.4](https://leafletjs.com/) (โหลดจาก cdnjs)
- แผนที่พื้นฐาน: CARTO Voyager / © OpenStreetMap
- ฟอนต์: Inter + IBM Plex Sans Thai (Google Fonts)

## แหล่งข้อมูล

ข้อมูลจากรายงาน ICCA GlobeWatch: Business Analytics – Country & City Rankings
และถ้อยแถลงของ TCEB (สำนักงานส่งเสริมการจัดประชุมและนิทรรศการ)
