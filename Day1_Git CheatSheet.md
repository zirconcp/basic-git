97% of storage used … If you run out of space, you can't save to Drive or use Gmail. Get 100 GB of storage for THB 70 THB 17/month for 2 months.
# 📘 Git Cheat Sheet ภาษาไทย
> สรุปคำสั่งพื้นฐานที่ใช้บ่อยในโปรเจกต์จริง เหมาะสำหรับมือใหม่และผู้ใช้ระดับกลาง

---

## 🧱 1. การตั้งค่าและข้อมูลระบบ (System Info & Setup)

| คำสั่ง | คำอธิบาย |
|--------|-----------|
| `git --version` | ตรวจสอบเวอร์ชันของ Git |
| `git config --global user.name "ชื่อ"` | ตั้งชื่อผู้ใช้สำหรับ commit |
| `git config --global user.email "อีเมล"` | ตั้งอีเมลผู้ใช้สำหรับ commit |
| `git config --list` | ตรวจสอบการตั้งค่า Git ปัจจุบัน |

---

## 📁 2. เริ่มโปรเจกต์ (Initialize/Clone Repository)

| คำสั่ง | คำอธิบาย |
|--------|-----------|
| `git init` | สร้าง repository ใหม่ในโฟลเดอร์ปัจจุบัน |
| `git clone <url>` | คัดลอก repository จาก remote |
| `git clone --depth 1 <url>` | คัดลอกแบบตื้นสำหรับโปรเจกต์ใหญ่ (เร็วขึ้น) |

---

## 📋 3. ตรวจสอบสถานะและประวัติ (Status & Inspect)

| คำสั่ง | คำอธิบาย |
|--------|-----------|
| `git status` | ดูสถานะไฟล์ที่เปลี่ยนแปลง |
| `git diff` | ดูรายละเอียดการเปลี่ยนแปลงในไฟล์ |
| `git log --oneline --graph --decorate --all` | ดูประวัติ commit แบบย่อ พร้อมกราฟและ branch |
| `git show <commit>` | แสดงรายละเอียดของ commit ที่ระบุ |

---

## ➕ 4. เพิ่มไฟล์และ Commit (Staging & Commit)

| คำสั่ง | คำอธิบาย |
|--------|-----------|
| `git add <file>` | เพิ่มไฟล์เข้าสู่ staging area |
| `git add .` | เพิ่มไฟล์ทั้งหมดเข้าสู่ staging area |
| `git commit -m "ข้อความ"` | สร้าง commit พร้อมข้อความ |
| `git commit -am "ข้อความ"` | เพิ่มและ commit ไฟล์ที่เคยถูก track แล้ว |
| `git commit --amend` | แก้ไข commit ล่าสุด (ข้อความ/ไฟล์) |

---

## 🌍 5. เชื่อมต่อและจัดการ Remote (Remotes)

| คำสั่ง | คำอธิบาย |
|--------|-----------|
| `git remote -v` | แสดงรายการ remote ทั้งหมด |
| `git remote add origin <url>` | เชื่อมต่อ repository กับ remote |
| `git push -u origin main` | ส่ง commit ขึ้น remote ครั้งแรกและตั้ง upstream |
| `git fetch --all --prune` | ดึงข้อมูลทุก remote และลบ branch ที่ถูกลบออกจาก remote |
| `git pull` | ดึงและรวมข้อมูลจาก remote มายัง branch ปัจจุบัน |

---

## 🌿 6. จัดการ Branch (Branching & Merging)

| คำสั่ง | คำอธิบาย |
|--------|-----------|
| `git branch` | แสดงรายชื่อ branch ทั้งหมด |
| `git branch <ชื่อ>` | สร้าง branch ใหม่ |
| `git switch <ชื่อ>` | สลับไป branch ที่มีอยู่ |
| `git switch -c <ชื่อ>` | สร้างและสลับไป branch ใหม่ |
| `git merge <ชื่อ>` | รวม branch ที่ระบุเข้ากับ branch ปัจจุบัน |
| `git branch -d <ชื่อ>` | ลบ branch ที่ merge แล้ว |

---

