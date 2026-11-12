# Executive Summary: BERT Model Sourcing Brief

**Prepared for:** Platform Review (due Friday)
**HF Account:** @lhz7891444 (https://huggingface.co/lhz7891444) — all Hub stats pulled live from the Hub via this account (user account, ID 68805cebc41d25c21ef2183e; write-role personal access token; no visible org memberships).
**GitHub Account:** HeziLiu (org: mcpmark-eval-liuhezi)

## Incumbent Model

Our current production model is google-bert/bert-base-uncased. Current Hub stats as returned right now: approximately **3,292.5M downloads** and **3,068 likes**. It is a 110.1M-parameter fill-mask model (architecture: bert, license: apache-2.0) under the google-bert organization, last updated 19 Feb 2024.

## Candidate Shortlist (top 3 most-downloaded BERT-family models on the Hub, excluding the incumbent)

| Model Identifier | Downloads | Likes |
|---|---|---|
| google-bert/bert-base-cased | 3.3M | 398 |
| google-bert/bert-base-multilingual-uncased | 2.0M | 177 |
| google-bert/bert-base-multilingual-cased | 1.5M | 623 |

All three are original Google BERT-family checkpoints (architecture: bert) with Apache-2.0 licensing.

## Where Things Live

- **Written brief:** model_sourcing_brief.docx (saved in the team workspace at /tmp/mcp_ws/)
- **Warehouse record:** BERT_SEARCH_STACK_SOURCING.EVAL.MODEL_SHORTLIST (Snowflake; database BERT_SEARCH_STACK_SOURCING, schema EVAL, table MODEL_SHORTLIST) — one row per shortlisted model plus one row for the incumbent, each with model identifier, download count, and like count. Verified row count: **4 rows (4 distinct models)**, confirmed via verification query.

## Next Steps

- Request a platform review of the three candidates (bert-base-cased, bert-base-multilingual-uncased, bert-base-multilingual-cased) against current production on accuracy, latency, and cost metrics before Friday.
- Validate BERT_SEARCH_STACK_SOURCING.EVAL.MODEL_SHORTLIST in Snowflake as the permanent record for future model sourcing evaluations; refresh download/like counts monthly.
- Update search stack routing configuration to allow fallback to the shortlisted BERT-family models if bert-base-uncased shows degradation in production.

---

*Note: This executive summary is hosted as a file in the `mcpmark-eval-liuhezi` organization repository (`mcpmark-eval-liuhezi/bert-model-sourcing`). The GitHub personal access token in use does not have the `gist` scope, so it could not be published as a gist; it was committed to the org repo instead.*
