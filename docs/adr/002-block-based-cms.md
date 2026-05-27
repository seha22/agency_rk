# ADR-002: Block-based CMS Implementation

**Date:** 2026-05-27
**Status:** Accepted

## Context

Kita membutuhkan CMS yang fleksibel untuk mengelola konten public site tanpa harus hardcode setiap section. Setelah mempertimbangkan beberapa pendekatan, kita memilih block-based CMS.

## Decision

### Approach
Gunakan model **Page + Block** dengan struktur:

- **Page**: `id`, `slug`, `title`, `meta_description`, `is_published`
- **Block**: `id`, `page_id`, `block_type`, `data` (JSON), `order`, `is_active`

Setiap halaman bisa memiliki multiple blok yang bisa diatur urutannya.

### Supported Blocks (MVP)
- `hero`
- `services_grid`
- `process_steps`
- `testimonials`
- `portfolio_preview`
- `about_short`
- `cta_banner`
- `contact_form`

### Implementation Notes
- `data` field menggunakan JSON untuk menyimpan konten spesifik tiap blok
- Blok bersifat reusable antar halaman
- Admin akan memiliki interface untuk menambah, mengedit, menghapus, dan mengatur urutan blok

## Consequences

**Positif:**
- Sangat fleksibel untuk perubahan konten di masa depan
- Cocok dengan kebutuhan agency yang sering update layanan & testimoni
- Relatif sederhana diimplementasikan di MVP

**Negatif / Trade-off:**
- Perlu membuat komponen React untuk setiap `block_type`
- Validasi `data` JSON harus dilakukan dengan hati-hati (menggunakan Zod)
- Performa query bisa menjadi concern jika jumlah blok sangat banyak (bisa dioptimasi nanti)

## Related
- Lihat CONTEXT.md untuk model data lengkap
- Lihat ADR-001 untuk tech stack
