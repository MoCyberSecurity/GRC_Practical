# Lab04 – ISO/IEC 27001 ISMS Implementation (Applied GRC Lab)

**Purpose:** a practical, end-to-end ISMS implementation guide tailored for small-to-medium organisations that demonstrates senior-level governance, audit leadership, and operational control. Designed to be used as a consulting engagement blueprint and as evidence of real-world capability for GRC roles.

**Scope of this lab:** scoping, context, risk assessment, control selection (SoA), treatment planning, policy & procedure mapping, internal audit, management review, surveillance, continual improvement, and expected outcomes.

---

## Quick index
1. Why this lab matters (evidence & outcomes).  
2. Engagement assumptions & preparatory work.  
3. Step-by-step implementation phases (A → Z) with sub-tasks, deliverables, and artifacts.  
4. Control selection & SoA guidance.  
5. Internal audit & evidence collection.  
6. Management review and board reporting.  
7. Surveillance, continual improvement, and expected business outcomes.  
8. Example artifacts to include in the `examples/` folder.  

---

## 1. Why this Lab matters (summary)
ISO 27001 implementation demonstrates a risk-based, board-aligned approach to information security. Certification produces measurable benefits including higher customer confidence and market access, faster containment of incidents, better regulatory alignment, and operational efficiencies — outcomes demonstrated in multiple case studies and vendor analyses. :contentReference[oaicite:5]{index=5}

---

## 2. Engagement assumptions & preparatory work

**Assumptions**
- Organisation size: SME (10–500 employees) but approach adapts to larger enterprises.
- Executive sponsorship is committed (CEO/Board-level champion identified).
- Access to key stakeholders (IT, HR, Legal, Finance, Operations).
- Existing basic IT controls (firewalls, AV/EDR) but may not be fully documented.

**Prep tasks (deliverables)**
- Obtain executive sign-off to start ISMS (recorded in Management Sponsor Charter).
- Identify a cross-functional Steering Committee and assign a Security Program Manager (SPM).
- Baseline data collection: inventory of critical assets, existing policies, known incidents, prior audits.

---

## 3. Implementation phases (detailed, with subcategories)

### Phase 0 — Project initiation & governance
**Goal:** establish authority, resources, and governance for the ISMS project.

**Key activities**
- Create **ISMS Project Charter** (objectives, scope, budget, roles, milestones).
- Form **Security Steering Committee** (weekly → monthly cadence).
- Map **communication plan** for stakeholders and staff.

**Artifacts**
- Project Charter (signed by CEO)
- Steering Committee Terms of Reference
- Project plan (Gantt / milestone list)

---

### Phase 1 — Understand context & scope (Clause 4 ISO 27001)
**Goal:** define boundaries and context for the ISMS.

**Key activities**
- Perform **Organisational Context Analysis** (external/internal issues, interested parties).
- Identify legal, regulatory, contractual obligations (GDPR, PCI-DSS, sector rules).
- Draft **Scope Statement**: what is in, what is out, locations, systems, business units.

**Deliverables**
- Scope Statement (example in `examples/sample_scope_statement.md`)
- Interested Parties & Requirements Register

**Notes (practical):**
- For small businesses, scope often focuses on customer-facing systems and data processing functions. Avoid scope creep: start narrow and extend later.

---

### Phase 2 — Leadership & governance (Clause 5)
**Goal:** obtain executive commitment and set ISMS policy & risk appetite.

**Key activities**
- Draft **Information Security Policy** (high-level principles).
- Define **Risk Appetite & Tolerance** statements and approval workflow.
- Assign **roles**: Data Owner, Risk Owner, Control Owner, ISMS Manager, Internal Auditor.

**Deliverables**
- Information Security Policy
- Risk Appetite Statement
- Role & Responsibility matrix (RACI)

**Board-level evidence**
- Signed policy by CEO, evidence of resource allocation, meeting minutes.

---

### Phase 3 — Risk assessment methodology & asset inventory (Clause 6)
**Goal:** select a repeatable risk methodology and build asset inventory.

**Key activities**
- Choose risk methodology (qualitative, quantitative, hybrid). Document scales (likelihood × impact).
- Create **Asset Register** with classification, owners, location, value.
- Identify threats & vulnerabilities per asset.
- Run initial **Risk Assessment Workshops** with Business Process Owners.

**Deliverables**
- Risk Assessment Methodology document (`02_Risk_Assessment_Methodology.md`)
- Asset Register (CSV/MD)
- Initial Risk Register (redacted example in `examples/redacted_risk_register_example.md`)

