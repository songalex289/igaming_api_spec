## 📈 Report API Specification

**Endpoint:**  
`GET https://brands-dev.win789.xyz/api/report`

**Description:**  
ดึงข้อมูลสรุปรายงาน (Report) สำหรับการวิเคราะห์และตรวจสอบข้อมูลเชิงลึกของระบบ

---

### รายละเอียดข้อมูลที่ต้องการ

#### 1️⃣ ยอดคนฝาก
- `deposit_users`: จำนวนคนที่ฝากเงิน `<number>`

#### 2️⃣ ฝากเงิน (จำนวนเงิน)
- `deposit_amount`:  
  **Output:**  
  ```json
  {
    "auto": number,
    "manual": number
  }
  ```

#### 3️⃣ ยอดคนถอน
- `withdraw_users`: จำนวนคนที่ถอนเงิน `<number>`

#### 4️⃣ ถอนเงิน (จำนวนเงิน)
- `withdraw_amount`:  
  **Output:**  
  ```json
  {
    "auto": number,
    "manual": number
  }
  ```

#### 5️⃣ กำไรขาดทุน
- `profit_loss`: ผลกำไรหรือขาดทุนสุทธิ `<number>`

#### 6️⃣ สมาชิกใหม่ฝากบิลแรก
- `new_users_first_deposit`: จำนวนสมาชิกใหม่ที่ฝากเงินครั้งแรก `<number>`

#### 7️⃣ สมาชิกใหม่ยังไม่ได้ฝากเงิน
- `new_users_no_deposit`: จำนวนสมาชิกใหม่ที่ยังไม่ได้ฝากเงิน `<number>`

#### 8️⃣ ยอดโปรโมชั่น
- `promotion_amount`: ยอดรวมจากโปรโมชั่นทั้งหมด `<number>`

#### 9️⃣ ยอดคูปอง
- `coupon_amount`: ยอดรวมจากคูปองทั้งหมด `<number>`

#### 🔟 ยอดวงล้อ
- `wheel_amount`: ยอดรวมจากวงล้อ `<number>`

#### 11️⃣ ยอดแคชแบ็ก
- `cashback_amount`: ยอดรวมจากแคชแบ็ก `<number>`

#### 12️⃣ ยอดแนะนำเพื่อน
- `referral_amount`: ยอดรวมจากระบบแนะนำเพื่อน `<number>`

#### 13️⃣ สมาชิกเข้าสู่ระบบ
- `active_users`: จำนวนสมาชิกที่เข้าสู่ระบบ `<number>`

#### 14️⃣ แพ้ชนะรวม
- `total_winlose`: ยอดรวมของผลแพ้ชนะ `<number>`

#### 15️⃣ ค่าคอมมิชชั่นรวม
- `total_commission`: ยอดค่าคอมมิชชั่นทั้งหมด `<number>`

#### 16️⃣ สรุปรายงานทั้งเดือน (User Logs)
- `userlogs`: รายการสรุปรายเดือนของผู้ใช้  
  **Output:**  
  ```json
  [
    {
      "name": "string",
      "date": "YYYY-MM-DD",
      "game": "string",
      "turn": number,
      "action": "win | lose",
      "commission": number,
      "status": "string"
    }
  ]
  ```

---

📌 **Note:**  
- ค่า date/time ใช้ timezone **Asia/Bangkok**  
- ค่าตัวเลขทั้งหมดให้เป็นหน่วย **บาท**  
- ถ้าไม่มีข้อมูลให้ return `0` หรือ array ว่าง `[]`
