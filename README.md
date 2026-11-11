# ⚡ n8n Workflow: Customer Application Data Parser (SPJBTL)

Automated n8n workflow designed to parse, normalize, and extract bulk customer service request data (such as new connection and power upgrade requests) for regional utility distribution units.

---

## 📌 Problem Statement
Raw incoming customer application data (SPJBTL) often arrives in unstructured batch arrays containing multiple service types (e.g., `Pasang Baru`, `Tambah Daya`). Processing these manually slows down administrative approval and data routing.

## 💡 Solution & Features
This n8n workflow automates the data transformation pipeline:
- **Bulk Item Processing:** Handles multi-item input payloads seamlessly using optimized JavaScript logic.
- **Data Normalization:** Maps request attributes like `no_agenda`, `id_pelanggan`, `daya_va`, `tarif`, and unit targets (`ULP Simulasi A/B`).
- **Date Tracking:** Retains payment (`tgl_bayar`) and signing dates (`tgl_ttd_spjbtl`) for audit logging.

---

## 🛠️ Built With
- **[n8n](https://n8n.io/)** (Cloud / Self-Hosted)
- **JavaScript (ES6+)** for custom data mapping node

---

## 📊 Sample Data Schema

**Input Item Example:**
```json
{
  "no_agenda": "AGD-26110001",
  "id_pelanggan": "990000000101",
  "nama": "Toko Sinar Jaya",
  "layanan": "Pasang Baru",
  "daya_va": 3500,
  "tarif": "B-1",
  "unit": "ULP Simulasi A",
  "tgl_bayar": "2026-11-02",
  "tgl_ttd_spjbtl": "2026-11-03"
}