## 🔄 7. ย้อนกลับและแก้ไขการเปลี่ยนแปลง (Undo/Repair)

| คำสั่ง | คำอธิบาย |
|--------|-----------|
| `git restore <file>` | คืนไฟล์ให้เหมือน commit ล่าสุด |
| `git restore --staged <file>` | นำไฟล์ออกจาก staging area |
| `git reset --hard HEAD` | ย้อนกลับทุกอย่างไป commit ล่าสุด (ล้างการเปลี่ยนแปลงทั้งหมด) |
| `git reset --hard <commit>` | ย้อนกลับไป commit ที่ระบุ (ระวังข้อมูลหาย) |
| `git revert <commit>` | ย้อนการเปลี่ยนแปลงด้วยการสร้าง commit ใหม่ (ปลอดภัย) |

---

## ⚡ 8. ซิงค์โปรเจกต์ (Sync)

| คำสั่ง | คำอธิบาย |
|--------|-----------|
| `git fetch` | ดึงข้อมูลล่าสุดจาก remote โดยไม่รวมเข้ามา |
| `git pull origin main` | ดึงและรวมข้อมูลจาก remote สาขา main |
| `git pull --rebase` | ดึงข้อมูลและเรียง commit ใหม่ให้เป็นเส้นตรง |
| `git push origin main` | ส่ง commit ขึ้น remote สาขา main |

---

## 🧰 9. เก็บงานชั่วคราวและ Tag (Stash & Tags)

| คำสั่ง | คำอธิบาย |
|--------|-----------|
| `git stash` | เก็บงานที่ยังไม่ commit ชั่วคราว |
| `git stash list` | แสดงรายการงานที่ stash ไว้ |
| `git stash pop` | ดึงงานที่ stash กลับมาและลบออกจากรายการ |
| `git tag <เวอร์ชัน>` | สร้าง tag สำหรับ release (เช่น `v1.0.0`) |
| `git push origin --tags` | ส่ง tag ทั้งหมดขึ้น remote |

---

## 💡 10. ตัวอย่าง Workflow พื้นฐาน

```bash
# เริ่มโปรเจกต์ใหม่
git init
git add .
git commit -m "Initial commit"
git branch -M main

# เชื่อมต่อ remote และ push ครั้งแรก
git remote add origin https://github.com/iamsamitdev/myproject.git
git push -u origin main

# สร้างฟีเจอร์ใหม่ใน branch แยก
git switch -c feature/login
# แก้โค้ดและบันทึกการเปลี่ยนแปลง
git add .
git commit -m "Implement login UI"

# รวมงานกลับไป main
git switch main
git pull --rebase
git merge feature/login
git push
```
---
## 💡 11. Workflow สำหรับทำงานเป็นทีม (Git)

#### 11.1 เลือกกลยุทธ์ Branching ที่เหมาะกับทีม
- Trunk-Based Development (แนะนำสำหรับทีมเล็ก-กลาง, release บ่อย)
	- ทำงานที่ `main` เป็นหลัก สร้าง branch ย่อยสั้น ๆ `feature/*`
	- เปิด PR ขนาดเล็ก ตรวจเร็ว merge ด้วย squash เพื่อให้ประวัติอ่านง่าย
	- ใช้ feature flags เปิด/ปิดฟีเจอร์ แทนการถือ branch นาน ๆ
- GitHub Flow (ง่าย เหมาะกับ web/app)
	- แตก `feature/*` → PR → Review → CI ผ่าน → merge เข้า `main` → auto-deploy
- GitFlow (ทีมใหญ่/ซับซ้อน มี release cycle ชัดเจน)
	- ใช้ `develop`, `release/*`, `hotfix/*` แต่มีโอเวอร์เฮดมากกว่า 2 แบบแรก
	- ในบริบท CI/CD สมัยใหม่ แนะนำเริ่มจาก Trunk‑Based หรือ GitHub Flow ก่อน

---