**Practical tips**
- Use standard templates for scoring. Begin with top 20–30 assets to keep initial scope manageable.
- Map critical business processes to assets to derive RTO/RPO where appropriate.

---

### Phase 4 — Risk analysis, evaluation & treatment (Clause 6.1.3)
**Goal:** prioritize risks and choose treatment options: mitigate, accept, transfer, avoid.

**Key activities**
- Score risks using approved methodology.
- Map risks outside appetite for immediate treatment.
- Produce a **Risk Treatment Plan (RTP)** with owners, timelines, costs.
- Evaluate control effectiveness and cost/benefit for treatments.

**Deliverables**
- Risk Treatment Plan template (`04_Risk_Treatment_Plan_Template.md`)
- Updated Risk Register with treatment status

**Practical**
- For ransomware risk: consider combination of offline encrypted backups + immutable storage + EDR tuning + insurance.
- For data leakage: DLP + classification + least privilege + contractual controls with vendors.

---

### Phase 5 — Statement of Applicability (SoA) & control selection (Clause 6.1.3 / Annex A)
**Goal:** create SoA listing selected controls, mapping to risk treatment & justification.

**Key activities**
- Map risks → Annex A controls (ISO 27002 guidance) → other frameworks where needed (NIST CSF, CIS).
- Decide 'Implemented/Planned/Not applicable' for each Annex A control and justify N/A items.
- Document compensating controls where direct controls aren't feasible.

**Deliverables**
- SoA Template & populated sample (`03_Statement_of_Applicability_Template.md`)
- Control implementation plan with owners

**Practical note**
- Use mappings to other frameworks for cloud or regulated contexts (e.g., map ISO Annex controls to PCI or NIST controls for vendor requests).

---

### Phase 6 — Policies, procedures, and baseline controls (Clause 7/8)
**Goal:** develop the necessary documentation: policies, SOPs, runbooks, and technical baselines.

**Key activities**
- Publish core policies (AUP, Access Control, Data Classification, IRP) — link Lab01 artifacts as starting material.
- Develop procedures for: access provisioning, patch management, change control, backup, incident handling.
- Define **technical baseline configurations** (hardening standards) per classification level.

**Deliverables**
- Policies & Procedures Index (`05_Policies_and_Procedures_Index.md`)
- Baseline configuration templates (server, endpoint, network)
- Evidence of rollout (training logs, signed acknowledgements)

**Practical**
- Document “how we do it now” and make clear owner and review cycle. Keep policies concise and practical.

---

### Phase 7 — Implement controls & operational integration (Clause 8/10)
**Goal:** deploy and operate controls with monitoring and measurement.

**Key activities**
- Implement prioritized technical and administrative controls (per SoA).
- Deploy logging/monitoring (SIEM or log aggregation) and establish detection rules.
- Operationalize patch management, vulnerability scanning, backup testing.
- Conduct awareness training tuned to observed risks (use Lab03 materials).

**Deliverables**
- Control Evidence pack (implementation screenshots, policy signoffs)
- Monitoring strategy & baseline metrics (KPI/KRI list)

**Practical**
- For minimal overhead, start with managed SIEM or EDR solutions and document tuning steps.

---

### Phase 8 — Internal audit & corrective actions (Clause 9)
**Goal:** verify ISMS conforms to ISO 27001 requirements and is effectively implemented.

**Key activities**
- Prepare **Internal Audit Plan** (scope, frequency) mapped to Annex A controls.
- Conduct audits using objective evidence; interview control owners and review logs/configs.
- Raise **Nonconformities** and assign Corrective Action Plans (CAPs). Track to closure.
- Prepare audit reports summarizing findings, risk impact, and remediation status.

**Deliverables**
- Internal Audit Checklist (`06_Internal_Audit_Checklist.md`)
- Audit Report & CAP tracker

**Practical**
- Train internal auditors (or use external specialists) and ensure independence of audit function.

---

### Phase 9 — Management review & certification readiness (Clause 9/10)
**Goal:** present ISMS top-level summary to leadership; prepare for external certification.

**Key activities**
- Run **Management Review Meeting**: ISMS performance, risk register status, resources, changes, improvement opportunities.
- Rectify open high-risk CAPs prior to external audit; ensure evidence is organized.
- Engage with an accredited Certification Body for Stage 1/Stage 2 audits.

**Deliverables**
- Management Review minutes template (`07_Management_Review_Template.md`)
- Certification readiness checklist

**Practical**
- Ensure Board has visibility to approve scope changes and risk appetite; capture all decisions in minutes.

---

### Phase 10 — Certification & surveillance (Clause 10)
**Goal:** achieve certification and maintain continual improvement.

