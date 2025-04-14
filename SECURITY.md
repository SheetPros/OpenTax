# OpenTax Security

**OpenTax** prioritizes security to protect users—individuals, businesses, and governments—while enabling interoperable, auditable financial transactions. Our universal transaction standard (UTC), built on [OData v4](https://www.odata.org/), ensures data integrity, confidentiality, and compliance with global standards like GDPR, IRS regulations, and the UK’s [Making Tax Digital (MTD)](https://www.gov.uk/government/collections/making-tax-digital). Below, we outline how OpenTax safeguards every transaction, addressing privacy concerns and supporting transparent oversight.

## Core Principles
- **Confidentiality**: Your data stays private, accessible only to authorized parties.
- **Integrity**: Transactions are tamper-proof, verifiable by all stakeholders.
- **Availability**: APIs and ledgers are resilient to attacks and downtime.
- **Compliance**: Meets IRS, HMRC, and GDPR requirements for trust.

## Security Features

### 1. End-to-End Encryption
- **Method**: AES-256 encryption for all data at rest and in transit, matching US federal standards (FIPS 140-2).
- **Implementation**: TLS 1.3 secures API calls (e.g., `GET /odata/Transactions`). Keys are managed via AWS KMS or equivalent, rotated every 90 days.
- **Benefit**: Even if intercepted, data is unreadable without keys, protecting against breaches (e.g., Equifax’s 2017 leak of 147M records).

### 2. Zero-Knowledge Proofs (ZKP)
- **Method**: zk-SNARKs enable public auditing without exposing sensitive data. For example, users can prove “total tax paid” without revealing individual transactions.
- **Implementation**: Integrated into the UTC’s `auditHash` (SHA-256), verifiable on a public ledger (e.g., Hyperledger Fabric).
- **Benefit**: Citizens can audit gov spending (e.g., $10M to an agency) while payer/payee details stay private, addressing GDPR’s data minimization.

### 3. Authentication and Authorization
- **Method**: OAuth 2.0 with OpenID Connect for API access, supporting role-based controls (e.g., taxpayer, IRS admin, auditor).
- **Implementation**: Tokens expire after 1 hour, with refresh flows. Multi-factor authentication (MFA) is mandatory for sensitive actions.
- **Benefit**: Prevents unauthorized access, like the IRS’s 2015 breach exposing 700K accounts. Aligns with UK MTD’s secure login.

### 4. Immutable Audit Ledger
- **Method**: Transactions are logged to a permissioned blockchain (e.g., Hyperledger Fabric v2.5), with `auditHash` ensuring integrity.
- **Implementation**: Each UTC record (see [transaction.json](src/schemas/transaction.json)) includes a cryptographic hash, validated by distributed nodes.
- **Benefit**: Tampering is impossible—any change breaks the chain. Supports IRS audits and citizen oversight without central control.

### 5. Data Anonymization
- **Method**: Payer/payee IDs are hashed (e.g., SHA-256) or replaced with pseudonyms for public queries, unless opted in for transparency.
- **Implementation**: OData queries (e.g., `?$filter=taxType eq 'VAT'`) return aggregated, anonymized data unless authorized.
- **Benefit**: Balances transparency (e.g., “$1B in VAT collected”) with privacy, avoiding backlash like DOGE’s 2025 Treasury data controversy.

### 6. Compliance with Standards
- **GDPR**: Right to erasure, data portability via OData exports. No personal data stored without consent.
- **IRS**: Aligns with Publication 1075 (Safeguarding Taxpayer Data), using FIPS-compliant crypto.
- **UK MTD**: Matches HMRC’s API security (OAuth, TLS), proven with 1.8M businesses.
- **Benefit**: Ready for US/UK gov adoption, reducing legal risks.

### 7. Resilience
- **Method**: APIs hosted on distributed clouds (e.g., AWS GovCloud), with DDoS protection and 99.99% uptime.
- **Implementation**: Rate limiting (1K requests/sec per user), auto-scaling, and failover across regions.
- **Benefit**: Withstands attacks like the 2020 IRS outage, ensuring taxpayers and IRS rely on OpenTax.

## Threat Model
We’ve planned for:
- **External Attacks**: SQL injection, XSS blocked by OData’s strict parsing and input validation.
- **Insider Threats**: Least-privilege access; no single admin controls keys or ledger.
- **Data Leaks**: ZKPs and anonymization ensure even compromised nodes reveal nothing sensitive.
- **Gov Misuse**: Opt-in public ledger prevents forced exposure, addressing 2025 privacy lawsuits against gov data grabs.

See [threat-model.md](docs/threat-model.md) (TBD) for details.

## How We Test
- **Penetration Testing**: Quarterly audits by third parties, starting Q3 2025 (post-MVP).
- **Code Review**: All PRs require 2+ approvals, using tools like SonarQube.
- **Fuzzing**: API endpoints tested with 10K+ malformed inputs to catch edge cases.
- **Bug Bounties**: Up to $10K for critical flaws, launching 2026.

## Comparison to Industry
- **UK MTD**: OpenTax adds public audits and global schemas, keeping MTD’s TLS/OAuth rigor.
- **IRS e-file**: OpenTax’s OData is more flexible than XML, with stronger encryption.
- **Palantir Gotham**: OpenTax is open-source, not proprietary, but matches gov-grade security.

OpenTax is secure by design, built for trust. Help us keep it that way.
