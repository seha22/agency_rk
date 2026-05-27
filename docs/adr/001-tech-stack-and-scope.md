# ADR-001: Tech Stack and MVP Scope

**Date:** 2026-05-27
**Status:** Accepted

## Context

Kita ingin membangun website agency "Rumah Ketan" yang memiliki public site + admin dashboard dengan CMS dan manajemen customer/project. Project ini akan dikembangkan dengan bantuan AI coding agent secara intensif.

## Decision

### Tech Stack
- **Frontend**: Next.js 15 (App Router) + Tailwind CSS + shadcn/ui
- **Backend & Infrastructure**: InsForge (agent-native backend platform)
  - Database
  - Authentication (dengan role support)
  - Storage
  - Serverless functions
- **Deployment**: Vercel (frontend) + InsForge (backend)

### MVP Scope
Kita memilih **Opsi B**:
- Public website
- Block-based CMS untuk mengelola konten public
- Admin Dashboard untuk:
  - Manajemen Customer
  - Manajemen Project
  - Manajemen Service (via CMS)

**Ditolak / Ditunda:**
- Credentials management
- Codebase & deployment tracking
- Client self-service portal

## Consequences

**Positif:**
- InsForge sangat cocok dengan workflow AI-assisted development
- Next.js 15 memberikan developer experience yang excellent + App Router
- Block-based CMS memberikan fleksibilitas tanpa terlalu kompleks di MVP
- Scope terkendali sehingga bisa selesai dalam waktu wajar

**Negatif / Risiko:**
- InsForge masih relatif baru (perlu evaluasi kestabilan & dokumentasi)
- Block-based CMS membutuhkan desain data model yang baik sejak awal
- Role-based access control harus diimplementasikan dengan hati-hati

## Related Decisions
- Lihat CONTEXT.md untuk domain model dan struktur halaman
