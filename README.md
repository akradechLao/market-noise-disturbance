# 🔊 Sound Monitor Dashboard - ตลาด Bigfood แหลมฉบัง

ระบบมอนิเตอร์เสียงรบกวนสำหรับตลาด Bigfood แหลมฉบัง แสดงผลแบบ Real-time พร้อมวิเคราะห์ตามมาตรฐานกฎหมายไทย

## 📋 หน้าที่ใช้งาน

| หน้า | รายละเอียด |
|------|-----------|
| **Dashboard** | ภาพรวมข้อมูลเสียง Real-time, กราฟ Line, สถิติ, การกระจายค่าเสียง |
| **Real-time** | วิเคราะห์เสียงรบกวน (Leq-L90), กราฟรายชั่วโมง, เกณฑ์จำแนก |
| **วิเคราะห์ & รายงาน** | กำหนดช่วงเวลาเอง, ตั้งค่า Background Noise, ส่งออกรายงาน |

## 🎯 คุณสมบัติ

- แสดงค่า Leq, L90, L10, LMax แบบ Real-time
- คำนวณเสียงรบกวน = Leq - L90
- ปัจจัยแก้ไขตามพระราชบัญญัติ/ประกาศ (Thai Legal Correction Factors)
  - Time of Day correction (-10 dB สำหรับ 22:00-06:00)
  - Outdoor Music/TV correction (+5~+10 dB)
  - Ldn (Day-Night Average Sound Level)
- ปรับธีม Dark/Light
- ส่งออกรายงาน PDF, CSV, HTML

## 🚀 วิธีใช้งาน

เปิด `dashboard.html` ในเบราว์เซอร์ หรือเข้าผ่าน [GitHub Pages](https://akradechLao.github.io/market-noise-disturbance/)

## 📁 ไฟล์ในโปรเจค

```
├── dashboard.html          # หน้า Dashboard หลัก
├── noise-disturbance.html  # หน้า Real-time วิเคราะห์เสียงรบกวน
├── analysis.html           # หน้าวิเคราะห์ & สร้างรายงาน
└── README.md
```

## 📐 สูตรคำนวณ

```
Noise Disturbance = Leq - L90

Ldn = 10 log[1/24 × (15×10^(Lday/10) + 9×10^((Lnight+10)/10))]

Time Correction:
  - 06:00-22:00 (กลางวัน): 0 dB
  - 22:00-06:00 (กลางคืน): -10 dB
```

## 🔗 แหล่งอ้างอิง

- ประกาศกระทรวงอุตสาหกรรม เรื่อง กำหนดระดับเสียงการรบกวน พ.ศ. ๒๕๔๘
- ประกาศ กมล. เรื่อง กำหนดระดับเสียงรบกวน พ.ศ. ๒๕๔๗
- กรมควบคุมมลพิษ กระทรวงทรัพยากรธรรมชาติและสิ่งแวดล้อม

## 📊 ข้อมูลจำลอง

> ⚠️ ปัจจุบันใช้ข้อมูลจำลอง (Simulated Data) เนื่องจากเว็บไซต์ bigfood.etc1992.com ใช้ Laravel Livewire ซึ่งไม่มี API โดยตรง

---

สร้างโดย [akradechLao](https://github.com/akradechLao)