#### 11.2 กฎ Branch Protection & PR
- เปิด Protected Branch สำหรับ `main` (และ `release/*` ถ้ามี)
- ต้องผ่าน CI ทุกครั้ง (status checks) และห้าม force push
- บังคับ code review ≥ 1–2 คน และปิด self‑approval หากทีมกำหนด
- บังคับ linear history + squash merge (อ่าน log และ revert ง่าย)
- ตั้ง `CODEOWNERS` ให้รีวิวตามโฟลเดอร์/โมดูลอัตโนมัติ
	```
	# CODEOWNERS
	src/auth/** @team-security
	src/api/**  @team-backend
	docs/**     @team-docs
	```
- เปิด Draft PR ให้ทีมเห็นงานเร็ว ลด conflict และช่วย early feedback

---

#### 11.3 สื่อสารผ่าน Commit/PR ให้เครื่องมืออัตโนมัติ "เข้าใจ"
- ใช้ Conventional Commits เพื่อช่วย release automation / changelog
	```
	feat: เพิ่ม endpoint /orders
	fix: แก้ null pointer ใน service A
	docs: อัปเดต README การตั้งค่า env
	refactor: แยก business logic ออกจาก service
	test: เพิ่ม unit test ให้ payment
	chore: อัปเดต dependency
	```
- ขยายผล: ใช้ semantic‑release ทำ auto changelog และ version bump
- เขียน PR message สั้น กระชับ มี What/Why/How/Test/Evidence + ลิงก์ issue

---

#### 11.4 คุณภาพโค้ดก่อนเข้า main
- เปิด pre‑commit hooks (lint, format, unit test บางส่วน) ด้วย `pre-commit` หรือ `husky`
- ตั้ง Required checks: Lint, Unit Test, Security Scan (SAST) ให้ผ่านก่อน merge
- เก็บ coverage report เป็น artifact และตั้ง threshold ขั้นต่ำใน CI
- ใช้ feature flags/config by env แทนการถือ branch ยาว ๆ เพื่อลด drift

---

#### 11.5 การ Tag/Release & Changelog
- ใช้ SemVer: `MAJOR.MINOR.PATCH` (เช่น `v1.4.2`)
- Tag จาก `main` ที่ผ่านทุก checks แล้ว → สร้าง GitHub Release/Artifacts/Images
- ทำ auto changelog จาก Conventional Commits (เช่นผ่าน semantic‑release)
	```bash
	git tag -a v1.4.2 -m "Release v1.4.2"
	git push origin v1.4.2
	```

---

#### 11.6 ความปลอดภัย (Security)
- ห้าม commit ความลับ (secrets/keys) → ใช้ `.gitignore` ให้ครบ และสแกนด้วย gitleaks/trufflehog
- เก็บ secrets ใน Jenkins Credentials, Vault หรือ Secret Manager ของคลาวด์
- เปิด commit signing (GPG/SSH) สำหรับผู้ดูแลรีลีส
	```bash
	git config --global user.signingkey <KEYID>
	git config --global commit.gpgsign true
	```

---

#### 11.7 โครงสร้างรีโป (ตัวอย่างที่เข้ากับ CI/CD)
```
.
├─ .github/ or .gitlab/        # workflows / templates / CODEOWNERS
├─ Jenkinsfile                 # pipeline as code (declarative)
├─ docker/
│   └─ app.Dockerfile          # สำหรับ dev/preview
├─ compose.yaml                # สคริปต์ build/test/deploy ที่เรียกจาก Jenkins
├─ scripts/                    # สคริปต์ช่วย build/test/deploy
├─ src/                        # โค้ดแอป
├─ tests/                      # unit/integration tests
├─ .gitignore
├─ package.json | pom.xml | go.mod ...
└─ README.md
```

---

#### 11.8 เชื่อม Git → Jenkins อย่างมีระบบ (สรุปย่อ)
- Multibranch Pipeline: ให้ Jenkins สแกนทุก branch/PR อัตโนมัติจาก `Jenkinsfile`
- Webhook & Triggers: trigger เมื่อ push, PR opened/sync, tag created
- แยกเงื่อนไขใน Jenkinsfile ตามประเภท
	- `feature/*` ⇒ build + test + scan + (preview)
	- `main` ⇒ build + test + scan + build image + push + (staging deploy)
	- tag `v*` ⇒ release pipeline (deploy to prod, publish artifacts)
