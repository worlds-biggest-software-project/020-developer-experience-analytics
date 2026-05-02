# Developer Experience (DX) Analytics

Unified developer productivity platform combining DORA metrics, SPACE framework assessment, AI-generated causal analysis, and ambient wellbeing inference — providing engineering managers with actionable insights without survey fatigue or surveillance anxiety.

## The Problem

Developer productivity measurement is caught between two bad options:

- **Quantitative-only tools** (LinearB, CodePulse) measure velocity but miss wellbeing and flow state
- **Quantitative + survey tools** (DX, Swarmia) require periodic surveys; response rates degrade over time; respondents game the system
- **No open-source tool integrates both dimensions** — Apache DevLake covers metrics; Swarmia covers surveys; none do both
- **Atlassian's $1B acquisition of DX** (September 2025) removes the leading independent option; leaves open-source gap

Engineering teams need:
1. **DORA metrics** (deployment frequency, lead time, change failure rate, MTTR) without per-developer surveillance
2. **Qualitative signals** (cognitive load, flow state, satisfaction) without survey fatigue
3. **Causal analysis** of metric degradation ("lead time increased because PR size grew 40%")
4. **Privacy preservation** — team-level aggregation, never individual developer exposure

## What This Does

### DORA + SPACE Integration
- **DORA four metrics** from VCS and CI/CD data — deployment frequency, lead time, change failure rate, MTTR
- **SPACE framework** dimensions — satisfaction, performance, activity, communication, efficiency
- **Team-level aggregation** — never surfaces individual developer metrics (privacy by design)
- **Trend dashboards** — weekly, monthly, quarterly views with statistical significance testing
- **Built on Apache DevLake** — Apache-2.0 foundation, SQL-queryable data lake

### AI-Generated Causal Narration (LLM-Native)
- **Weekly team health summary** explaining metric changes with correlated contributing signals
- **"Lead time increased 2.3 days this sprint because average PR size grew from 240 to 420 lines. Correlation: three new feature PRs unreviewed for >3 days waiting for review from the same 2 people."**
- **Actionable insights** — not raw numbers but narratives a manager can act on
- **No existing open-source tool does this** — Apache DevLake has metrics; no causal layer

### Ambient Wellbeing Inference (AI-Native)
- **Infers developer wellbeing from behavioral signals** — no surveys required
- **PR comment tone analysis** — frustration vs. engagement in code review discussions
- **Time-to-first-review patterns** — team responsiveness, reviewer load distribution
- **After-hours commit frequency** — burnout indicator without surveillance anxiety
- **Context-switching frequency** — inferred from Git activity patterns
- **Continuously updated** — always-on signal vs. periodic survey response

### AI-Code Contribution Tracking
- **Distinguishes AI-generated from human-authored code** contributions
- **Correlates with DORA stability** — 2024 DORA report found AI adoption correlates with 7.2% delivery stability decrease
- **Enables differentiation** — "instability caused by large AI-generated PRs" vs. other failure modes
- **No tool addresses this gap** — DORA metrics are blind to AI-code contribution rates

### Privacy-Preserving Manager Narratives
- **Deliberate team-level aggregation** — prevents individual surveillance anxiety
- **Manager-facing reports** (not developer-facing) — "review bottleneck in authentication service: same 2 reviewers handling 80% of load"
- **Compliant with union and European data protection** — required for adoption in sensitive contexts

## Key Differentiators

| Feature | This Platform | DX (Atlassian) | LinearB | Swarmia | Apache DevLake |
|---------|---|---|---|---|---|
| **DORA metrics** | ✓ | ✓ | ✓ | ✓ | ✓ |
| **SPACE framework** | ✓ | ✓ | — | ✓ | — |
| **AI causal narration** | ✓ | (Insight cards) | — | — | — |
| **Ambient wellbeing** | ✓ (No surveys) | Survey-based | — | Survey-based | — |
| **AI code tracking** | ✓ | — | — | — | — |
| **Privacy-first design** | ✓ (Team-level) | Team-level | Dev-level exposed | Team-level | Team-level |
| **Open source** | ✓ (Apache DevLake foundation) | — | — | — | ✓ |

## Market & Opportunity

- **Market size**: Dev tools $7.44B (2026) → $15.72B (2031) at 16.1% CAGR
- **Developer Productivity Insight Platforms**: Gartner-tracked category; $5–$20/developer/month per estimates
- **Atlassian's $1B DX acquisition (Sept 2025)** sets market-cap benchmark for the category
- **Buyers**: VPs of Engineering, CTOs, engineering managers, platform teams
- **Open-source gap**: DX's acquisition removes the leading independent option; no OSS tool combines metrics + surveys + AI analysis

## Research Foundation

- **DORA metrics** (Forsgren, Humble, Kim; *Accelerate*, 2018) — foundational research
- **SPACE framework** (Forsgren et al., ACM Queue 2021) — five-dimension view of developer productivity
- **DevEx / DX Core 4 framework** (Noda, Forsgren, Storey, Greiler, ACM Queue 2023) — operationalizes developer experience
- **2024 DORA Report** — AI adoption correlates with 7.2% delivery stability decrease
- **Google DORA Research Program** — annual Accelerate State of DevOps Report

## Quick Start

```bash
# Deploy with Apache DevLake as foundation
docker-compose up -d devlake postgres

# Configure VCS and CI/CD integrations
devlake config:
  - github: repo/owner
  - gitlab: repo/owner
  - github-actions: workflows
  - circleci: pipelines
  - pagerduty: incidents

# Enable AI causal analysis
analytics:
  ai_narration: enabled
  causal_signals: [pr_size, ci_flakiness, reviewer_load, deploy_frequency]

# Configure ambient wellbeing inference
wellbeing:
  ambient_inference: enabled
  signals: [pr_sentiment, review_response_time, after_hours_activity, context_switching]

# Track AI-generated code
code_analysis:
  ai_code_detection: enabled
  correlate_with: [dora_metrics, stability_signals]
```

## Target Users

1. **VPs of Engineering / CTOs** — board-level reporting on engineering investment ROI
2. **Engineering Managers** — team health signals without surveillance anxiety
3. **Platform / DevEx Engineers** — open APIs and integration with existing tooling
4. **Individual Contributors** — opt-in personal dashboard without mandatory exposure
5. **Compliance / HR** — privacy-preserving metrics aligned with union/GDPR requirements

## Related Standards

- DORA Metrics — four-metric foundation (Forsgren, Humble, Kim)
- SPACE Framework — five-dimension productivity model (ACM 2021)
- DevEx / DX Core 4 Framework — survey + metric hybrid (ACM 2023)
- Flow Framework — connects engineering activity to business value (Planview)
- OpenTelemetry (OTLP) — instrumentation of CI/CD pipelines and deployments
- SLSA (Supply-chain Levels for Software Artifacts) — deployment provenance

---

Built on research from Nicole Forsgren and Abi Noda (DORA, SPACE, DevEx frameworks), the 2024 DORA Report, and the Atlassian/DX research partnership. Open-source foundation built on Apache DevLake (Apache-2.0). [Read the full research](./research.md) | [Feature roadmap](./features.md)
