# Product Requirements Document (PRD)

**Project:** Rumah Ketan — Agency Website & Internal Dashboard
**Version:** 1.0 (MVP)
**Date:** 2026-05-27
**Status:** Draft

---

## 1. Overview

**Rumah Ketan** adalah agency digital yang membantu UMKM dan bisnis menengah di Indonesia melakukan digitalisasi melalui pembuatan website profesional serta setup business automation menggunakan AI Agents.

Website ini akan menjadi **platform utama** agency yang terdiri dari dua bagian utama:
- **Public Site**: Website landing page yang profesional namun hangat.
- **Admin Dashboard**: Sistem internal untuk mengelola konten, customer, dan project.

## 2. Vision & Goals

### Vision
Menjadi agency digital pilihan utama bagi UMKM Indonesia yang ingin naik kelas secara digital dengan pendekatan yang ramah, profesional, dan modern.

### Goals (MVP)
- Meningkatkan kredibilitas dan konversi calon klien.
- Mempercepat operasional internal agency.
- Memberikan kemampuan mengubah konten website tanpa perlu developer (melalui CMS).

### Success Metrics (MVP)
- Website bisa diakses publik
- Admin dapat melakukan CRUD Customer & Project
- Admin dapat mengelola konten public melalui Block-based CMS
- Minimal bisa mengelola 1–2 project secara end-to-end di sistem

## 3. Target Users

### Primary Users
- **Owner / Founder** (full access)
- **Team Members**: Sales, Developer, Support

### Secondary Users (Future)
- Calon klien (hanya melihat public site)

## 4. Scope

### In Scope (MVP)

**Public Website**
- Hero section
- Layanan (Services)
- Cara Kerja
- Portfolio / Studi Kasus
- Testimoni
- Tentang Kami
- Kontak

**Admin Dashboard**
- Overview Dashboard
- Manajemen Customer
- Manajemen Project
- Manajemen Service (via CMS)
- Block-based CMS untuk mengelola konten public
- Manajemen Team Members (basic)

**Core Features**
- Authentication & Role-based Access Control
- CRUD Customer
- CRUD Project (terkait Customer & Service)
- Block-based Content Management System
- Responsive design

### Out of Scope (MVP)
- Credentials & secret management
- Codebase & repository tracking
- Deployment & domain management
- Client self-service portal
- Payment integration
- Advanced reporting & analytics

## 5. Data Model (MVP)

### User
- id, name, email, role (owner, admin, developer, sales, support)

### Customer
- id, company_name, contact_person, whatsapp, email, status, notes

### Project
- id, customer_id, service_id, title, status, start_date, expected_end_date, notes

### Service
- id, name, slug, short_description, full_description, base_price, is_active, order

### Page (CMS)
- id, slug, title, meta_description, is_published

### Block (CMS)
- id, page_id, block_type, data (JSON), order, is_active

## 6. Block Types (CMS)

Blok yang didukung di MVP:
- hero
- services_grid
- process_steps
- testimonials
- portfolio_preview
- about_short
- cta_banner
- contact_form

## 7. Technical Approach

- Frontend: Next.js 15 (App Router) + Tailwind CSS + shadcn/ui
- Backend: InsForge (Database, Auth, Storage, Functions)
- Auth: InsForge Auth dengan role-based access
- Validation: Zod + React Hook Form
- Deployment: Vercel (frontend) + InsForge (backend)

## 8. Design Direction

**Positioning**: Profesional + Sedikit Warmth
- Clean dan modern
- Warna hangat (golden/earth tone) + profesional blue/gray
- Typography yang ramah namun tajam
- Fokus pada kepercayaan dan kemudahan bagi UMKM

## 9. User Roles & Permissions (MVP)

| Role      | Access Level     | Description                     |
|-----------|------------------|---------------------------------|
| Owner     | Full access      | Pemilik agency                  |
| Admin     | High access      | Bisa manage hampir semua        |
| Developer | Project + Content| Fokus development & konten      |
| Sales     | Customer + Project | Fokus sales pipeline          |
| Support   | View only        | Fokus support & maintenance     |

## 10. Open Questions & Risks

- Implementasi Block-based CMS di Next.js + InsForge
- Kestabilan InsForge untuk production
- Jumlah custom component per block type
- Strategi seed data

## 11. Next Steps

1. Finalisasi schema InsForge
2. Setup project (Next.js + InsForge)
3. Implementasi Authentication & Role system
4. Bangun Block-based CMS
5. Implementasi Customer & Project management
6. Bangun Public Site + integrasi CMS
7. Testing & Deployment

---

*Dibuat berdasarkan hasil grilling session menggunakan grill-with-docs.*