**Key activities**
- Undergo Stage 1 (documentation review) and Stage 2 (implementation & evidence) audits.
- Address auditor observations and close nonconformities.
- Implement surveillance plans: periodic internal audits, management reviews, continuous monitoring.

**Deliverables**
- Certification report (once achieved)
- Surveillance calendar & continual improvement backlog (`08_Surveillance_and_Continual_Improvement.md`)

**Practical outcomes (documented in case studies):**
- Better customer trust, fewer external audit requests, faster incident containment, measurable overhead reduction when using ISMS tooling and defined procedures. :contentReference[oaicite:6]{index=6}

---

## 4. Control selection & SoA — practical guidance

- **Map risks to Annex A (ISO 27002) controls** first; when annex control is N/A, document business justification.
- **Use compensating controls** where direct control is infeasible (document residual risk).
- **Prioritise controls** that reduce likelihood and impact for top critical risks (backup & recovery for ransomware, IAM/MFA for credential theft, DLP & classification for data leakage).

**Suggested SoA columns:**
- Control ID (Annex ref)
- Control description
- Implementation status (Implemented/Planned/N/A)
- Evidence reference (log, config, doc)
- Owner
- Residual risk rating
- Justification for N/A or compensating control

---

## 5. Internal audit & evidence collection — professional tips

- **Evidence-first mindset:** Collect screenshots, logs, policy signoffs, SR tickets, and monitoring outputs. Each control should have at least 1 piece of objective evidence.
- **Sampling approach:** For distributed endpoints, sample with an evidence matrix to avoid excessive evidence collection but ensure representativeness.
- **Redaction & confidentiality:** When sharing audit reports publicly, redact PII and sensitive vendor details.

---

## 6. Management review & board reporting — what to present

Board-level reporting should be concise and decision-focused:

**Recommended board pack:**
- ISMS status dashboard (Top 10 risks, trending)
- High severity nonconformities and remediation roadmap
- Key metrics: number of incidents, MTTR, number of overdue CAPs, % controls implemented (SoA coverage)
- Significant changes to context, scope, or legal obligations
- Resource requests (budget, headcount) with ROI justification

**Presentation tip:** Link security investments to business outcomes (risk reduction, contractual wins, insurance premium improvement).

---

## 7. Surveillance, continual improvement & expected outcomes

**Continual improvement activities:**
- Weekly operational metrics reviews
- Quarterly risk re-assessment
- Annual internal audit & management review
- Periodic tabletop and full-scale DR tests

**Expected business outcomes (from studies & case stories):**
- Improved win rates with enterprise customers and reduced procurement friction. :contentReference[oaicite:7]{index=7}  
- Faster incident containment and clearer evidence for insurers/regulators. :contentReference[oaicite:8]{index=8}  
- Efficiency gains using ISMS tooling and templates (workload reduction during implementation reported in vendor case studies). :contentReference[oaicite:9]{index=9}

---

## 8. Example artifacts to include in `examples/` folder

- `sample_scope_statement.md` — real-looking scope with assets & exclusions.  
- `redacted_risk_register_example.md` — top 10 risks with scores and treatments.  
- `sample_soa.md` — Annex A mapping for top relevant controls.  
- `management_review_minutes_example.md` — board minutes showing decisions.

---

## Sources & further reading (selected)
- IT Governance — Key Benefits of ISO 27001. :contentReference[oaicite:10]{index=10}  
- ISMS.online — Tangible ROI / time to breach containment and business case builder. :contentReference[oaicite:11]{index=11}  
- BSI case study (SVM) – practical implementation and internal auditor training. :contentReference[oaicite:12]{index=12}  
- Advisera case study — practical lessons learned (start with risk assessment). :contentReference[oaicite:13]{index=13}  
- Industry commentary on risk & incident lessons (ISMS.online lessons). :contentReference[oaicite:14]{index=14}

---

## Next steps I can implement for you

If you want, I will create the following files (ready for GitHub) next:
- `01_Scoping_and_Context.md` (sample scope + step-by-step template)
- `02_Risk_Assessment_Methodology.md` (detailed workshop script + templates)
- `03_Statement_of_Applicability_Template.md` (SoA matrix with sample rows)
- `04_Risk_Treatment_Plan_Template.md` (detailed RTP with costing columns)
- `06_Internal_Audit_Checklist.md` (annex-linked checklist + evidence examples)
- `examples/*` artifacts (scope, redacted risk register, sample SoA, management minutes)

Tell me which two files you want first (I recommend: **Scoping & Risk Assessment**), and I’ll create them in full with realistic, redacted sample content and templates.
