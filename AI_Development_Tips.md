# Step-by-step Development App (Prompt-driven) dengan AI

> Tujuan: bikin aplikasi dari nol sampai siap dipakai dengan cara “AI sebagai pair programmer”, tapi tetap rapi, terukur, dan gampang di-maintain.

---

## 1) Definisikan outcome & scope (anti melebar)
**Output yang harus jelas:**
- Masalah apa yang diselesaikan
- User utama siapa
- 3–5 fitur wajib (MVP)
- Non-goals (yang sengaja tidak dibuat dulu)

**Prompt ke AI:**
> “Saya mau bikin aplikasi **[jenis aplikasi]** untuk **[target user]**. MVP fitur wajib: **[...]**. Non-goals: **[...]**. Tolong tulis scope 1 halaman: objective, user story, acceptance criteria, dan constraint teknis.”

---

## 2) Buat PRD mini + user flow
Bikin dokumen pendek supaya arah tidak berubah-ubah:
- User stories
- User flow (happy path + edge cases)
- Data apa yang dibutuhkan
- Error states & empty states

**Prompt ke AI:**
> “Dari scope ini, buat **Mini PRD**: user stories (format ‘As a… I want… so that…’), user flow langkah demi langkah, edge cases penting, dan acceptance criteria per fitur.”

---

## 3) Tentukan arsitektur & tech stack (sesuai skill & deadline)
Pilih stack yang kamu kuat dan cepat shipping.
- Frontend: React/Next/Vue
- Backend: Node/Go/Laravel
- DB: Postgres/MySQL
- Auth: JWT/OAuth
- Hosting: VPS/Cloud

**Prompt ke AI:**
> “Dengan deadline **[X hari]** dan skill saya **[stack]**, rekomendasikan arsitektur sederhana: modul, layer, folder structure, dan alasan trade-off.”

---

## 4) Desain data model + API contract dulu (biar coding nggak bolak-balik)
- ERD / tabel inti
- Relasi & index
- API endpoints + request/response contoh
- Status code & error format

**Prompt ke AI:**
> “Buat data model untuk fitur **[...]**: tabel, kolom, tipe data, relasi, index. Lalu buat API contract (endpoint, payload, response contoh, error).”

---

## 5) Setup repo & standar engineering (biar scalable sejak awal)
Wajib:
- `.env.example`
- lint/format
- pre-commit (optional)
- logging & config loader
- basic CI (test + lint)

**Prompt ke AI:**
> “Buat checklist setup repo untuk **[stack]**: env, config, lint, format, test, CI minimal. Sertakan contoh struktur folder.”

---

## 6) Generate UI skeleton + component plan (kalau ada frontend)
- Wireframe sederhana
- Daftar halaman
- Component breakdown
- State management approach

**Prompt ke AI:**
> “Dari user flow, buat daftar halaman + komponen. Untuk tiap halaman: state yang dibutuhkan, loading/empty/error state, dan rencana integrasi API.”

---

## 7) Implementasi iteratif per fitur (vertical slice)
Kerjain fitur end-to-end per slice:
1 slice = UI → API → DB → test → polish

Contoh urutan:
1. Auth
2. CRUD utama
3. Search/filter
4. Analytics/logging

**Prompt ke AI:**
> “Buat rencana implementasi model ‘vertical slice’ untuk MVP ini. Urutkan prioritas, estimasi effort, dan risiko per slice.”

---

## 8) Testing strategy (minimal tapi efektif)
Minimal yang penting:
- Unit test untuk business logic
- Integration test untuk endpoint penting
- E2E test 1–2 happy path (kalau sempat)

**Prompt ke AI:**
> “Untuk stack **[stack]**, rekomendasikan testing pyramid dan tulis test case prioritas untuk fitur **[...]** (happy path + edge).”

---

## 9) Security & quality gate (yang sering kelupaan)
Checklist cepat:
- Validasi input (server-side)
- Rate limit basic
- Sanitasi output (XSS)
- AuthZ (role/permission)
- Secrets jangan masuk git

**Prompt ke AI:**
> “Review rancangan API saya ini untuk security: apa celah umum, validasi yang wajib, dan perbaikan cepat yang bisa saya lakukan.”

---

## 10) Observability & debugging (biar gampang maintain)
- Structured logging
- Error tracking (opsional)
- Metrics basic (latency/error rate)
- Request ID

**Prompt ke AI:**
> “Tambahkan observability minimal untuk **[stack]**: format log, middleware logging, error handler, dan contoh output log yang baik.”

---

## 11) Deploy pipeline (dev → staging → prod)
- Docker (jika cocok)
- Migration run otomatis
- Health check endpoint
- Rollback plan sederhana

**Prompt ke AI:**
> “Buat langkah deploy untuk **[stack]** ke **[platform]**: env vars, build, migrate, start, healthcheck, dan rollback.”

---

## 12) Dokumentasi & handover
Minimal docs:
- Cara run lokal
- Env var
- API docs (ringkas)
- Known limitations
- Next improvements

**Prompt ke AI:**
> “Buat README ringkas untuk project ini: setup, run, test, env vars, endpoint list, dan catatan limitasi.”

---

# Template Prompt Utama (copy-paste)
Gunakan ini supaya AI konsisten:

## Context
Saya sedang bikin aplikasi: **[deskripsi singkat]**  
Target user: **[...]**  
MVP fitur: **[...]**  
Constraint: **deadline, stack, platform, aturan]**

## Task
Tolong hasilkan: **[output yang kamu mau: PRD / ERD / endpoint / code / test]**

## Rules
- Jawaban harus praktis dan bisa langsung dipakai.
- Kalau ada asumsi, tulis asumsi.
- Fokus MVP, jangan over-engineering.

---

# Tips workflow AI biar cepat
- Selalu minta AI bikin “plan + checklist” dulu, baru minta code per modul.
- Setelah AI kasih code, minta AI bikin “review”: bug potensial, edge case, security.
- Simpan keputusan teknis dalam `docs/decisions.md` biar nggak lupa.
