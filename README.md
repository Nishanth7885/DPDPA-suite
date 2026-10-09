# DPDPA Suite

**DPDP Act compliance, built into your stack.**

DPDPA Suite is an early-stage, hosted developer platform and AI toolkit that helps healthcare providers and other teams handling sensitive personal data comply with India's Digital Personal Data Protection Act, 2023 and the DPDP Rules, 2025. Ship consent, data principal rights, breach response and data discovery through APIs, instead of spreadsheets.

> **Status:** Private beta. We are onboarding a small group of design partners.

## Who it is for

- **Hospitals and clinics:** EHR, HIS and OPD systems with patient records, prescriptions and discharge summaries.
- **Diagnostics and labs:** sample tracking, reports and results shared with patients, doctors and partners.
- **Health tech and insurers:** telemedicine, ABDM-linked apps, TPAs and health insurance claims workflows.
- **Other sensitive data:** fintech, HR, education and any team handling children's or financial data.

## Why now

Every organisation processing digital personal data in India is a Data Fiduciary under the Act, with obligations enforced by the Data Protection Board of India.

| | |
|---|---|
| **₹250 Cr** | maximum penalty for failing to take reasonable security safeguards |
| **₹200 Cr** | maximum penalty for failing to notify a personal data breach |
| **72 hrs** | to file a detailed breach report with the Data Protection Board |
| **22** | scheduled Indian languages in which notices can be offered |

## Platform modules

Each module maps to specific duties under the Act and Rules, and every action is written to a tamper-evident audit log.

| Module | What it does | Reference |
|---|---|---|
| Consent and Notice | Purpose-specific consent capture, multilingual notices, one-click withdrawal, embeddable widgets | Sections 5, 6 |
| Data Principal Rights | Hosted portal and API for access, correction, erasure, grievance and nomination, with identity checks and SLA tracking | Sections 11 to 14 |
| AI Data Discovery | Classifies personal data across databases, HL7 and FHIR feeds, PDFs and scanned forms | Section 8 |
| Breach Response | Incident runbooks, Data Principal notifications, pre-filled Board reports | Section 8(6), Rule 7 |
| Retention and Erasure | Policy-driven retention aware of clinical record laws, automated erasure with advance notice | Section 8(7), Rule 8 |
| Children and Guardians | Verifiable parental consent and support for lawful guardians | Section 9, Rules 10, 11 |

## For developers

- **REST API and webhooks** for consent, rights requests and breach events
- **Healthcare connectors** for FHIR R4 and HL7 v2, with ABDM-aware consent flows on the roadmap
- **India data residency**, encrypted at rest and in transit
- **DPO copilot:** an AI assistant that drafts notices, DPIAs and Board reports from your live data map, with citations to the Act

```js
import { DPDPA } from "@dpdpa-suite/node";

const dpdpa = new DPDPA(process.env.DPDPA_API_KEY);

// Capture purpose-specific consent at patient registration
const consent = await dpdpa.consents.create({
  principal: { id: "UHID-20931" },
  purposes: ["treatment", "billing", "lab_reports_sms"],
  notice: { language: "ta", version: "2026-09" },
  channel: "front_desk_tablet",
});
```

*The SDK and API shown are illustrative and not yet publicly available.*

## Compliance timeline

| When | Milestone |
|---|---|
| Nov 2025 | DPDP Rules notified; Data Protection Board constituted |
| Nov 2026 | Consent Manager registration and obligations take effect |
| May 2027 | Full Data Fiduciary obligations apply |

## Roadmap

- **Now (private beta):** consent and notice API, rights request portal, audit log and exports, design partner onboarding
- **Next:** AI data discovery for EHR and LIS, breach response runbooks, FHIR and HL7 connectors, DPO copilot preview
- **Later:** Consent Manager interoperability, DPIA and audit tooling for Significant Data Fiduciaries, self-hosted deployment

## Website and domain

The DPDPA Suite website is currently live at **[printandplan.ink](https://printandplan.ink)**. This is a temporary domain. A professional domain for the startup is under development and will be announced soon. Once it launches, all traffic to printandplan.ink will be redirected to the new domain.

## Early access

We are looking for hospitals, diagnostic chains, health tech teams and other sensitive-data businesses ready to get ahead of May 2027. [Open an early access request](https://github.com/nishanth7885/dpdpa-suite/issues/new?title=Early%20access%20request) and tell us about your stack.

## Disclaimer

DPDPA Suite is under active development and features may change before general availability. Nothing in this repository is legal advice. Penalty amounts and timelines are summarised from the Digital Personal Data Protection Act, 2023 and the DPDP Rules, 2025; refer to official MeitY notifications for authoritative text.
