# Session Log — 2026-04-06

## Goal
Build a Quarto-based learning notes website with three sections:
1. AI Tools
2. Thesis research
3. Causal ML book reading notes

## Completed This Session
- Created Quarto project at `~/learning-notes/`
- Configured `_quarto.yml` with navbar, themes, math support
- Built homepage (`index.qmd`) with three-column card layout
- Created listing pages for all three sections
- Written one sample post per section
- Rendered site to `docs/` (7 pages, success)
- Initialized git and committed

## Next Step
- User to create GitHub repo `learning-notes` (Public)
- User to generate new PAT token
- Push and enable GitHub Pages (source: `docs/` folder)

---

# Session Log — 2026-04-06 (continued) + 2026-04-07

## Goal
Taiwan Same-Sex Marriage & Innovation — Synthetic Control research project setup

## Completed

### Website updates (2026-04-06)
- Renamed site to "Muller Chen Blog"
- Added homepage auto-listing for recent posts
- Created About page (anonymous — "Muller")
- Removed 論文 section, removed categories display
- Renamed "Causal ML 筆記" → "Causal Inference and Econometrics"
- Removed three-topic card grid from homepage
- Anonymized all real name mentions across .qmd and .yml files

### Research project setup: Taiwan SSM × Innovation
**Location:** `~/Desktop/NTU_ECON/Course/LaborEcon/SSM_Taiwan_SC/`

**Folder structure created:**
```
SSM_Taiwan_SC/
├── papers/    ← Awad & McCluskey 2024, Trandafir 2014
├── data/raw/  ← all raw data files
├── data/processed/
├── code/      ← 01_prepare_data.R, 02_synthetic_control.R
├── output/figures/ output/tables/
└── notes/     ← data_sources.md
```

**Data downloaded (2026-04-06 ~ 2026-04-07):**

| File | Source | Status |
|------|--------|--------|
| `patent_total_donors.csv` | World Bank API (RESD+NRES) | ✅ |
| `gdp_per_capita.csv` | World Bank API | ✅ |
| `rd_expenditure_pct_gdp.csv` | World Bank API | ✅ |
| `gdp_total.csv` | World Bank API | ✅ |
| `fdi_inflows.csv` | World Bank API | ✅ |
| `taiwan_patents_MANUAL.csv` | TIPO 統計年報 (PDF) | ✅ |
| `taiwan_gdp_pc_IMF.csv` | IMF WEO API | ✅ |
| `taiwan_rd_pct_gdp_MANUAL.csv` | NSTC 科學技術統計要覽 | ⚠️ 需對照官方確認 |

**R scripts written:**
- `01_prepare_data.R` — merges all data into panel, saves `data/processed/panel_2000_2023.csv`
- `02_synthetic_control.R` — runs SC using `tidysynth`, outputs 4 figures + MSPE table

**Data sources documented:** `notes/data_sources.md`

## Next Steps
1. Run `01_prepare_data.R` to merge panel
2. Run `02_synthetic_control.R` to get SC results
3. Verify `taiwan_rd_pct_gdp_MANUAL.csv` against official NSTC yearbook
