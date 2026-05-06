# Contractor Management Platform

> Part of the [worlds-biggest-software-project](https://github.com/worlds-biggest-software-project) initiative.
>
> An AI-native, open-source platform for onboarding, classifying, and paying independent contractors with documented misclassification risk analysis.

Contractor Management Platform is a self-hostable system for HR, finance, and legal teams that engage independent contractors. It combines onboarding, document collection, invoice approval, and payment orchestration with an AI-driven classification engine that scores worker engagements against the IRS 20-factor, DOL economic reality, and state ABC tests. It targets the underserved segment of organisations with 10–200 contractors that find Deel and Rippling too expensive and Gusto too narrowly scoped.

---

## Why Contractor Management Platform?

- Misclassification liability is the dominant pain point in contractor management — IRS data implies cumulative exposure of approximately $135,900 over three years for a single misclassified $100K/year worker, yet no current open-source tool offers automated classification analysis.
- Deel charges $49/contractor/month and Rippling layers modular fees on top of its base platform; a company with 100 contractors pays Deel roughly $58,800/year for contractor management alone.
- Gusto is the only inexpensive option ($6/contractor/month) but is US-only and provides no classification analysis, no insurance certificate handling, and no multi-currency payments.
- The only existing OSS option (OrangeHRM core) treats contractors as a record type with no classification engine, no payment rails, and no jurisdiction-aware compliance.
- Data-sovereign organisations — government agencies, defence contractors, regulated SMBs — currently have no credible self-hosted contractor management option at all.

---

## Key Features

### Onboarding & Document Management

- Digital contractor agreement execution with jurisdiction-appropriate templates
- W-9 collection for US contractors and equivalent tax form collection for international engagements
- Smart document requirement engine that determines required documents (insurance certificates, right-to-work, local tax registration) based on contractor country, state, industry, and engagement type
- Centralised storage of agreements, tax forms, insurance certificates, and NDAs with expiry alerting
- Self-service contractor portal for document upload, profile management, and status tracking

### Classification & Compliance

- AI-powered classification risk assessment analysing engagement description, jurisdiction, control factors, and economic-dependence indicators
- Documented classification confidence scores with cited reasoning against IRS 20-factor, DOL economic reality, and state ABC tests, clearly labelled as guidance rather than legal advice
- Proactive regulatory monitoring of DOL, IRS, state labour board, and EU member-state feeds with automated alerts when changes affect existing contractor relationships
- EU Platform Work Directive tooling supporting the rebuttable presumption framework that member states must transpose by December 2026
- Audit-ready, immutable classification decision trail suitable for SOX and ERISA review

### Invoicing & Payments

- Contractor-submitted invoices with configurable manager approval workflow and bulk payment processing
- US domestic ACH payment processing via Stripe or Modern Treasury
- Multi-currency international payments via Wise API or Stripe Connect (v1.1)
- 1099-NEC generation and IRS filing for US contractors, with international tax-form equivalents for top contractor countries

### Operations & Reporting

- Unified dashboard showing contractor status, payment history, document expiry, and compliance posture
- Cryptographic audit logging to satisfy SOX Section 404 immutability and auditability requirements
- Self-hosted deployment option for organisations with data sovereignty requirements

---

## AI-Native Advantage

The platform's classification engine is its core differentiator: rather than the static, guidance-only checklists that incumbents provide, it analyses each engagement against the relevant legal tests and produces a documented confidence score with cited reasoning. AI-driven regulatory monitoring continuously watches DOL, IRS, state, and EU jurisdictional feeds and flags contractor relationships that drift out of compliance without requiring manual legal research. A smart document requirement engine replaces static checklists with jurisdiction-aware determinations of what evidence each engagement actually needs. Invoice anomaly detection flags unusual billing patterns that may indicate misclassification risk or fraud.

---

## Tech Stack & Deployment

The platform is designed for both self-hosted and managed deployment, with self-hosting prioritised for data-sovereign customers. Payment orchestration uses standard commercial APIs — Stripe Connect, Modern Treasury, and Wise — over open ACH (NACHA) rails. Classification logic is implemented against publicly available regulatory frameworks (IRS 20-factor, DOL economic reality, state ABC tests) and the EU Platform Work Directive (Directive 2024/2831). The system is built to align with GDPR data-handling obligations and ISO/IEC 27001 information-security expectations, with cryptographic audit logging for SOX-grade traceability.

---

## Market Context

The global contingent workforce management market was approximately $5.2B in 2024 and is projected to reach $8.1B by 2030 (CAGR ~7.8%), with contingent and gig workers comprising roughly 36% of the US workforce in 2025. Incumbent pricing ranges from $6/contractor/month (Gusto, US-only) and $1,999/year flat (Contractor Compliance, compliance-only) up to $49/contractor/month (Deel) and $20–$100/worker/month (Papaya, Rippling) for global coverage. Primary buyers are HR directors, finance and AP teams, general counsel concerned about misclassification exposure, and engineering or procurement managers who source contractors frequently.

---

## Project Status

> This project is in the **research and specification phase**.  
> Contributions, feedback, and domain expertise are welcome.

---

## Contributing

We welcome contributions from developers, domain experts, and potential users.
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Important:** All contributions must be your own original work or clearly attributed
open-source material with a compatible licence. Copyright infringement and licence
violations will not be tolerated and will result in immediate removal of the offending
contribution. If you are unsure whether a piece of code, text, or other material is
safe to contribute, open an issue and ask before submitting.

---

## Licence

Licence to be determined. See [discussion](#) for context.
