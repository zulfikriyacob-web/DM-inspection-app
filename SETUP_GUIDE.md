# 🚀 Setup Guide — Door Mirror Inspection App

Panduan lengkap dari mula sampai app live. Ikut step by step. Tak payah rush.

**Ada 2 bahagian:**
- **Bahagian A — GitHub** (untuk host app, dapat URL) → buat sekarang, WAJIB
- **Bahagian B — Google Sheets** (untuk data storage) → boleh buat kemudian, untuk Phase 3

---

## 📦 File yang Zul ada

| File | Untuk apa | Masuk mana |
|------|-----------|------------|
| `index.html` | App sebenar (Dashboard, Check Sheet, History) | GitHub repo |
| `README.md` | Nota projek | GitHub repo (optional) |
| `Inspection_App_DataSheet_v2.xlsx` | Data master (semua check items, specs, dsb.) | Google Sheets (Bahagian B) |

**Yang WAJIB untuk app jalan sekarang: `index.html` je.**
Excel tu untuk nanti (Phase 3 — bila sambung data live).

---

# BAHAGIAN A — GitHub Setup

> Goal: App Zul live kat internet, boleh akses dari phone.
> Repo Zul dah ada: `door-mirror-inspection-app` ✅

## Step A1 — Upload index.html

1. Buka repo Zul: `https://github.com/zulfikriyacob-web/door-mirror-inspection-app`
2. Pastikan Zul kat tab **Code** (bukan Settings)
3. Klik butang **Add file** (atas kanan) → **Upload files**
4. Buka File Explorer, cari `index.html` (di folder Downloads)
5. **Drag** `index.html` masuk ke browser window
6. Scroll bawah, di kotak "Commit changes":
   - Taip: `Upload inspection app`
7. Klik butang hijau **Commit changes**

✅ File dah masuk repo.

## Step A2 — Activate GitHub Pages

1. Kat repo yang sama, klik tab **Settings** (atas)
2. Sidebar kiri, scroll bawah → klik **Pages**
3. Bahagian "Build and deployment":
   - **Source:** pilih `Deploy from a branch`
   - **Branch:** pilih `main`, folder biar `/ (root)`
   - Klik **Save**
4. Tunggu 1-2 minit, **refresh** page ni

✅ Bila siap, akan nampak mesej:
> Your site is live at **https://zulfikriyacob-web.github.io/door-mirror-inspection-app/**

## Step A3 — Test

1. Buka URL tu di browser (laptop atau phone)
2. App Zul dah jalan! 🎉

**Bonus (phone):** Buka URL kat Chrome/Safari phone → menu → **Add to Home Screen**.
Lepas tu app jadi macam real app icon, tap terus buka full-screen.

## Step A4 — Cara UPDATE app nanti (bila ada perubahan)

Setiap kali Zul (atau saya) buat perubahan pada `index.html`:

1. Repo → **Add file** → **Upload files**
2. Drag `index.html` versi baru
3. Commit message: (contoh) `Update dashboard`
4. **Commit changes**
5. Tunggu 1-2 minit → refresh live URL → dah update

> GitHub auto-replace file lama dengan yang baru sebab nama sama.

---

# BAHAGIAN B — Google Sheets Setup

> Goal: Sediakan "database" untuk app baca data.
> **Buat bahagian ni bila dah ready untuk Phase 3.** Untuk sekarang, app guna mock data
> (data contoh yang dah built-in), jadi boleh test dulu tanpa Google Sheets.

## Step B1 — Upload Excel ke Google Drive

1. Buka `https://drive.google.com` (login guna Google account Zul)
2. Klik **+ New** → **File upload**
3. Pilih `Inspection_App_DataSheet_v2.xlsx`
4. Tunggu upload siap

## Step B2 — Convert jadi Google Sheets

1. Dalam Google Drive, **double-click** file yang baru upload tu
2. Kat atas, klik **Open with** → **Google Sheets**
3. Bila dah buka, klik **File** → **Save as Google Sheets**
4. Sekarang ada versi Google Sheets (format asal Excel boleh delete kalau nak)

✅ Data Zul dah dalam Google Sheets, ada 10 tabs (README, Templates, Processes, dsb.)

## Step B3 — Dapatkan Spreadsheet ID

1. Tengok URL Google Sheets Zul, format dia macam ni:
   ```
   https://docs.google.com/spreadsheets/d/AbC123XyZ.../edit
                                          ^^^^^^^^^^^^
                                          ini Spreadsheet ID
   ```
2. Copy bahagian ID tu (antara `/d/` dan `/edit`)
3. Simpan — nanti kita guna masa Phase 3

## Step B4 — Set sharing (nanti masa Phase 3)

Kita akan setup ni sama-sama bila mula Phase 3. Involve:
- Enable Google Sheets API
- Set permission untuk app baca data
- Sambung `index.html` ke spreadsheet ID

> **JANGAN buat step ni sekarang** — kita buat sama-sama bila mula Phase 3, sebab
> ada beberapa keputusan teknikal yang saya kena guide Zul through.

---

# ✅ Checklist Ringkas

**Sekarang (WAJIB):**
- [ ] A1 — Upload `index.html` ke GitHub
- [ ] A2 — Activate GitHub Pages
- [ ] A3 — Test app di live URL
- [ ] A4 — (faham je) cara update nanti

**Nanti (Phase 3):**
- [ ] B1 — Upload Excel ke Drive
- [ ] B2 — Convert jadi Google Sheets
- [ ] B3 — Copy Spreadsheet ID
- [ ] B4 — Setup API + sambung app (buat sama-sama dengan Claude)

---

# 🆘 Kalau Stuck

Screenshot mana yang stuck, hantar kat Claude. Bagitau:
1. Step mana (contoh: "A2")
2. Apa Zul nampak kat screen
3. Apa yang tak jadi

Kita debug sama-sama. Take your time — takde rush! 😎
