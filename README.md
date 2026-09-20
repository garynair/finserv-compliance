# FinServ Compliance

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC0-1.0](https://img.shields.io/badge/license-CC0--1.0-lightgrey.svg)](LICENSE)

A curated list of regulations, supervisory guidance, and tooling for **US financial-services compliance** — the overlapping banking, securities, and financial-crimes regulatory perimeter that governs banks, broker-dealers, and non-bank financial institutions.

**Scope:** Anything that materially helps a practitioner scope, implement, or examine against US financial-services regulatory obligations — banking safeguards, state cybersecurity rules, securities and broker-dealer requirements, AML/sanctions compliance, model risk management, and the prudential-regulator examination framework built around them. PCI-DSS (payment card security) and SOX/ITGC/COBIT (financial-reporting and IT governance controls) sit outside this list's scope and are covered by the companion Security Frameworks and IT Audit & Controls lists (see Related Lists).

**Why now:** The supervisory baseline shifted materially across 2025 and 2026. The FFIEC formally sunset its Cybersecurity Assessment Tool on 31 August 2025, directing institutions toward NIST CSF 2.0, the Cyber Risk Institute Profile, and other established frameworks instead of a bespoke checklist. The Federal Reserve, OCC, and FDIC then jointly rescinded SR 11-7 — the model risk management guidance that had stood since 2011 — replacing it with SR 26-2 on 17 April 2026, a more risk-based standard aimed at correcting over-application of the original guidance, particularly at community banks. NYDFS's own Part 500 amendments reached full effect in November 2025, and the department issued fresh guidance on cybersecurity risk assessments as recently as 10 September 2026 — so several of the frameworks below are considerably newer than their headline names suggest.

Contributions welcome.

---

## Contents

- [Why These Frameworks Matter](#why-these-frameworks-matter)
- [How to Approach Implementation](#how-to-approach-implementation)
- [GLBA and FFIEC](#glba-and-ffiec)
- [NYDFS 500](#nydfs-500)
- [SEC and FINRA](#sec-and-finra)
- [BSA, AML, and Sanctions](#bsa-aml-and-sanctions)
- [Model Risk Management (SR 11-7)](#model-risk-management-sr-11-7)
- [Prudential Regulators](#prudential-regulators)
- [Dodd-Frank Act and the Volcker Rule](#dodd-frank-act-and-the-volcker-rule)
- [Community Reinvestment Act (CRA)](#community-reinvestment-act-cra)
- [Cross-Framework Mapping and GRC Platforms](#cross-framework-mapping-and-grc-platforms)
- [Assessment, Audit, and Risk Analysis Resources](#assessment-audit-and-risk-analysis-resources)
- [Certifications and Training](#certifications-and-training)
- [Government and Standards Bodies](#government-and-standards-bodies)
- [Learning Resources](#learning-resources)
- [Related Lists](#related-lists)

---

## Why These Frameworks Matter

Financial services compliance does not have a single statute or a single certifiable framework the way healthcare has HIPAA and HITRUST. A bank, broker-dealer, or non-bank lender typically answers to several regulators at once: a safety-and-soundness supervisor (the Federal Reserve, OCC, or FDIC, depending on charter), a market-conduct regulator (the SEC and FINRA for anything touching securities), a state regulator (NYDFS for any institution operating in New York, or a state-adopted NAIC model law for insurers), and a financial-crimes regulator (FinCEN and OFAC, regardless of charter). Each imposes its own safeguards, examination cycle, and enforcement mechanism, and no HITRUST-equivalent body exists to combine them into one assessable control set a vendor can point to.

In practice, most financial-services compliance programmes are built in two layers. The sector-specific obligations in this list — GLBA/FFIEC, NYDFS 500, SEC/FINRA rules, BSA/AML and sanctions, SR 11-7 (now SR 26-2), and the prudential examination manuals — define what a regulator will actually test for. On top of that, most institutions run a general-purpose control framework, typically NIST CSF or ISO/IEC 27001 (covered by the companion [Security Frameworks](https://github.com/garynair/security-frameworks) list), to organise day-to-day security operations and give examiners a familiar structure to map findings against. Neither layer replaces the other: passing a NIST CSF assessment does not satisfy a GLBA Safeguards Rule examination, and vice versa.

---

## How to Approach Implementation

1. **Determine your regulatory perimeter.** Identify which agency charters and examines you (Federal Reserve, OCC, FDIC, NCUA, or a state regulator), whether you fall under FTC or SEC jurisdiction instead of a prudential regulator, and whether NYDFS or another state cyber regulation applies based on where you are licensed to do business.
2. **Run a GLBA-driven risk assessment.** The Safeguards Rule requires a written risk assessment covering the confidentiality, integrity, and availability of customer information — document it the same way you would for any other mandatory risk-analysis regime.
3. **Map a baseline security framework underneath the sector rules.** Most institutions run NIST CSF or ISO/IEC 27001 (see the companion Security Frameworks list) since none of GLBA, NYDFS 500, or the FFIEC handbook prescribes a full control catalogue on its own.
4. **Build the BSA/AML programme in parallel.** A written, board-approved AML programme with a designated compliance officer, employee training, independent testing, and customer due diligence procedures is a distinct, mandatory workstream from information-security compliance.
5. **Stand up sanctions screening.** Screen customers, counterparties, and transactions against the OFAC SDN list and other sanctions lists, structured around OFAC's five-pillar compliance framework.
6. **Scope model risk management separately if you use quantitative models.** If you are supervised by the Federal Reserve, OCC, or FDIC and rely on models for credit decisioning, stress testing, or trading, build a model inventory and validation programme against the current interagency guidance — SR 26-2, which superseded SR 11-7 in April 2026.
7. **Satisfy state cyber regulation where it applies.** DFS-licensed entities must meet 23 NYCRR Part 500's specific requirements (CISO designation, MFA, encryption, 72-hour breach notification, annual certification); insurers elsewhere should check whether their state has adopted the NAIC Insurance Data Security Model Law.
8. **Layer on securities-specific obligations if applicable.** Broker-dealers, investment advisers, and public companies carry additional disclosure and privacy obligations under SEC rules (cybersecurity incident disclosure, Regulation S-P, Regulation S-ID) and FINRA guidance that sit on top of, not instead of, the safeguards above.
9. **Prepare for CRA and fair-lending examinations if you are a depository institution.** These are periodic, rated examinations distinct from the security- and privacy-focused work above, and the underlying rule is currently being revised.
10. **Monitor continuously and expect the guidance to keep moving.** Several pillars of this list changed materially between 2025 and 2026 (the FFIEC retired the CAT, the banking agencies rewrote model risk guidance, NYDFS issued new risk-assessment guidance) — treat "final" guidance as provisional and track the regulators' own bulletins and SR letters directly.

---

## GLBA and FFIEC

**Applicability:** the GLBA Safeguards Rule is mandatory for non-bank financial institutions under FTC jurisdiction; FFIEC guidance applies to banks, thrifts, and credit unions examined by the FFIEC member agencies. Not certifiable — there is no official "GLBA certified" status.

- [FFIEC Cybersecurity Assessment Tool (Retired)](https://www.ffiec.gov/news/press-releases/2024/an-09-29) - The FFIEC's official notice sunsetting the CAT on 31 August 2025 and redirecting institutions to NIST CSF 2.0, the CRI Profile, CISA's Cybersecurity Performance Goals, and the CIS Controls. Read this before building a self-assessment programme around the retired tool.
- [FFIEC IT Examination Handbook InfoBase](https://ithandbook.ffiec.gov/) - The interagency examiner reference covering information security, business continuity, development and acquisition, management, and outsourcing, used across all FFIEC member-agency examinations.
- [FTC Safeguards Rule](https://www.ftc.gov/legal-library/browse/rules/safeguards-rule) - The regulation implementing GLBA's information-security mandate for financial institutions under FTC jurisdiction, amended in 2021 and again in 2023 to add a breach-notification requirement effective May 2024.
- [FTC Safeguards Rule: What Your Business Needs to Know](https://www.ftc.gov/business-guidance/resources/ftc-safeguards-rule-what-your-business-needs-know) - The FTC's plain-language compliance guide walking through each required element of the information security programme.
- [Gramm-Leach-Bliley Act](https://www.ftc.gov/business-guidance/privacy-security/gramm-leach-bliley-act) - The FTC's hub for the 1999 statute establishing the Privacy Rule and Safeguards Rule, the starting point for understanding which of a financial institution's obligations flow from GLBA itself.

## NYDFS 500

**Applicability:** mandatory for DFS-regulated entities (banks, insurers, and other financial services companies licensed in New York); not certifiable, but requires an annual Certification of Compliance filed with the Superintendent.

- [23 NYCRR Part 500 (Cybersecurity Regulation)](https://www.dfs.ny.gov/cybersecurity/23-NYCRR-Part-500) - New York's first-in-the-nation cybersecurity regulation for financial services companies, in effect since March 2017 and amended twice since, most recently reaching full effect in November 2025.
- [Cybersecurity Program Template](https://www.dfs.ny.gov/system/files/documents/2025/02/Cybersecurity-Program-Template-05.2024.pdf) - DFS's official template to help smaller, Class A-exempt, or individual licensees build a Part 500-compliant cybersecurity programme without a large compliance function.
- [DFS Guidance on Cybersecurity Risk Assessments](https://www.dfs.ny.gov/reports_and_publications/press_releases/pr20260910) - New guidance issued 10 September 2026 clarifying DFS's expectations for risk-assessment governance, methodology, scope, and documentation, including treatment of third-party and AI-related risk.
- [NAIC Insurance Data Security Model Law](https://content.naic.org/insurance-topics/cybersecurity) - The National Association of Insurance Commissioners' model law, closely based on Part 500 and adopted by roughly half the states, relevant to any insurer not directly captured by NYDFS.
- [NYDFS Cybersecurity FAQs](https://www.dfs.ny.gov/cybersecurity/faqs) - DFS's official answers to common questions about covered-entity status, exemptions, and compliance obligations under Part 500.

## SEC and FINRA

**Applicability:** mandatory for SEC-registered public companies, broker-dealers, investment advisers, and FINRA member firms; enforced through SEC rulemaking and FINRA's self-regulatory examination programme.

- [FINRA 2026 Annual Regulatory Oversight Report: Cybersecurity and Cyber-Enabled Fraud](https://www.finra.org/rules-guidance/guidance/reports/2026-finra-annual-regulatory-oversight-report/cybersecurity) - FINRA's current-year summary of examination findings and effective practices, the closest thing to an annual state-of-the-industry cybersecurity report for member firms.
- [FINRA Cybersecurity](https://www.finra.org/rules-guidance/key-topics/cybersecurity) - FINRA's key-topics hub consolidating regulatory notices, advisories, and exam findings on cybersecurity for broker-dealers.
- [FINRA Small Firm Cybersecurity Checklist](https://www.finra.org/compliance-tools/cybersecurity-checklist) - A free, practical starting-point checklist FINRA built specifically for small member firms without a dedicated security team.
- [SEC Cybersecurity Risk Management, Strategy, Governance, and Incident Disclosure](https://www.sec.gov/resources-small-businesses/small-business-compliance-guides/cybersecurity-risk-management-strategy-governance-incident-disclosure) - The SEC's small-entity compliance guide to its 2023 rule requiring material-incident disclosure on Form 8-K within four business days and annual cybersecurity risk-governance disclosure.
- [SEC Regulation S-ID: Identity Theft Red Flags Rules](https://www.sec.gov/resources-small-businesses/small-business-compliance-guides/identity-theft-red-flags-rules) - The rule requiring covered broker-dealers, investment companies, and advisers to maintain a written identity-theft prevention programme, with recent SEC enforcement actions underlining its relevance.
- [SEC Regulation S-P: Small Entity Compliance Guide](https://www.sec.gov/files/rules/final/2024/regulation-s-p-small-entity-compliance-guide.pdf) - The SEC's guide to its May 2024 amendments requiring an incident-response programme and a 30-day customer-notification deadline for breaches of sensitive customer information.

## BSA, AML, and Sanctions

**Applicability:** mandatory for banks and other "financial institutions" as defined by the Bank Secrecy Act; OFAC sanctions compliance is a strict-liability obligation for all US persons regardless of sector.

- [A Framework for OFAC Compliance Commitments](https://ofac.treasury.gov/media/16331/download) - OFAC's May 2019 guidance describing the five components (management commitment, risk assessment, internal controls, testing and auditing, training) OFAC expects of a sanctions compliance programme, and the document it references when evaluating enforcement actions.
- [Bank Secrecy Act](https://www.fincen.gov/resources/statutes-and-regulations/bank-secrecy-act) - FinCEN's hub for the 1970 statute underpinning US AML law, requiring recordkeeping and reporting (CTRs, SARs) from covered financial institutions.
- [FinCEN Anti-Money Laundering Programs and Records](https://www.fincen.gov/resources/statutes-regulations/guidance/anti-money-laundering-programs-and-records-english) - FinCEN's guidance on the AML Program Rule's core requirements: written policies, a designated compliance officer, training, and independent testing.
- [OFAC Specially Designated Nationals and Blocked Persons List (SDN List)](https://ofac.treasury.gov/specially-designated-nationals-and-blocked-persons-list-sdn-human-readable-lists) - The primary sanctions list financial institutions must screen against, updated on a rolling basis with no fixed schedule.

## Model Risk Management (SR 11-7)

**Applicability:** supervisory guidance, not a binding rule, for banking organisations supervised by the Federal Reserve, OCC, or FDIC that use quantitative models in decision-making; proportionate to an institution's size and model risk profile. SR 11-7 itself was superseded in April 2026 — see below.

- [FDIC: Agencies Revise the Interagency Model Risk Management Guidance](https://www.fdic.gov/news/financial-institution-letters/2026/agencies-revise-interagency-model-risk-management-guidance) - The FDIC's Financial Institution Letter announcing the joint rescission of SR 11-7 and its replacement, aimed at resetting a more proportionate, risk-based standard.
- [OCC Bulletin 2026-13: Model Risk Management — Revised Guidance](https://www.occ.gov/news-issuances/bulletins/2026/bulletin-2026-13.html) - The OCC's issuance of the revised guidance, explicitly rescinding Bulletin 2011-12 and stating the new guidance does not yet cover generative or agentic AI models.
- [SR 11-7: Guidance on Model Risk Management (2011, superseded)](https://www.federalreserve.gov/boarddocs/srletters/2011/sr1107.pdf) - The original 2011 Federal Reserve/OCC guidance that defined model risk management for banking for fifteen years; retained here for historical context, since much existing literature and internal policy still cites it by name.
- [SR 26-2: Revised Guidance on Model Risk Management (current)](https://www.federalreserve.gov/supervisionreg/srletters/SR2602.htm) - The Federal Reserve's letter issued 17 April 2026, which explicitly supersedes and replaces SR 11-7 with a guidance tailored to a banking organisation's size, complexity, and extent of model use.

## Prudential Regulators

The four agencies below layer safety-and-soundness and consumer-protection supervision on top of the framework-specific obligations above; their examination manuals are where those obligations get operationalised in day-to-day examinations.

- [CFPB Supervision and Examination Manual](https://www.consumerfinance.gov/compliance/supervision-examinations/) - The Consumer Financial Protection Bureau's guide for examiners assessing compliance with federal consumer financial law, including compliance-management-system expectations.
- [FDIC Risk Management Manual of Examination Policies](https://www.fdic.gov/risk-management-manual-examination-policies) - The FDIC's examiner manual covering CAMELS-based risk-focused supervision, organised into basic concepts, ratings, other examination issues, and enforcement actions.
- [Federal Reserve Bank Holding Company Supervision Manual](https://www.federalreserve.gov/publications/supervision_bhc.htm) - The Federal Reserve's guidance for inspecting bank holding companies and their nonbank subsidiaries, the largest segment of institutions it supervises.
- [Federal Reserve Consumer Compliance Handbook](https://www.federalreserve.gov/boarddocs/supmanual/cch/cch.pdf) - The Fed's examiner handbook covering consumer compliance and CRA examinations, updated on a semiannual cycle.
- [OCC Comptroller's Handbook](https://www.occ.gov/publications-and-resources/publications/comptrollers-handbook/index-comptrollers-handbook.html) - The OCC's examiner reference for national banks and federal savings associations, organised into safety-and-soundness, asset-management, consumer-protection, and specialty series.

## Dodd-Frank Act and the Volcker Rule

**Applicability:** Dodd-Frank provisions apply broadly across banking, securities, and derivatives markets depending on institution size and activity; the Volcker Rule specifically applies to "banking entities" engaged in proprietary trading or fund sponsorship.

- [Dodd-Frank Wall Street Reform and Consumer Protection Act (Full Text)](https://www.congress.gov/bill/111th-congress/house-bill/4173/text) - The official text of the 2010 statute (P.L. 111-203), the source document for every provision summarised elsewhere in this section.
- [Dodd-Frank Wall Street Reform and Consumer Protection Act: Background and Summary](https://www.congress.gov/crs-product/R41350) - The Congressional Research Service's plain-language summary of the act's major titles, useful as a map before reading specific provisions.
- [Federal Reserve Board: Volcker Rule](https://www.federalreserve.gov/supervisionreg/volcker-rule.htm) - The Fed's hub on Section 619's restrictions on proprietary trading and fund sponsorship, including the 2019 and 2020 interagency revisions.
- [OCC: Volcker Rule Implementation](https://www.occ.gov/topics/supervision-and-examination/capital-markets/financial-markets/trading-volcker-rule/volcker-rule-implementation.html) - The OCC's implementation guidance and FAQs for national banks subject to the Volcker Rule's trading and covered-fund restrictions.

## Community Reinvestment Act (CRA)

**Applicability:** mandatory for federally insured depository institutions; enforced through periodic CRA examinations and a rated performance record, not certification.

- [FDIC: Agencies Issue Joint Proposal Amending the Community Reinvestment Act Rules](https://www.fdic.gov/news/press-releases/2026/agencies-issue-joint-proposal-amending-community-reinvestment-act-rules) - The OCC and FDIC's July 2026 joint proposal to raise asset thresholds, reduce data-collection burden for community banks, and rescind the enjoined 2023 CRA final rule.
- [FDIC: Community Reinvestment Act (CRA)](https://www.fdic.gov/banker-resource-center/community-reinvestment-act-cra) - The FDIC's practitioner hub for CRA examination schedules, performance evaluations, and related guidance.
- [Federal Reserve: Community Reinvestment Act (CRA)](https://www.federalreserve.gov/consumerscommunities/cra_about.htm) - The Federal Reserve's overview of the 1977 law's purpose, evaluation process, and how CRA performance factors into merger and expansion applications.
- [OCC Bulletin 2026-35: Community Reinvestment Act Interagency Notice of Proposed Rulemaking](https://www.occ.gov/news-issuances/bulletins/2026/bulletin-2026-35.html) - The OCC's issuance of the 2026 interagency CRA proposal, with a public comment period, worth tracking given the rule's history of litigation and reversal since 2023.

---

## Cross-Framework Mapping and GRC Platforms

- [Ascent RegTech (AscentAI)](https://www.ascentregtech.com/) - Commercial regulatory-lifecycle-management platform that tracks 400,000+ regulatory obligations across jurisdictions and maintains a firm-specific obligations register, useful for change management across the overlapping regulators above.
- [Fenergo](https://www.fenergo.com/regulatory-compliance) - Commercial client-lifecycle-management platform covering KYC, onboarding, and regulatory compliance workflows for banks and other regulated financial institutions.
- [Mitratech Continuity](https://mitratech.com/products/continuity/) - Commercial RegTech suite purpose-built for banks and credit unions, combining regulatory-change monitoring (RegAdvisor Pro), controls management, and vendor-risk tracking.
- [Ncontracts](https://www.ncontracts.com/) - Commercial compliance, risk, and vendor-management platform for financial institutions, covering compliance-management-system documentation, BSA/AML workflows, and examination-finding tracking.
- [NICE Actimize](https://www.niceactimize.com/) - Commercial financial-crime platform covering AML transaction monitoring, sanctions screening, and customer due diligence, widely deployed for BSA/AML and OFAC compliance workflows.
- [Secure Controls Framework (SCF)](https://securecontrolsframework.com/) - Free, open (Creative Commons) meta-framework mapping outward to 250+ laws and regulations, including explicit GLBA and NYDFS control mappings. Shared with the companion [Security Frameworks](https://github.com/garynair/security-frameworks) and [IT Audit & Controls](https://github.com/garynair/it-audit-controls) lists.
- [Wolters Kluwer OneSumX](https://www.wolterskluwer.com/en/solutions/onesumx-for-compliance-program-management) - Commercial compliance-program-management platform for financial institutions, covering regulatory-change tracking, policy management, and risk and control self-assessment across multiple regulators.

---

## Assessment, Audit, and Risk Analysis Resources

- [FFIEC BSA/AML Examination Manual](https://bsaaml.ffiec.gov/manual) - The interagency examiner manual specifying exactly what examiners test for during BSA/AML and OFAC examinations, the closest thing to an official BSA/AML audit protocol.
- [FFIEC Uniform Bank Performance Report (UBPR)](https://www.ffiec.gov/data/ubpr) - A free analytical tool built from quarterly Call Report data, used by examiners and institutions to benchmark a bank's earnings, liquidity, capital, and growth against peer groups.
- [OCC Bulletin 2026-22: Proposed Revisions to the Uniform Financial Institutions Rating System](https://www.occ.gov/news-issuances/bulletins/2026/bulletin-2026-22.html) - A 2026 interagency proposal to revise the CAMELS rating methodology, worth tracking for any institution preparing for its next safety-and-soundness examination.
- [Uniform Financial Institutions Rating System (CAMELS)](https://www.federalreserve.gov/boarddocs/supmanual/cbem/200904/A50201.pdf) - The Federal Reserve's official description of the CAMELS composite rating (Capital, Asset quality, Management, Earnings, Liquidity, Sensitivity to market risk) that underlies every prudential safety-and-soundness examination.

---

## Certifications and Training

- [ABA Certified Regulatory Compliance Manager (CRCM)](https://www.aba.com/training-events/certifications/certified-regulatory-compliance-manager) - The American Bankers Association's flagship banking-compliance designation, covering lending, deposit, financial-crimes, privacy, and CRA regulation.
- [ACAMS Certified Anti-Money Laundering Specialist (CAMS)](https://www.acams.org/en/certifications/cams-certification) - The globally recognised AML competency credential, the most widely held qualification for BSA/AML compliance officers and analysts.
- [ACAMS Certified Global Sanctions Specialist (CGSS)](https://www.acams.org/en/certifications/certified-global-sanctions-specialist-cgss) - ACAMS's sanctions-specific credential, aligned closely with the OFAC compliance-programme work in the BSA, AML, and Sanctions section above.
- [ACFCS Certified Financial Crime Specialist (CFCS)](https://www.acfcs.org/certification-overview) - The Association of Certified Financial Crime Specialists' broader financial-crime credential, covering AML, fraud, sanctions, and anti-bribery in a single exam.

---

## Government and Standards Bodies

- [Board of Governors of the Federal Reserve System](https://www.federalreserve.gov/) - The central bank and primary federal supervisor of bank holding companies and state member banks, publisher of the SR letter series.
- [Consumer Financial Protection Bureau (CFPB)](https://www.consumerfinance.gov/) - The federal agency responsible for enforcing consumer financial protection law across banks, credit unions, and non-bank lenders.
- [Federal Deposit Insurance Corporation (FDIC)](https://www.fdic.gov/) - The federal deposit insurer and primary supervisor of state-chartered banks that are not members of the Federal Reserve System.
- [Federal Financial Institutions Examination Council (FFIEC)](https://www.ffiec.gov/) - The interagency body (Fed, FDIC, NCUA, OCC, CFPB, plus a state-regulator liaison) that sets uniform examination principles and publishes the IT Examination Handbook.
- [Financial Crimes Enforcement Network (FinCEN)](https://www.fincen.gov/) - The Treasury bureau that administers the Bank Secrecy Act and collects, analyses, and disseminates financial-intelligence data.
- [Financial Industry Regulatory Authority (FINRA)](https://www.finra.org/) - The self-regulatory organisation overseeing US broker-dealers, responsible for licensing, rulemaking, and examinations.
- [New York State Department of Financial Services (NYDFS)](https://www.dfs.ny.gov/) - The New York state regulator that promulgated 23 NYCRR Part 500 and supervises banks and insurers licensed in New York.
- [Office of Foreign Assets Control (OFAC)](https://ofac.treasury.gov/) - The Treasury office that administers and enforces US economic and trade sanctions programmes.
- [Office of the Comptroller of the Currency (OCC)](https://www.occ.gov/) - The Treasury bureau that charters, regulates, and supervises national banks and federal savings associations.
- [U.S. Securities and Exchange Commission (SEC)](https://www.sec.gov/) - The federal agency responsible for securities-market regulation, including public-company disclosure rules and broker-dealer and investment-adviser oversight.

---

## Learning Resources

- [FDIC Banker Resource Center](https://www.fdic.gov/banker-resource-center) - The FDIC's hub of free supervisory resources for bankers, including CRA, cybersecurity, and capital-markets material.
- [FFIEC Cybersecurity Awareness](https://www.ffiec.gov/resources/cybersecurity-awareness) - The FFIEC's practitioner-facing hub of cybersecurity resources for financial institutions, updated as guidance and tools change.
- [OFAC Frequently Asked Questions](https://ofac.treasury.gov/faqs) - OFAC's official, searchable FAQ database, the fastest way to resolve a specific sanctions-compliance question with an authoritative answer.
- [SEC Small Business Compliance Guides](https://www.sec.gov/resources-small-businesses/small-business-compliance-guides) - The SEC's library of plain-language compliance guides for smaller entities, covering everything from cybersecurity disclosure to Regulation S-P.

---

## Related Lists

- [Healthcare Compliance](https://github.com/garynair/healthcare-compliance) - A companion curated list covering HIPAA, HITECH, and HITRUST CSF, the healthcare-sector equivalent of this list.
- [IT Audit & Controls](https://github.com/garynair/it-audit-controls) - A companion curated list covering COBIT, COSO, and ITGC/ITAC — the source for anything SOX-, ITGC-, or COBIT-related that is out of scope here.
- [Security Frameworks](https://github.com/garynair/security-frameworks) - A companion curated list covering NIST CSF, ISO/IEC 27001, and PCI-DSS — the source for the general-purpose control framework most institutions layer underneath the sector-specific obligations above.

---

## Contributing

PRs welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for the criteria a new entry must meet.

## Licence

This list is published under [CC0 1.0 Universal](LICENSE). The linked resources retain their own licences.
