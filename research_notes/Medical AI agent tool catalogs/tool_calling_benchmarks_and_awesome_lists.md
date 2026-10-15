# Medical Tool-Calling Benchmarks/Datasets and Curated Discovery Lists

## What datasets define/benchmark biomedical tool-calling specifically (as opposed to clinical-reasoning benchmarks already covered), and where can new tool catalogs be tracked over time?

### Takeaway
A newer, narrower benchmark category has emerged that evaluates tool-calling *mechanics* over a fixed biomedical API pool (distinct from the clinical-reasoning/diagnosis benchmarks — AgentClinic, MedAgentBench, etc. — already in the companion report's `clinical_agent_benchmarks.md`). Separately, several actively maintained "awesome list" repositories exist specifically to track new medical AI agent/tool releases, useful as a standing discovery mechanism rather than a one-time catalog.

### Cited Findings — tool-calling benchmarks/datasets
- **BioTool** ([ACL 2026](https://aclanthology.org/2026.acl-long.2138/); earlier version [arXiv:2605.05758](https://arxiv.org/html/2605.05758)) — an instruction-fine-tuning-style biomedical tool-calling dataset: 7,040 high-quality, human-verified query→API-call pairs over 34 frequently used tools collected from NCBI, Ensembl, and UniProt, spanning variation, genomics, proteomics, evolution, and general biology. Fine-tuning a 4B-parameter LLM on BioTool is reported to outperform commercial LLMs including GPT-5.1 on biomedical tool-calling. This is a direct biomedical analog to BFCL/ToolBench in the general-domain companion report, but scoped specifically to genomics/proteomics API calls rather than general software APIs or clinical FHIR actions.
- **CalcQA** (introduced alongside MeNTi, [arXiv:2410.13610](https://arxiv.org/pdf/2410.13610)) — 100 case-calculator pairs evaluating selection/use of the 281-tool medical calculator toolkit; see companion-report cross-reference in `clinical_calculators_and_mcp_servers.md` in this folder.

### Cited Findings — curated discovery lists ("awesome lists")
- **[AgenticHealthAI/Awesome-AI-Agents-for-Healthcare](https://github.com/AgenticHealthAI/Awesome-AI-Agents-for-Healthcare)** — 210+ entries tracking agentic AI/AI agents for healthcare, including MedAgentGym (training LLM agents for medical reasoning) and LungNoduleAgent (lung nodule diagnosis).
- **[ZJU4HealthCare/Awesome-Medical-LLMs-and-Agents](https://github.com/ZJU4HealthCare/Awesome-Medical-LLMs-and-Agents)** — tracks recent systems such as MedAgent-Pro (ICLR 2026, evidence-based multi-modal medical diagnosis).
- **[FreedomIntelligence/Awesome-AI4Med](https://github.com/FreedomIntelligence/Awesome-AI4Med)** — curated list of medical LLMs, multimodal systems, datasets, and benchmarks.
- **[Nanboy-Ronan/awesome-medical-imaging-agents](https://github.com/Nanboy-Ronan/awesome-medical-imaging-agents)** — imaging-specific: radiology agents, pathology agents, segmentation agents, medical VLM agents; recent entries include RadAgent (chest CT interpretation) and Echo-alpha (ultrasound interpretation). Useful if the research scope ever extends to imaging-tool agents, which the companion report does not currently cover.
- **[juneyaooo/awesome-medical-ai](https://github.com/juneyaooo/awesome-medical-ai)** — broader open-source medical/healthcare AI projects (LLMs, imaging, multi-agent systems, clinical software), spanning OpenAI, Anthropic, Gemini, and other platforms.
- **[infonality/awesome-llm-biomedicine](https://github.com/infonality/awesome-llm-biomedicine)** and **[yczhou001/Awesome-Medical-LLM-Agent](https://github.com/yczhou001/Awesome-Medical-LLM-Agent)** — adjacent curated lists; the latter frames the field as "the evolution from medical LLMs to versatile medical agents," and references Biomni (this folder's `general_purpose_toolboxes.md`) and MedAgentGym directly.

### Inferences
- BioTool's framing (fine-tuning beats prompting commercial frontier models on biomedical tool-calling) is the clearest medical-domain data point for a workshop paper's "specialist fine-tuning vs. generalist prompting" axis — directly comparable in spirit to the general-domain report's ReWOO distillation result (175B→7B planner/solver distillation), suggesting a possible cross-domain parallel worth drawing out explicitly.
- The "awesome list" ecosystem is fragmented (at least 7 independently maintained lists found, several overlapping) — no single canonical index exists for "medical LLM agent tools," which is itself consistent with the companion report's observation that the medical benchmark/tooling ecosystem is "genuinely dense and still-fragmenting."

### Gaps
- BioTool's 34-tool pool (NCBI/Ensembl/UniProt) has not been cross-checked against ToolUniverse's or Biomni's tool catalogs for overlap — unclear whether BioTool tests a subset of tools already present in the larger general-purpose catalogs or an independent pool.
- Awesome-list entries are self-reported/community-curated and were not independently verified against primary sources in this pass; treat specific tool/agent names surfaced only through these lists (e.g., LungNoduleAgent, Echo-alpha, RadAgent) as leads to verify before citing in a paper draft.
