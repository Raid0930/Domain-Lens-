---
name: domain-lens
description: >
  Beginner-friendly deep-dive domain research assistant. Input a research
  topic and it automatically performs keyword deconstruction, multi-source
  academic and industry retrieval, landscape mapping, and gap analysis, then
  outputs an illustrated mini review with linked references in plain language.
  Use for research-style requests such as "help me research the field of X",
  "write a mini survey on X", "帮我调研XX领域", "出个关于XX的小综述",
  "领域调研", "技术缺口分析", "gap analysis", "domain survey".
metadata:
  version: "1.0.0"
  task_type: open-ended
---

# DomainLens / 领域透镜

## 1. Purpose

Turn any research topic into a highly readable mini review, so that both
technical and non-technical readers can quickly build a systematic
understanding of the field: its current state, core technologies, published
results, and unsolved problems.

**Output language rule**: follow the language the user writes in. If the
user asks in Chinese, deliver the review in Chinese; if in English, deliver
in English. Academic terms may remain in English in either case.

## 2. Scope

- Activate when the user explicitly requests academic or industry research,
  a literature/field survey, or technical gap analysis.
- Do NOT use for pure fact lookup, code review, single-paper deep reading,
  or tasks unrelated to research.

## 3. Workflow

### 3.1 Topic Confirmation

If the user has not specified boundaries (time span, regional scope, research
depth), proactively ask 1–2 key constraints and proceed with defaults for
everything else:

- **Time**: prioritize the last 3–5 years unless the user specifies otherwise.
- **Language**: English literature primary; Chinese literature to supplement
  industry context.
- **Length**: a 1,200–2,000-word Markdown review by default.

Once constraints are received, START immediately — do not wait for
step-by-step confirmation.

### 3.2 Topic Deconstruction

Generate three layers of keywords for the given topic:

- **Core terms**: the research object and its key concepts.
- **Adjacent terms**: peripheral technologies, task types, typical scenarios.
- **Query strings**: Chinese/English combinations ready for database queries,
  e.g. `adolescent companionship robot AND healthcare`.

Suggested counts: 3–8 English query strings, 2–4 Chinese query strings.

### 3.3 Multi-Source Retrieval

Invoke available sources sequentially or in parallel; record retrieval dates
and coverage:

1. **Academic retrieval**
   - Use `web_search` for academic content; prioritize highly cited journal
     and conference papers, surveys, and preprints.
   - If the topic maps to specific databases, name the sources (IEEE Xplore,
     ACM DL, arXiv, PubMed, CNKI).
   - Keep at least one verifiable citation for every important conclusion;
     even when full text is unavailable, record an abstract-level source.
2. **Industry retrieval**
   - Search industry reports, white papers, think-tank studies, company
     blogs, and product pages.
   - Use these to supplement application scenarios, market context, deployed
     cases, and demand gaps.
3. **Code and tool retrieval**
   - Only when the topic involves reproducible implementation, search GitHub
     repositories, demo projects, or open datasets.
4. **Retrieval quality check**
   - If a source is outdated, barely cited, or a press release, mark it
     "evidence level: weak" in the body text and state the reason.
   - If retrieval results are insufficient to support a conclusion, state
     "evidence insufficient; recommend querying: XXXX" instead of proceeding
     silently.

### 3.4 Landscape Mapping

Extract high-frequency keywords and concept nodes, classified into four
categories:

- **Purpose**: what problem the research tries to solve, what need it serves.
- **Core technologies**: algorithms, architectures, models, tools, or
  engineering methods (plain-language explanation required).
- **Agent integration**: whether LLM/Agent orchestration, API integration,
  or tool calling is involved, and the calling strategy.
- **Development and production outcomes**: experimental metrics, prototype
  performance, commercial adoption.

Keep 3–6 sourced entries per category; merge verbose entries into
consolidated conclusions.

### 3.5 Gap Analysis

From limitations sections, experimental flaws, failed cases, and
future-work statements, extract three classes of gaps:

- **Technical gaps**: unsolved problems at the algorithm/model level.
- **Market gaps**: scenarios or populations not covered by existing products.
- **Demand gaps**: explicit or latent user needs not being met.

Every gap entry must cite its evidence source; if no literature supports it,
label it "inferred — needs empirical validation".

### 3.6 Content Generation

Output a complete Markdown review structured as follows:

1. **Introduction**: background, significance, retrieval scope.
2. **State of the field**: key advances and milestones, by timeline or theme.
3. **Core technologies**: each with a plain-language explanation.
4. **Gaps and opportunities**: three gap classes (technical / market /
   demand) with priority ranking.
5. **Mind map**: a Mermaid `mindmap` with the topic as the central node and
   technologies, current state, and gaps as branches.
6. **References**: clickable list, each entry labeled with source type and
   retrieval date.

### 3.7 Quality Gate

Check before delivery:

- [ ] No unsourced conclusions (tag the evidence level or delete them).
- [ ] Every major technical term carries a plain-language explanation.
- [ ] Mind-map nodes correspond to core terms in the body.
- [ ] Reference links checked once; if unreachable, mark the link status
      rather than silently deleting the reference.

### 3.8 Readability Norms

- Non-expert audience first: attach a bracketed explanation to every
  technical term on first use, e.g. `Transformer (a neural network that
  processes an entire text sequence in parallel)`.
- Avoid unexplained acronyms; on first occurrence, give the full form and
  a brief explanation.

### 3.9 Output Format

- File format: Markdown (`.md`), named `<topic>_DomainLens_Review_YYYYMMDD.md`.
- Page title: `# <Topic> — DomainLens Review`.
- Include a small number of formatted tables where they aid readability
  (e.g. comparing technical routes).
- For topics with existing visual assets, embed remote images; otherwise
  use a Mermaid diagram instead.

### 3.10 Prohibitions

- Never fabricate citations, data, or research conclusions; every conclusion
  must be sourced.
- Never treat press releases or marketing pages as academic evidence.
- Never make quantitative claims about technical performance or market size
  without a source.
- Never introduce analyses or analogies unrelated to the topic.

## 4. Termination

The task ends when the review has passed the Section 3.7 quality gate and
the user has received the complete output.
