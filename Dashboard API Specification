# 🧩 Dashboard API Specification

**Endpoint:**  
`GET https://brands-dev.win789.xyz/api/dashboard`

**Description:**  
ดึงข้อมูลสรุปสำหรับหน้า Dashboard ของระบบแบรนด์

---

## 📊 Required Data (รวมใน response เดียว)

### 1️⃣ ยอดฝาก (Deposit)
- `total_deposit`: ยอดฝากรวมทั้งหมด `<number>`
- `deposit_7days`: ยอดฝากรวม 7 วันล่าสุด `<number>`

---

### 2️⃣ ยอดถอน (Withdraw)
- `total_withdraw`: ยอดถอนรวมทั้งหมด `<number>`
- `withdraw_7days`: ยอดถอนรวม 7 วันล่าสุด `<number>`

---

### 3️⃣ สมาชิกใหม่
- `new_members_7days`: จำนวนสมาชิกใหม่ใน 7 วันล่าสุด `<number>`

---

### 4️⃣ กำไร (Profit)
- `profit_7days`: กำไร 7 วันล่าสุด `<number>`
- `profit_by_month`: กำไรย้อนหลัง 12 เดือน  
  **Output:**
  ```json
  {
    "jan": number,
    "feb": number,
    "mar": number,
    "apr": number,
    "may": number,
    "jun": number,
    "jul": number,
    "aug": number,
    "sep": number,
    "oct": number,
    "nov": number,
    "dec": number
  }
  ```

---

### 5️⃣ ยอดฝาก–ถอนต่อเดือนย้อนหลัง 12 เดือน
- `deposit_withdraw_by_month`:  
  **Output:**
  ```json
  {
    "jan": number,
    "feb": number,
    "mar": number,
    "apr": number,
    "may": number,
    "jun": number,
    "jul": number,
    "aug": number,
    "sep": number,
    "oct": number,
    "nov": number,
    "dec": number
  }
  ```

---

### 6️⃣ รายการฝาก–ถอนล่าสุด
- `recent_transactions`: รายการฝาก/ถอนล่าสุด (สูงสุด 6 คน)  
  **Output:**
  ```json
  [
    {
      "name": "string",
      "date": "YYYY-MM-DD HH:mm:ss",
      "type": "deposit | withdraw"
    }
  ]
  ```

---

### 7️⃣ รายการเดิมพันล่าสุด
- `recent_bets`: รายการเดิมพันล่าสุด (สูงสุด 6 รายการ)  
  **Output:**
  ```json
  [
    {
      "name": "string",
      "provider": "string",
      "game": "string",
      "bet": number,
      "status": "win | lose"
    }
  ]
  ```

---

### 8️⃣ Top Spender
- `top_spender`: คนถอนเงินมากที่สุด (สูงสุด 6 คน)  
  **Output:**
  ```json
  [
    {
      "name": "string",
      "phone": "string",
      "last_online": "YYYY-MM-DD HH:mm:ss",
      "amount": number
    }
  ]
  ```

---

### 9️⃣ สถิติยอดคนถอนรายวัน (สัปดาห์ก่อน vs สัปดาห์นี้)
- `withdraw_by_day`  
  **Output:**
  ```json
  {
    "last": {
      "sun": number,
      "mon": number,
      "tue": number,
      "wed": number,
      "thu": number,
      "fri": number,
      "sat": number
    },
    "current": {
      "sun": number,
      "mon": number,
      "tue": number,
      "wed": number,
      "thu": number,
      "fri": number,
      "sat": number
    }
  }
  ```

---

### 🔟 สถิติยอดคนฝากรายวัน (สัปดาห์ก่อน vs สัปดาห์นี้)
- `deposit_by_day`  
  **Output:**
  ```json
  {
    "last": {
      "sun": number,
      "mon": number,
      "tue": number,
      "wed": number,
      "thu": number,
      "fri": number,
      "sat": number
    },
    "current": {
      "sun": number,
      "mon": number,
      "tue": number,
      "wed": number,
      "thu": number,
      "fri": number,
      "sat": number
    }
  }
  ```

---

### 11️⃣ ช่องทางสมัครสมาชิก
- `register_channel`  
  **Output:**
  ```json
  {
    "facebook": number,
    "google": number,
    "friend": number
  }
  ```

---

## 📦 ตัวอย่าง Response รวมทั้งหมด
```json
{
  "total_deposit": 125000,
  "deposit_7days": 24000,
  "total_withdraw": 110000,
  "withdraw_7days": 18000,
  "new_members_7days": 42,
  "profit_7days": 6000,
  "profit_by_month": {
    "jan": 10000,
    "feb": 8000,
    "mar": 9500,
    "apr": 7000,
    "may": 12000,
    "jun": 9000,
    "jul": 11000,
    "aug": 8500,
    "sep": 9500,
    "oct": 10000,
    "nov": 0,
    "dec": 0
  },
  "deposit_withdraw_by_month": {
    "jan": 220000,
    "feb": 190000,
    "mar": 210000,
    "apr": 230000,
    "may": 200000,
    "jun": 240000,
    "jul": 250000,
    "aug": 260000,
    "sep": 240000,
    "oct": 250000,
    "nov": 0,
    "dec": 0
  },
  "recent_transactions": [
    { "name": "Somchai", "date": "2025-10-29 14:21:00", "type": "deposit" },
    { "name": "Aree", "date": "2025-10-29 13:52:00", "type": "withdraw" }
  ],
  "recent_bets": [
    { "name": "Napat", "provider": "PGSoft", "game": "Mahjong Ways", "bet": 200, "status": "win" }
  ],
  "top_spender": [
    { "name": "Nui", "phone": "0801234567", "last_online": "2025-10-28 22:10:00", "amount": 50000 }
  ],
  "withdraw_by_day": {
    "last": { "sun": 5, "mon": 6, "tue": 7, "wed": 4, "thu": 8, "fri": 9, "sat": 3 },
    "current": { "sun": 7, "mon": 8, "tue": 6, "wed": 9, "thu": 10, "fri": 11, "sat": 4 }
  },
  "deposit_by_day": {
    "last": { "sun": 4, "mon": 5, "tue": 6, "wed": 7, "thu": 8, "fri": 9, "sat": 3 },
    "current": { "sun": 6, "mon": 7, "tue": 8, "wed": 9, "thu": 10, "fri": 12, "sat": 5 }
  },
  "register_channel": {
    "facebook": 120,
    "google": 80,
    "friend": 40
  }
}
```
---

📌 **Note:**  
- ค่า date/time ใช้ timezone **Asia/Bangkok**  
- ค่าตัวเลขทั้งหมดให้เป็นหน่วย **บาท**  
- ถ้าไม่มีข้อมูลให้ return `0` หรือ array ว่าง `[]`
