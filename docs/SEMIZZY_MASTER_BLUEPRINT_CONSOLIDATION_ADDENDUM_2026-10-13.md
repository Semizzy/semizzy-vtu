# Semizzy Master Blueprint Consolidation Addendum
Date: 2026-10-13
Status: Proposed scope consolidation; not a claim that features are implemented or production-ready.

## Purpose
Consolidate the current Semizzy master blueprint, accepted product decisions, and recent dashboard/reliability recommendations. This is additive: preserve all accepted features and existing repository behavior. Do not delete functionality merely because it is not yet implemented. Implement and merge code only after branch-by-branch review, tests, migration review, provider verification, and pull-request approval.

## Product direction
Semizzy is a Nigeria-first VTU, fintech, digital services, and unified marketplace platform. Keep one unified marketplace for physical goods, digital goods, services, classifieds/P2P, bookings/tickets, wholesale and business supplies. Use shared identity, transaction processing, ledger, provider orchestration, risk controls, support, reporting and administration.

## Accepted dashboard and theme system
Provide five selectable design families, each with Day and Night skins:
1. Modern Green & White — recommended default.
2. Premium Navy & Teal.
3. Minimal Blue & White.
4. Obsidian Luxe — black/charcoal and gold accents.
5. Arctic Light — fresh blue and light surfaces.
The admin panel must expose Theme & Appearance settings with previews, Day/Night/system preference, persistent personal preferences, and an authorised global default. Use shared design tokens and accessible contrast, focus, validation, chart, table, dialog and notification components. Theme selection changes presentation only, never feature access or business rules. Admin and customer/seller layouts remain role-appropriate.

## Existing scope to preserve
- Airtime, data, electricity, TV, internet and other configured bill payments.
- Wallet, deposits, bank transfers, withdrawals, virtual accounts where supported, ledger and reconciliation.
- Unified marketplace, seller storefronts, physical/digital products, services, classified/P2P, orders, fulfillment, ratings, disputes and eligible transaction protection.
- Resellers, agents, mini-stores, pricing, commissions and business reporting.
- Dynamic VTU plans across configured Nigerian networks and provider-supported types (SME, Corporate, Gifting, Direct, social/special and other configured types) and provider-defined durations. Show only combinations actually available from providers.
- Optional device biometrics where supported, with normal authentication fallback; never store raw biometric data.
- Admin-configurable registration fields and validation.
- Physical listings with NEW/USED condition.
- Maintained Nigeria states/FCT, LGAs and supported localities, with cascading selection and deduplication.
- Authorised bank-account name enquiry for withdrawals, transfers and saved withdrawal destinations; user confirmation, re-verification after changes, risk controls and audit trail.
- Education, exam preparation, past questions, admissions support and authorised exam-registration workflows.
- Developer APIs, existing payment gateway integrations, Remita, reseller mini-stores and related approved integrations.
- Existing accepted features remain in scope even if their implementation status is unknown.

## Additional recommended features to incorporate
### 1. Fraud and account protection
Risk-based checks for unusual transaction velocity, repeated purchases, suspicious login/device activity, fake payment evidence and unusual withdrawal patterns; step-up verification, alerts, review queues, rate limits, device/session controls, trusted admin access and audit history. Do not make irreversible automated decisions solely from weak signals.

### 2. Transaction recovery centre
Unique references and customer-visible timelines; explicit states for initiation, provider result, settlement and ledger posting; automated status requery; idempotent event handling; safe retry rules; duplicate-purchase prevention; exception queues; eligibility-based refunds; linked support tickets. Never treat a receipt or webhook alone as proof of settlement.

### 3. Profit and business intelligence
Report gross sales, provider costs, actual margins, fees, commissions, refunds, failures, settlement differences and marketplace earnings. Filter by service, provider, network, seller, agent/reseller and time period. Clearly distinguish revenue, cash flow, wallet liabilities and profit.

### 4. Seller/reseller growth tools
Storefront analytics, shareable product links, configurable discounts/campaigns, inventory alerts, reseller pricing tiers, commission reports and order tracking. Apply eligibility, expiry, abuse controls and audit records to promotions.

### 5. Unified support and dispute centre
Link cases to customer, transaction, wallet ledger, marketplace order and seller. Include evidence attachments, severity, ownership, escalation, response-time targets, customer updates and searchable resolution history.

### 6. Operations command centre
Monitor provider health, success/failure rates, latency, payment settlement, reconciliation mismatches, low provider balances and incident events. Provide alerts, incident logs, runbooks and safe maintenance/rollback procedures.

### 7. Rewards and promotions
Configurable cashback, points, referrals, coupons and seller promotions with eligibility rules, caps, expiry, fraud checks, ledger-backed issuance and reversal handling.

### 8. Additional operational capabilities
- Public service-status page and incident history.
- Customer notification centre for in-app, email and SMS messages where configured, with preferences and delivery logs.
- Bulk airtime/data operations with validation, per-item outcomes, idempotency and exportable reports.
- Optional scheduled reminders and recurring purchases only with explicit consent, clear cancellation and provider/payment support.
- Admin global search across customers, transaction references, orders, sellers and support cases with permission-aware results.
- Backup monitoring, tested restore procedures, documented recovery objectives and disaster-recovery exercises.
- Dependency-aware feature flags and staged rollout/rollback controls.
- Developer API documentation, scoped API keys, rotation, rate limits, webhook signature verification and delivery/replay logs.

## Security and financial invariants
- Double-entry ledger, immutable journal history, precision-safe amounts, unique references and no silent balance edits.
- Idempotency, concurrency control, transaction state machines, controlled reversals and compensating entries.
- Signed webhook validation, replay protection, secrets management, sandbox/production separation and redacted logs.
- Maker-checker approvals for sensitive finance/admin actions; least-privilege role permissions and complete audit trails.
- Separate currencies and ledgers; no cross-currency mixing.
- KYC tiers, risk-based limits, account status and provider verification controls.
- Privacy-by-design, data minimisation, retention rules, access controls and incident response.

## Scope filter: exclude or gate
Do not add the following as standalone product modules:
- Dedicated Student Super-Hub.
- Standalone Social Network & Community.
- Standalone Merchant Checkout & Collections module (retain existing gateways, Remita, developer APIs and reseller mini-stores).
- License server, license keys, domain-binding activation, activation licensing or anti-piracy subsystem.
- Services that facilitate account takeover, unauthorised OTP interception or bypassing third-party security.

Keep regulated or partner-dependent capabilities gated until legal/compliance review, authorised providers, operational controls and required approvals are confirmed: lending, investments/trading execution, crypto custody, stored-value products beyond authorised scope, and live escrow funding/holding. Escrow/transaction protection remains in scope for eligible transactions, but real-money holding/release must use an authorised partner and approved legal structure.

## Delivery and acceptance rules
- Treat the master blueprint as target scope, not proof of implementation.
- Inventory both target repositories and their branches before merging code; compare divergent branches and inspect overlapping migrations before any merge.
- Prefer additive changes and a reviewable feature branch/PR. Do not force-push or directly overwrite production branches.
- For each feature, track: Not started / In progress / Implemented / Tested / Provider-verified / Production-ready. Only mark a status when evidence supports it.
- Run automated tests, security checks, migration compatibility checks, and sandbox/provider contract tests. Verify recovery, duplicate requests, webhook replay, refunds and reconciliation.
- Do not delete existing accepted features. Exclusions above are scope boundaries, not a request to remove unrelated working functionality.
