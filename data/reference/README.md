# MTL-XF-033 — References and mappings

Retain source documentation, licence/citation notices and required codebooks for Bank Marketing. Extract nested bank.zip; read bank-full.csv with semicolon separator and bank-names.txt. Ignore bank.csv sample and bank-additional variants.

Version each reference with ID, official URL, retrieval date/version, content checksum, rights, raw→display mapping, rationale, owner and reviewer. Unknown categories remain visible; validate mapping completeness/uniqueness and all many-to-many joins.

**Interpretation rule:** No stable customer ID is available. duration leaks completed-call information and must be excluded from pre-call prioritisation. Historical subscription probability is not incremental campaign uplift; consent, customer vulnerability and actual account profitability are absent.

**Project policy assumptions:** Baseline selects a deterministic random 20% contact list (seed 33). Alternative selects top-scored 20% using a validation-selected model and locked tie rule. Evaluate subscriptions per 1,000 attempted contacts and assumed net value under £1/£3/£5 contact costs and £20/£50/£100 subscription value; all amounts are simulation assumptions.

Keep choices separate from publisher facts. Register categorical/segment/class labels, unit conversions and any financial or capacity assumptions. Do not invent operational history absent from S1.

A reference explains the source; it cannot supply an unmeasured outcome. Register supplements and scope changes in [SOURCE_REGISTER.md](../SOURCE_REGISTER.md) before dependent work.
