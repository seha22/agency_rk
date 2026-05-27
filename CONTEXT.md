# CONTEXT.md - Rumah Ketan Agency Website

> Project: Website Agency "Rumah Ketan"
> Repo: agency_rk
> Started: 2026-05-27

## Vision

Website agency digital yang membantu UMKM dan mid-size business di Indonesia untuk digitalisasi melalui:
- Pembuatan website profesional (Company Profile, E-commerce, Odoo ERP, Omnichannel + Chatwoot)
- Setup Business Automation menggunakan AI Agents

Brand Positioning: **Profesional + Sedikit Warmth** — Ramah untuk UMKM, tapi tetap terlihat kompeten dan modern.

## Scope MVP (v1)

**In Scope:**
- Public website (landing page + beberapa section utama)
- Admin Dashboard + CMS untuk mengelola konten public
- Manajemen Customer
- Manajemen Project (terikat ke Customer)
- Manajemen Service (via CMS)

**Out of Scope (ditunda):**
- Manajemen Codebase & Repository
- Domain & Deployment tracking
- Penyimpanan Credentials
- Multi-tenant atau client portal

## Tech Stack

- **Frontend**: Next.js 15 (App Router) + Tailwind CSS + shadcn/ui
- **Backend**: InsForge (agent-native backend — database, auth, storage, functions)
- **Auth**: InsForge Auth (dengan support role-based)
- **Styling & Components**: Tailwind + shadcn/ui
- **Deployment**: Vercel (frontend) + InsForge (backend)

## Core Domain Concepts (MVP)

### User Roles
- **Owner / Admin**: Full access
- **Team Member**: Developer, Sales, Support (dengan permission berbeda)

### Main Entities

#### Customer
- Nama / Perusahaan
- Kontak (WA / Email)
- Status
- Catatan internal

#### Project
- Terikat ke 1 Customer
- Jenis layanan (dari Service)
- Status pipeline (Inquiry → Proposal → On Progress → Delivered → Maintenance)
- Catatan & timeline

#### Service
- Dikelola sepenuhnya via CMS (nama, deskripsi, harga dasar, dll)

## Public Site Structure (MVP)

1. Home / Hero
2. Layanan (Services)
3. Cara Kerja / Proses
4. Portfolio / Studi Kasus
5. Testimoni
6. Tentang Kami
7. Kontak / Mulai Project

## Design Direction

Mix antara **profesional** dan **sedikit warmth**:
- Clean, modern, mudah dibaca
- Warna hangat (terinspirasi "Ketan" — golden/earth tone) dikombinasikan dengan profesional blue/gray
- Typography yang ramah tapi tajam
- Fokus pada kepercayaan dan kemudahan bagi UMKM

## Next Decisions Needed

- Detail data model & fields
- Struktur halaman Admin Dashboard
- Authentication & Authorization flow
- CMS implementation approach di Next.js + InsForge
- Folder structure & component architecture
