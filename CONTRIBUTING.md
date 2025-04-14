# Contributing to OpenTax

Welcome to **SheetPros/OpenTax**! We’re building a free, [OData-based](https://www.odata.org/) universal transaction standard, inspired by the UK’s [Making Tax Digital](https://www.gov.uk/government/collections/making-tax-digital), to streamline finance, save $80 billion in tax costs, and ensure fair, secure oversight. Licensed under [Apache 2.0](LICENSE), OpenTax invites everyone—developers, accountants, policy experts—to unify accounting for all.

Your contributions can shape a transparent, efficient future. Whether you’re coding APIs, securing ledgers, or mapping tax codes, we need you. Let’s make finance work for everyone!

## How to Contribute

We value all input, from bug reports to code. Here’s how to jump in:

### 1. Get Started
- **Star the repo**: Show support at [github.com/SheetPros/OpenTax](https://github.com/SheetPros/OpenTax).
- **Read the docs**:
  - [README.md](README.md): Project vision and setup.
  - [security.md](docs/security.md): Encryption and compliance details.
  - [overview.md](docs/overview.md): UK inspiration and goals.
- **Join Discussions**: Share ideas in [GitHub Discussions](https://github.com/SheetPros/OpenTax/discussions).

### 2. Find a Task
Browse [Issues](https://github.com/SheetPros/OpenTax/issues) for open tasks, tagged by skill:
- **Code**: Build APIs, ledgers, or ZKP integrations.
- **Security**: Harden encryption, test vulnerabilities.
- **Tax Logic**: Map US/UK tax codes to UTC.
- **Docs**: Improve guides, translate for global use.

Try these starter issues:
- `#1`: Add sample VAT transaction to [transaction.json](src/schemas/transaction.json).
- `#2`: Write unit tests for OData queries in [demo.js](src/api/demo.js).
- `#3`: Suggest GDPR tweaks in [security.md](docs/security.md).

No task? Propose one in Discussions!

### 3. Submit Your Work
1. **Fork the repo**: `git clone https://github.com/YourUser/OpenTax.git`.
2. **Create a branch**: `git checkout -b feature/your-idea`.
3. **Code**:
   - Follow [JavaScript](https://www.w3schools.com/js/js_conventions.asp) or [Rust](https://www.rust-lang.org/policies/code-of-conduct) style guides.
   - Use Node.js for APIs, Rust/Go for ledgers, Python for tax logic.
   - Test locally: `npm test` or `cargo test`.
4. **Commit**: Write clear messages, e.g., “Add ZKP to auditHash validation”.
5. **Push & PR**: Open a Pull Request with:
   - Title: “Feature: Add X to Y”.
   - Description: Why it helps OpenTax (e.g., “Enables IRS auditability”).
   - Link to issue (e.g., “Fixes #1”).
6. **Review**: Expect 2+ approvals. We’ll provide feedback within 48 hours.

### 4. Code of Conduct
- Be respectful, inclusive, and collaborative, per [Contributor Covenant](https://www.contributor-covenant.org/version/2/0/code_of_conduct/).
- No harassment—let’s unify finance, not divide people.
- Report issues to conduct@opentax.dev (TBD).

### 5. What We Need
- **Developers**:
  - **APIs**: Extend OData endpoints (Node.js, Express).
  - **Ledger**: Build Hyperledger Fabric nodes (Rust, Go).
  - **Security**: Code zk-SNARKs for audits (Circom, WebAssembly).
  - **Tests**: Write Jest or Mocha suites for [demo.js](src/api/demo.js).
- **Accountants**: Map IRS 1040, UK SA100, or VAT codes to [transaction.json](src/schemas/transaction.json).
- **Policy Experts**: Ensure GDPR, IRS Pub 1075 compliance in [security.md](docs/security.md).
- **Writers**: Clarify docs for non-tech users (e.g., SMEs).

No experience? Try docs or bug reports—every bit counts!

### 6. Bounties & Recognition
- **Bounties**: Starting 2026, earn up to $10K for critical fixes (e.g., security bugs) or features (e.g., IRS API integration).
- **Shoutouts**: Top contributors get featured on our [X posts](#AmericanStandard) and README’s “Hall of Fame”.
- **Impact**: Your code could save billions and empower citizens to audit gov spending.

### 7. Why Contribute?
- **Impact**: Help cut $80B in tax costs, easing burdens for 150M US taxpayers.
- **Tech**: Work on OData, blockchain, and ZKPs—skills that shine for Palantir or IRS gigs.
- **Community**: Join a bi-partisan effort to make finance fair, inspired by UK’s 1.8M-business MTD success.
- **Timing**: Gov APIs are hot (see IRS’s 2025 push)—be part of the change.

## Questions?
- **Issues**: File bugs or ideas at [GitHub Issues](https://github.com/SheetPros/OpenTax/issues).
- **Chat**: Join [Discussions](https://github.com/SheetPros/OpenTax/discussions) or tweet #AmericanStandard.
- **Email**: opentax.devs@gmail.com (TBD).

Thank you for building OpenTax—let’s unify finance, securely and fairly!
