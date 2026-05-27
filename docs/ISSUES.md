# Implementation Issues (to-issues)

> Dipecah menggunakan pendekatan vertical slices berdasarkan PRD dan CONTEXT.md

## Milestone: Rumah Ketan MVP

### Phase 1: Foundation

#### Issue #1: Project Setup & Infrastructure
**Title:** [Setup] Initialize Next.js 15 + InsForge Integration
**Labels:** `setup`, `infrastructure`

**Description:**
Setup proyek Next.js 15 dengan App Router, Tailwind, shadcn/ui, dan integrasi dasar dengan InsForge.

**Acceptance Criteria:**
- [ ] Next.js 15 project berhasil diinisialisasi
- [ ] Tailwind CSS + shadcn/ui terinstall
- [ ] InsForge client & environment variables dikonfigurasi
- [ ] Folder structure sesuai CONTEXT.md sudah dibuat
- [ ] README diperbarui

---

#### Issue #2: Authentication & Role System
**Title:** [Auth] Implement Authentication + Role-based Access Control
**Labels:** `feature`, `auth`

**Description:**
Implementasi sistem autentikasi dan role-based access control menggunakan InsForge Auth.

**Acceptance Criteria:**
- [ ] User bisa register & login
- [ ] Role-based access (`owner`, `admin`, `developer`, `sales`, `support`) berfungsi
- [ ] Protected routes untuk admin dashboard
- [ ] Middleware auth berjalan

---

### Phase 2: Core Features

#### Issue #3: Customer Management
**Title:** [Feature] Customer Management (CRUD)
**Labels:** `feature`, `admin`

**Description:**
Membuat fitur manajemen customer di Admin Dashboard.

**Acceptance Criteria:**
- [ ] Halaman daftar customer
- [ ] Form tambah & edit customer
- [ ] Delete customer
- [ ] Status customer (active/lead/inactive)

---

#### Issue #4: Project Management
**Title:** [Feature] Project Management (CRUD + Pipeline)
**Labels:** `feature`, `admin`

**Description:**
Membuat fitur manajemen project beserta status pipeline.

**Acceptance Criteria:**
- [ ] Project terhubung dengan Customer
- [ ] Project terhubung dengan Service
- [ ] Status pipeline (inquiry → delivered)
- [ ] CRUD project lengkap

---

#### Issue #5: Service Management (CMS)
**Title:** [CMS] Service Management
**Labels:** `feature`, `cms`

**Description:**
Membuat fitur CRUD Service yang dikelola via Admin.

**Acceptance Criteria:**
- [ ] CRUD Service
- [ ] Service bisa ditampilkan di public site

---

### Phase 3: Block-based CMS

#### Issue #6: Block-based CMS Core
**Title:** [CMS] Block-based Content Management System
**Labels:** `feature`, `cms`, `complex`

**Description:**
Membangun sistem Block-based CMS (Page + Block dengan JSON data).

**Acceptance Criteria:**
- [ ] Model Page & Block di InsForge
- [ ] Admin bisa menambah, edit, hapus, dan mengatur urutan blok
- [ ] Blok bisa dirender di public site

---

#### Issue #7: Public Site + Dynamic Blocks
**Title:** [Public] Build Public Site with Dynamic Blocks
**Labels:** `feature`, `public`

**Description:**
Membangun halaman public yang mengambil konten dari Block-based CMS.

**Acceptance Criteria:**
- [ ] Halaman utama (Home) bisa dirender dari blok
- [ ] Beberapa blok dasar sudah dibuat (Hero, Services, Testimonials, dll)
- [ ] Responsive design

---

### Phase 4: Polish & Deployment

#### Issue #8: Admin Dashboard UI Polish
**Title:** [UI] Admin Dashboard Interface
**Labels:** `ui`, `admin`

**Description:**
Mempercantik dan memoles tampilan Admin Dashboard.

**Acceptance Criteria:**
- [ ] Sidebar navigation
- [ ] Table & form yang rapi
- [ ] Loading & empty state

---

#### Issue #9: Deployment
**Title:** [Deploy] Deploy to Vercel + InsForge
**Labels:** `deployment`

**Description:**
Melakukan deployment production.

**Acceptance Criteria:**
- [ ] Frontend berhasil di-deploy ke Vercel
- [ ] Backend InsForge production ready
- [ ] Environment variables production dikonfigurasi

---

## Catatan

- Issues dipecah secara **vertical** (bisa dikerjakan end-to-end)
- Urutan pengerjaan disarankan dari Phase 1 → Phase 4
- Setiap issue bisa dikerjakan secara independen setelah foundation selesai
