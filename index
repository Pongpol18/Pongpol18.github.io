<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ระบบรับแจ้งร้องทุกข์ | องค์การบริหารส่วนตำบลคลองหก</title>

<style>
  body {
    font-family: "Sarabun", "TH Sarabun New", sans-serif;
    margin: 0;
    padding: 0;
    color: #1f2937;

    /* พื้นหลังแนวคลอง / น้ำ */
    background:
      radial-gradient(circle at top left, rgba(59,130,246,0.15), transparent 40%),
      radial-gradient(circle at bottom right, rgba(37,99,235,0.18), transparent 45%),
      linear-gradient(180deg, #e0f2fe, #f8fafc 60%);
    min-height: 100vh;
  }

  header {
    background: linear-gradient(135deg, #1e3a8a, #2563eb);
    color: white;
    padding: 30px 16px;
    text-align: center;
  }

  header h1 {
    margin: 0;
    font-size: 28px;
    font-weight: 800;
    letter-spacing: 0.6px;
  }

  header p {
    margin-top: 8px;
    font-size: 17px;
    opacity: 0.95;
  }

  .container {
    max-width: 720px;
    margin: 28px auto;
    background: white;
    border-radius: 14px;
    padding: 26px;
    box-shadow: 0 12px 30px rgba(0,0,0,0.1);
  }

  .section-title {
    font-size: 21px;
    font-weight: 800;
    color: #1e40af;
    margin-bottom: 16px;
    border-left: 7px solid #2563eb;
    padding-left: 12px;
  }

  label {
    display: block;
    margin-top: 14px;
    font-weight: 700;
    font-size: 15.5px;
    color: #0f172a;
  }

  input, textarea {
    width: 100%;
    margin-top: 6px;
    padding: 11px 12px;
    border-radius: 9px;
    border: 1px solid #cbd5e1;
    font-size: 15px;
  }

  textarea {
    resize: vertical;
    min-height: 100px;
  }

  input[type="file"] {
    padding: 6px;
  }

  .hint {
    font-size: 13px;
    color: #475569;
    margin-top: 4px;
  }

  button {
    margin-top: 24px;
    width: 100%;
    background: linear-gradient(135deg, #2563eb, #1d4ed8);
    color: white;
    border: none;
    padding: 15px;
    font-size: 18px;
    font-weight: 800;
    border-radius: 12px;
    cursor: pointer;
  }

  button:hover {
    background: linear-gradient(135deg, #1d4ed8, #1e40af);
  }

  .success {
    text-align: center;
    color: #14532d;
    font-weight: 800;
    font-size: 17px;
    display: none;
    margin-top: 22px;
  }

  footer {
    text-align: center;
    font-size: 13px;
    color: #475569;
    margin: 22px 0;
  }
</style>
</head>

<body>

<header>
  <h1>ระบบรับแจ้งร้องทุกข์</h1>
  <p>องค์การบริหารส่วนตำบลคลองหก</p>
</header>

<div class="container">
  <div class="section-title">ข้อมูลผู้ร้องเรียน</div>

  <form id="complaintForm">
    <label>ชื่อ – นามสกุล</label>
    <input type="text" name="fullname" required>

    <label>หมายเลขโทรศัพท์</label>
    <input type="tel" name="phone" required>

    <label>ที่อยู่</label>
    <textarea name="address" required></textarea>

    <div class="section-title" style="margin-top:26px;">รายละเอียดเรื่องร้องทุกข์</div>

    <label>หัวข้อเรื่องร้องทุกข์</label>
    <input type="text" name="topic" required>

    <label>รายละเอียดเพิ่มเติม</label>
    <textarea name="detail" required></textarea>

    <label>ลิงก์ตำแหน่งที่เกิดเหตุ (Google Maps)</label>
    <input type="url" name="map">
    <div class="hint">ถ้ามี สามารถคัดลอกลิงก์จาก Google Maps มาวาง</div>

    <label>แนบรูปถ่ายประกอบ</label>
    <input type="file" name="photo" accept="image/*">
    <div class="hint">รองรับไฟล์ภาพ เช่น JPG, PNG</div>

    <button type="submit">📨 ส่งเรื่องร้องทุกข์</button>
  </form>

  <div class="success" id="successMsg">
    ✅ ส่งเรื่องร้องทุกข์เรียบร้อยแล้ว<br>
    องค์การบริหารส่วนตำบลคลองหกจะดำเนินการตรวจสอบต่อไป
  </div>
</div>

<footer>
  © องค์การบริหารส่วนตำบลคลองหก
</footer>

<script>
const SCRIPT_URL = "ใส่ URL จาก Google Apps Script ตรงนี้";

document.getElementById("complaintForm").addEventListener("submit", function(e){
  e.preventDefault();
  const formData = new FormData(this);

  fetch(SCRIPT_URL, { method: "POST", body: formData })
    .then(() => {
      this.style.display = "none";
      document.getElementById("successMsg").style.display = "block";
    })
    .catch(() => alert("เกิดข้อผิดพลาด กรุณาลองใหม่อีกครั้ง"));
});
</script>

</body>

</html>
