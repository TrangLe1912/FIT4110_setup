# Smart Campus · Buổi 1 · Student Setup Repo

Repo này dành **chỉ cho sinh viên** trong Buổi 1 của học phần **Dịch vụ kết nối và Công nghệ nền tảng**.

Mục tiêu của Buổi 1 là đưa máy cá nhân của sinh viên về trạng thái sẵn sàng:

- Có Git, Docker, Docker Compose, Node.js, Python/Miniconda.
- Chạy được container cơ bản.
- Pull trước các Docker image dùng trong học phần.
- Chạy được smoke test.
- Tạo được minh chứng học tập trong thư mục `evidence/buoi-01/`.

> Repo này **không chứa file Word/PDF gốc**. Thư mục `docs/` chỉ chứa Markdown dành cho sinh viên.

---

## 1. Cách dùng nhanh

### macOS / Linux

```bash
git clone <URL_REPO_CUA_LOP>
cd smart-campus-session01-student
chmod +x scripts/*.sh
./scripts/pull_all.sh
./scripts/smoke_test.sh
./scripts/collect_session01_evidence.sh
```

Sau đó nộp minh chứng:

```bash
git add evidence/buoi-01
git commit -m "Add session 01 setup evidence"
git push
```

### Windows PowerShell

Mở PowerShell tại thư mục repo, chạy:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\scripts\pull_all.ps1
.\scripts\smoke_test.ps1
.\scripts\collect_session01_evidence.ps1
```

Sau đó nộp minh chứng:

```powershell
git add evidence/buoi-01
git commit -m "Add session 01 setup evidence"
git push
```

---

## 2. Minh chứng cần có sau Buổi 1

Sau khi chạy script, thư mục `evidence/buoi-01/` cần có các file:

```text
evidence/buoi-01/
  README.md
  checklist.md
  known-issues.md
  tool-versions.txt
  docker-version.txt
  compose-version.txt
  hello-world.txt
  smoke-test-result.txt
  image-list.txt
  git-log.txt
```

Giảng viên/nhóm khác có thể kiểm tra lại bằng cách clone repo và đọc các log này.

---

## 3. Cấu trúc repo

```text
.
├── README.md
├── docs/
│   ├── docker-quickstart.md
│   ├── miniconda-setup.md
│   ├── quick-reference.md
│   └── troubleshooting.md
├── scripts/
│   ├── pull_all.sh
│   ├── pull_all.ps1
│   ├── smoke_test.sh
│   ├── smoke_test.ps1
│   ├── collect_session01_evidence.sh
│   └── collect_session01_evidence.ps1
├── compose/
│   └── docker-compose.smoke.yml
├── evidence/
│   └── buoi-01/
│       ├── README.md
│       ├── checklist.md
│       └── known-issues.md
├── requirements.txt
├── environment.yml
├── package.json
└── .github/workflows/check-repo.yml
```

---

## 4. Quy ước branch khi nộp bài

Mỗi sinh viên hoặc nhóm tạo branch theo mẫu:

```text
feat/s1-setup-<ten-nhom-hoac-ma-sv>
```

Ví dụ:

```bash
git checkout -b feat/s1-setup-team-iot
```

---

## 5. Tiêu chí hoàn thành Buổi 1

Sinh viên được xem là sẵn sàng khi:

- `docker run --rm hello-world` chạy OK.
- `docker compose version` chạy OK.
- `scripts/smoke_test` không có lỗi nghiêm trọng.
- Có ít nhất một commit chứa minh chứng Buổi 1.
- Nếu có lỗi chưa sửa được, ghi rõ vào `evidence/buoi-01/known-issues.md`.

