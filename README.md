# looker-studio-manual

คู่มือเชิงปฏิบัติการสร้าง Dashboard โดยใช้ Looker Studio พร้อมกระบวนการ build ด้วย Material for MkDocs และส่งออก PDF ด้วยปลั๊กอิน MkDocs with PDF

## เริ่มต้นใช้งาน
1. ติดตั้ง dependencies
   ```bash
   pip install -r requirements.txt
   ```
2. พรีวิวเอกสาร
   ```bash
   mkdocs serve
   ```
   > **หมายเหตุ:** ปัจจุบัน auto reloading จะไม่ทำงานเนื่องจาก bug ในไลบรารี click วิธีแก้ไขชั่วคราวคือให้ใช้คำสั่ง `mkdocs serve --livereload` แทน หรือติดตั้งไลบรารี click รุ่น 8.2.1 แทน (`pip install click==8.2.1`) ทั้งนี้ จนกว่า [issue #8478](https://github.com/squidfunk/mkdocs-material/issues/8478) จะได้รับการแก้ไข

   เปิดเบราว์เซอร์ไปที่ http://127.0.0.1:8000
3. สร้างไฟล์ HTML และ PDF
   ```bash
   mkdocs build --strict
   ```
   - HTML จะอยู่ในโฟลเดอร์ `site/`
   - PDF จะอยู่ที่ `site/pdf/looker-studio-workshop.pdf`

## การดีพลอยอัตโนมัติด้วย GitHub Actions
เวิร์กโฟลว์ `.github/workflows/deploy.yml` จะ build และ deploy เอกสารไปยังสาขา `gh-pages` เมื่อมีการ push ไปที่สาขา `main` หรือสั่งรันด้วยตนเองผ่านหน้า Actions โดยใช้ `mkdocs gh-deploy` และ `GITHUB_TOKEN` ที่ GitHub จัดให้
