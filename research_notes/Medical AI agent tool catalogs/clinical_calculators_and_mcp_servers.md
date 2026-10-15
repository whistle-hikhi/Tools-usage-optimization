# Clinical Calculator Toolkits and Biomedical MCP Servers

## What curated clinical-calculator toolkits exist, and what MCP (Model Context Protocol) servers expose biomedical data to agents?

### Takeaway
Clinical-calculator toolkits (AgentMD's RiskCalcs, MeNTi's toolkit) are covered in depth in the companion report's `clinical_tool_efficiency.md` note; this note adds the production/open-source MCP-server layer that exposes biomedical databases (literature, genes, diseases, variants, drugs) to any MCP-compatible agent (Claude Code/Desktop, GPT, etc.), which is a distinct and fast-growing category not covered there.

### Cited Findings — calculator toolkits (cross-reference)
- **AgentMD / RiskCalcs** ([arXiv:2402.13225](https://arxiv.org/pdf/2402.13225)) — 2,164 PubMed-mined clinical risk calculators; retrieved via MedCPT embeddings, selected/executed by an LLM. 87.7% accuracy on RiskQA vs. 40.9% for CoT GPT-4. See companion report for full detail.
- **MeNTi** ([arXiv:2410.13610](https://arxiv.org/pdf/2410.13610)) — "metatool and nested calling" architecture; 281-tool medical calculator toolkit; CalcQA benchmark (100 case-calculator pairs).
- **[medical-calc-mcp](https://github.com/u9401066/medical-calc-mcp)** — open-source MCP server exposing 121 validated medical calculators to AI agents, built with a DDD (domain-driven design) architecture, evidence-based formulas with PMID citations; supports Claude, GPT, and other LLM integrations via MCP. This is the first located instance of a clinical-calculator toolkit shipped specifically as an MCP server rather than a bespoke agent framework.

### Cited Findings — biomedical MCP servers
- **[BioMCP](https://biomcp.org/)** ([mcp.so listing](https://mcp.so/server/biomcp/genomoncology)) — MIT-licensed open-source MCP server unifying search/retrieval across dozens of biomedical sources (PubTator3, Europe PMC, ClinVar, UniProt, etc.). Provides 24 specialized tools including a "Think Tool" (recommended first), gene/disease/drug lookup tools (`gene_getter` via MyGene.info, `disease_getter` via MyDisease.info), and search/retrieval tools for clinical trials, scientific literature, and genomic variants. Installable as a CLI/MCP server (`biomcp serve`) and registrable with Claude Desktop, Claude Code, or Codex.
- **[INDRA Knowledge Graph MCP server](https://discovery.indra.bio/mcp)** — exposes the INDRA mechanistic biomedical knowledge graph (causal/molecular mechanism statements extracted from literature) via MCP.
- **[BioContext.ai registry](https://biocontext.ai/registry)** — a registry/index site cataloging biomedical MCP servers; functions as a discovery hub rather than a tool itself, useful for finding newly published servers as the ecosystem grows.
- **[OpenClaw-Medical-Skills](https://github.com/FreedomIntelligence/OpenClaw-Medical-Skills)** — described as "the largest open-source medical AI skills library" for the OpenClaw agent framework, with 869 AI agent skills spanning biomedical and clinical research (skills ≈ structured tool-use procedures, adjacent to but distinct from raw API tool catalogs).

### Inferences
- The clinical-calculator category has moved from bespoke research-paper architectures (AgentMD's custom retrieval pipeline, MeNTi's nested-calling mechanism) to a standardized, protocol-level packaging (MCP servers) that any MCP-compatible agent can consume without reimplementing retrieval/selection logic — this mirrors the same standardization trend ToolUniverse represents at the "all biomedical tools" scale.
- No paper or repo located directly compares calculator-selection accuracy between a bespoke research pipeline (AgentMD's MedCPT retrieval) and a generic MCP-exposed toolkit (medical-calc-mcp) under the same evaluation protocol — open comparison opportunity.

### Gaps
- Could not verify medical-calc-mcp's or BioMCP's tool counts/architecture against independent benchmark results (e.g., no CalcQA or RiskQA score reported for either as of this search pass) — these are engineering/packaging artifacts, not yet benchmarked research contributions.