- Credentials & Secrets: เก็บใน Jenkins Credentials (เช่น `dockerhub-cred`, `kubeconfig`, `ssh-key`)
- Agents: ใช้ Docker agent เพื่อสภาพแวดล้อมคงที่ หรือ Docker‑in‑Docker สำหรับ build image

ตัวอย่าง Jenkinsfile (ย่อ แบบ Declarative):
```groovy
pipeline {
	agent any
	options { timestamps(); skipDefaultCheckout(true) }
	stages {
		stage('Checkout') { steps { checkout scm } }
		stage('Build & Test') {
			steps { sh 'echo run build && echo run tests' }
		}
		stage('Package') {
			when { branch 'main' }
			steps { sh 'echo build image && echo push image' }
		}
		stage('Release') {
			when { expression { env.BRANCH_NAME?.startsWith('v') } }
			steps { sh 'echo publish artifacts' }
		}
	}
}
```

## 🧠 12. Tips & Tricks และ Best Practices

- เขียนข้อความ Commit ให้มีความหมายและสม่ำเสมอ (เช่น Conventional Commits)
	- ตัวอย่าง: `feat(auth): add login UI` / `fix(api): handle 500 on user fetch`
- ใช้ Branch Strategy ที่ชัดเจน: `main`/`develop`/`feature/*` หรือ Trunk-Based + short-lived branches
- จัดประวัติให้อ่านง่ายด้วย Rebase/Squash ก่อน merge
	```bash
	# rebase branch ของเราให้ตาม main ล่าสุด
	git switch feature/login
	git fetch origin
	git rebase origin/main

	# squash commits ระหว่าง merge (บน GitHub/GitLab มีตัวเลือก)
	```
- ตั้ง `.gitignore` และ global ignore ให้เหมาะกับเครื่องและภาษา
	```bash
	# สร้าง global ignore
	git config --global core.excludesfile ~/.gitignore_global
	# เพิ่มรายการที่ไม่ต้องการ track เช่น
	echo node_modules >> ~/.gitignore_global
	echo .DS_Store >> ~/.gitignore_global
	```
- ตั้ง `.gitattributes` เพื่อ normalize line endings และปรับแต่ง diff
	```
	# .gitattributes
	* text=auto eol=lf
	*.lock binary
	*.png binary
	*.jpg binary
	```
- ใช้ Annotated Tags สำหรับ release และระบุข้อความ
	```bash
	git tag -a v1.0.0 -m "Initial release"
	git push origin v1.0.0
	```
- เวลาเผลอลบ branch หรือ commit หาย ใช้ `reflog` เพื่อกู้คืน
	```bash
	git reflog
	# ค้นหา SHA ที่ต้องการย้อนกลับ
	git reset --hard <sha>
	```
- หา commit ที่ทำให้บั๊กเกิดด้วย `git bisect`
	```bash
	git bisect start
	git bisect bad            # สถานะปัจจุบันมีบั๊ก
	git bisect good <sha>     # ระบุ SHA ที่แน่ใจว่าเคยดี
	# ทดสอบแต่ละจุด แล้ว mark ว่า good/bad ไปเรื่อย ๆ จนพบ commit ต้นเหตุ
	git bisect reset
	```
- ปลอดภัยไว้ก่อนเวลาแก้ประวัติ: อย่า rebase/force-push บน branch ที่คนอื่นใช้งานร่วมกันแล้ว
- ตั้งค่า `pull.rebase=true` เพื่อหลีกเลี่ยง merge commit ไม่จำเป็น (ถ้าทีมเห็นพ้อง)
	```bash
	git config --global pull.rebase true
	```
- ปกป้อง branch หลักด้วย Branch Protection Rules (รีวิวก่อน merge, ต้องผ่าน CI, ต้องอัปเดตจาก main)

---

## 📚 แหล่งอ้างอิงแนะนำ
- [Pro Git Book](https://git-scm.com/book/en/v2)
- [GitHub Docs](https://docs.github.com/en/get-started/using-git/about-git)
- [Git Cheat Sheet PDF by GitHub](https://education.github.com/git-cheat-sheet-education.pdf)