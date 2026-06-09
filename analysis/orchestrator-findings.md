# Orchestrator Analysis Findings - 2026-06-09

## Top 5 Risks
1. **Acme Corp Production Stability**: Critical outage (June 01) and unresolved batch job issues in UTC+7. Pipeline shows conflicting stages and ARR mismatch (20k vs 50k).
2. **Meridian Systems Security**: Critical security escalation in Google Sheets regarding suspected unauthorized API access; requiring incident report within 24h. This account is missing from GitHub.
3. **Summit Finance Billing Integrity**: Critical invoice mismatch (May 09). Pipeline shows conflicting stages and "billing reconciled" status in Sheets despite missing GitHub confirmation.
4. **Pioneer Health Compliance/Audit**: High severity feedback regarding audit log export (May 07). Release notes claim GA, but pipeline inconsistencies persist.
5. **Nova Retail Data Quality & Onboarding**: Duplicate customer records (May 18) and SSO configuration issues. Release notes claim SSO auto-config is fixed, but feedback suggests otherwise.

## Cross-Source Inconsistencies
- **ARR Mismatch (Acme Corp)**: $420,000 (GitHub) vs $450,000 (Google Sheets).
- **Risk Level Contradictions**: GitHub flags Acme, Pioneer, and Summit as "High/Critical" risk, while Google Sheets marks them as "Medium/Low" or "Reconciled."
- **Missing Account**: "Meridian Systems" exists only in Google Sheets `Support Themes` with a critical security risk; absent from GitHub.
- **Pipeline Stage Conflicts**: GitHub `pipeline.csv` lists both "Negotiation" and "Closed Won" for multiple accounts, while Google Sheets lists only "Closed Won."
- **SSO Implementation**: `release_notes.md` claims auto-config is live, but `customer_feedback.csv` confirms it was skipped for Nova Retail.

## Source Documents
- GitHub: `data/pipeline.csv`, `data/customer_feedback.csv`, `docs/release_notes.md`.
- Google Workspace: `Pipeline Review` (Spreadsheet), `Support Themes` (Spreadsheet).

## Recommended Next Actions
- **Meridian Systems**: Immediately investigate suspected unauthorized API access and produce the requested incident report.
- **Acme Corp**: Resolve UTC+7 batch job fix and reconcile the $30k ARR discrepancy and contract stage.
- **Summit Finance**: Verify billing reconciliation status across both sources and confirm webhook idempotency.
- **Pioneer Health**: Update GitHub repository to reflect GA status of audit log export and consolidate pipeline rows.
- **Nova Retail**: Execute data deduplication for customer records and verify SSO wizard fix in production.
