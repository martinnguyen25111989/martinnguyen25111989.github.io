# 📤 Hướng dẫn deploy lên GitHub Pages

Anh có 2 thứ cần upload lên GitHub:

1. **Portfolio website** → repo `martinnguyen25111989.github.io` → tự deploy ra URL https://martinnguyen25111989.github.io
2. **GitHub Profile README** → repo `martinnguyen25111989` (cùng tên username) → hiển thị đẹp trên trang profile

---

## 🚀 Phần 1: Deploy Portfolio Website

### Bước 1 — Tạo repo mới trên GitHub

1. Vào https://github.com/new
2. **Repository name:** `martinnguyen25111989.github.io` (phải đúng chính xác — đây là tên đặc biệt cho GitHub Pages user site)
3. Để **Public**
4. **KHÔNG** tick "Add a README file" (vì mình đã có sẵn rồi)
5. Click **Create repository**

### Bước 2 — Upload files

**Cách 1 — Upload qua web (dễ nhất, không cần git):**

1. Trong repo vừa tạo, click **"uploading an existing file"** (link xanh giữa trang)
2. Drag & drop **3 file** từ folder `portfolio/`:
   - `index.html`
   - `cv.pdf`
   - `photo.jpg`
   - `README.md`
3. Scroll xuống, click **Commit changes**

**Cách 2 — Dùng git command line:**

```bash
cd path/to/portfolio
git init
git add index.html cv.pdf photo.jpg README.md
git commit -m "Initial portfolio"
git branch -M main
git remote add origin https://github.com/martinnguyen25111989/martinnguyen25111989.github.io.git
git push -u origin main
```

### Bước 3 — Bật GitHub Pages (thường tự bật, nhưng kiểm tra)

1. Vào tab **Settings** của repo
2. Sidebar trái → click **Pages**
3. Source → chọn **Deploy from a branch**
4. Branch → **main** / **/ (root)** → **Save**

### Bước 4 — Chờ 1-2 phút và check URL

Site sẽ live tại: **https://martinnguyen25111989.github.io**

> 💡 Nếu chưa thấy hiện, đợi 2-3 phút rồi refresh. Lần đầu deploy hơi chậm.

---

## 👤 Phần 2: Setup GitHub Profile README

Đây là tính năng đặc biệt — repo có cùng tên với username sẽ hiển thị README ngay trên trang profile của anh (https://github.com/martinnguyen25111989).

### Bước 1 — Tạo repo "profile"

1. Vào https://github.com/new
2. **Repository name:** `martinnguyen25111989` (giống tên username — GitHub sẽ hiện 1 thông báo *"You found a secret!"* → tốt rồi, đúng là cái mình cần)
3. **Public**
4. Tick **"Add a README file"**
5. **Create repository**

### Bước 2 — Edit README.md

1. Trong repo `martinnguyen25111989` vừa tạo, click vào file `README.md`
2. Click icon ✏️ (Edit pencil) ở góc trên phải
3. **Xóa hết nội dung** mặc định
4. Mở file `profile-README.md` mình đã tạo, **copy toàn bộ nội dung**, paste vào
5. Scroll xuống → **Commit changes**

### Bước 3 — Check profile

Vào https://github.com/martinnguyen25111989 → sẽ thấy README hiển thị đẹp đẽ trên đầu trang profile.

---

## 🎨 Tùy chỉnh thêm (optional)

### Đổi màu accent

Trong `index.html`, tìm dòng này (gần đầu phần `<style>`):

```css
--accent: #e8a04b;
```

Đổi sang màu khác nếu thích. Một số gợi ý:
- Emerald: `#0d9488`
- Coral: `#fb7185`
- Electric blue: `#3b82f6`
- Lavender: `#a78bfa`

### Đổi photo

Replace file `photo.jpg` trong repo bằng ảnh khác. Khuyên dùng ảnh **portrait dọc (4:5)**, độ phân giải tối thiểu **600×750px**.

### Thêm LinkedIn

Trong `index.html`, tìm phần Contact section, thêm vào `<ul class="contact-info">`:

```html
<li>
  <span class="label">LinkedIn</span>
  <a href="https://linkedin.com/in/YOUR-PROFILE" class="value" target="_blank" rel="noopener">linkedin.com/in/YOUR-PROFILE</a>
</li>
```

### Cập nhật CV mới

Khi anh update CV, chỉ cần upload file `cv.pdf` mới đè lên file cũ trong repo. Site sẽ tự dùng file mới.

---

## 🌐 Custom domain (optional — nâng cao)

Nếu sau này anh mua domain riêng (ví dụ `tuannguyen.dev`):

1. Trong Settings → Pages → Custom domain → nhập domain
2. Ở nhà cung cấp domain, add bản ghi DNS:
   - `CNAME` trỏ về `martinnguyen25111989.github.io`
3. Đợi propagation (15 phút — vài tiếng)

---

## ❓ Troubleshooting

**Site không hiện sau khi deploy?**
- Đợi 2-5 phút sau lần push đầu tiên
- Check Settings → Pages có thấy URL màu xanh không
- Hard refresh browser (Ctrl+Shift+R)

**Font hiển thị xấu?**
- Đảm bảo có internet (font load từ Google Fonts)
- Check Console (F12) xem có chặn font không

**Photo không hiện?**
- Đảm bảo file tên đúng `photo.jpg` (lowercase, đúng đuôi `.jpg` không phải `.jpeg`)
- Photo cùng folder với `index.html`

---

Có gì hỏi mình hỗ trợ tiếp nhé! 🚀
