# Executive Summary: BERT-Family Model Sourcing Brief

**Prepared for:** Platform Review (due Friday)
**HF Account:** lhz7891444 (https://huggingface.co/lhz7891444) — all Hub stats pulled live from the Hub via this account.
**Deliverables:**
- Word brief: `model_sourcing_brief.docx` (saved in the team workspace)
- Snowflake warehouse table: `BERT_SOURCING.PUBLIC.MODEL_SHORTLIST`

---

## Incumbent Model

**google-bert/bert-base-uncased** — our current production model.
- **Downloads (current, per Hub):** ~3,292.5M (3.29B)
- **Likes (current, per Hub):** 3,067
- **Source:** https://hf.co/google-bert/bert-base-uncased
- 110.1M parameters, fill-mask task, Apache-2.0 license, last updated 19 Feb 2024.

## Candidate Shortlist (top 3 most-downloaded BERT-family models on the Hub, excluding the incumbent)

| # | Model Identifier | Downloads (per Hub) | Likes (per Hub) |
|---|---|---|---|
| 1 | google-bert/bert-base-cased | 334.6M | 398 |
| 2 | google-bert/bert-base-multilingual-uncased | 124.1M | 177 |
| 3 | google-bert/bert-base-multilingual-cased | 263.1M | 623 |

All three are original Google BERT-family checkpoints (architecture: bert) with Apache-2.0 licensing.

## Snowflake Warehouse Record

- **Table path:** `BERT_SOURCING.PUBLIC.MODEL_SHORTLIST`
- **Contents:** 4 rows total — 1 for the incumbent (`google-bert/bert-base-uncased`) and 3 for the candidates, each with MODEL_ID, DOWNLOAD_COUNT, LIKE_COUNT, RECORD_TYPE (INCUMBENT / CANDIDATE), and SOURCED_AT timestamp.
- **Verified row count:** 4 (1 incumbent + 3 candidates), confirmed via verification query.

## Recommendation

All three candidates are strong, well-maintained Google BERT-family checkpoints with substantial community adoption. The shortlist should be validated in staging with our benchmark suite before any commitment is made at the platform review.

---

*Note: This executive summary is hosted as a file in the `mcpmark-eval-liuhezi` organization repository. The GitHub personal access token in use does not have the `gist` scope, so it could not be published as a gist; it was committed to the org repo instead.*
