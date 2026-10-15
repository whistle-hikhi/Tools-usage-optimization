# Therapeutics / Drug-Discovery Data Commons as Agent Tool Sources

## What large structured data commons underlie medical/therapeutic LLM agent tools (feeding ToolUniverse, TxAgent, and others)?

### Takeaway
Two Harvard-originated resources — Therapeutics Data Commons (TDC/TDC-2) and PrimeKG — function as the structured-data backbone that several agent tool catalogs (including ToolUniverse/TxAgent) query as tools, rather than being agents themselves. They are the "database" half of the tool-catalog ecosystem, complementing the "API/tool-execution" half covered in the other notes in this folder.

### Cited Findings
- **Therapeutics Data Commons (TDC / TDC-2)** ([GitHub: mims-harvard/TDC](https://github.com/mims-harvard/TDC); original paper [arXiv:2102.09548](https://arxiv.org/abs/2102.09548); NeurIPS 2021 Datasets & Benchmarks; TDC-2 [bioRxiv](https://www.biorxiv.org/content/10.1101/2024.06.12.598655v1.full)) — a coordinated Harvard (Zitnik Lab) initiative providing 66+ AI-ready datasets across 22 learning tasks spanning drug discovery and development, plus 33 data functions, 23 model-evaluation strategies, 17 molecule-generation oracles, and 29 public leaderboards. TDC-2 explicitly reframes this as an "API-first" dataset model with a multimodal retrieval API, stated as designed for integration into "emerging tool-based LLMs and agentic workflows" rather than only static ML benchmarking.
- **PrimeKG** ([GitHub: mims-harvard/PrimeKG](https://github.com/mims-harvard/PrimeKG)) — Harvard's Precision Medicine Knowledge Graph, integrating 20 high-quality biomedical resources to describe 17,080 diseases with 4,050,249 relationships across ten biological scales, including text descriptions of clinical guidelines for drugs and diseases (enabling multimodal, not just graph-structural, queries). TDC-2 explicitly leverages PrimeKG as one of its integrated resources.
- Both TDC and PrimeKG originate from the same lab (Zitnik Lab, Harvard) as ToolUniverse and TxAgent, suggesting a single research group has built a vertically integrated stack: structured data commons (TDC, PrimeKG) → tool/API wrapping layer (ToolUniverse) → application-level reasoning agent (TxAgent).

### Inferences
- For a workshop paper distinguishing "tool catalogs" from "knowledge sources," TDC and PrimeKG are better classified as *data sources that tools query* rather than *tools* in the function-calling sense — but they are frequently the concrete thing a general biomedical tool catalog (ToolUniverse) exposes as a callable API, so any taxonomy of "medical agent tools" should note this layering explicitly (API wrapper vs. underlying database) to avoid conflating the two in a tool-count comparison.

### Gaps
- No paper located in this pass benchmarks agent tool-selection accuracy specifically over TDC's or PrimeKG's API surface in isolation (as opposed to as one resource among hundreds inside ToolUniverse or Biomni) — i.e., there is no PrimeKG-specific or TDC-specific analog to MedAgentBench's FHIR-tool-selection evaluation.
