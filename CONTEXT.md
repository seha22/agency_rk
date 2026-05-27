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

#### User
- id, name, email, role (`owner` | `admin` | `developer` | `sales` | `support`)

#### Customer
- id, company_name, contact_person, whatsapp, email, status (`active` | `inactive` | `lead`), notes

#### Project
- id, customer_id, service_id, title, status (`inquiry` | `proposal_sent` | `negotiation` | `in_progress` | `delivered` | `maintenance`), start_date, expected_end_date, notes

#### Service
- id, name, slug, short_description, full_description, base_price, is_active, order

#### Page (CMS)
- id, slug, title, meta_description, is_published

#### Block (CMS)
- id, page_id, block_type, data (JSON), order, is_active

## CMS Approach (MVP)

**Block-based CMS**
- Setiap halaman public bisa terdiri dari beberapa blok yang bisa diedit via Admin
- Blok bersifat reusable dan bisa diatur urutannya
- Blok yang didukung di MVP: hero, services_grid, process_steps, testimonials, portfolio_preview, about_short, cta_banner, contact_form

## Public Site Structure (MVP)

1. Home / Hero
2. Layanan (Services)
3. Cara Kerja / Proses
4. Portfolio / Studi Kasus
5. Testimoni
6. Tentang Kami
7. Kontak / Mulai Project

## Admin Dashboard Structure (MVP)

**Sidebar:**
- Dashboard (Overview)
- Customers
- Projects
- Services (CMS)
- Content / CMS (Block-based page builder)
- Settings (Profile & Team Members)

## Design Direction

Mix antara **profesional** dan **sedikit warmth**:
- Clean, modern, mudah dibaca
- Warna hangat (golden/earth tone) dikombinasikan dengan profesional blue/gray
- Typography yang ramah tapi tajam
- Fokus pada kepercayaan dan kemudahan bagi UMKM

## Folder Structure

```
app/
├── (public)/
│   ├── layout.tsx
│   ├── page.tsx
│   ├── layanan/
│   ├── tentang-kami/
│   └── kontak/
├── (admin)/
│   ├── layout.tsx
│   ├── dashboard/
│   ├── customers/
│   ├── projects/
│   ├── services/
│   ├── content/
│   └── settings/
├── components/
│   ├── ui/
│   ├── blocks/
│   └── admin/
├── lib/
└── types/
```

## Next Decisions Needed

- Schema design di InsForge (tables & relations)
- Authentication & role-based authorization implementation
- Form handling & validation strategy (React Hook Form + Zod)
- Mulai scaffolding project
