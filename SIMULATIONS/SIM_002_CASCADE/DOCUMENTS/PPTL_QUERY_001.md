═══════════════════════════════════════════════════════════════
INVESTIGATION STATE
═══════════════════════════════════════════════════════════════
Date (Player Perspective): July 6, 2026 - 16:45 EST
Focus Period: January 2024 - Present
Active Threads: Blake Emergency Transfer, PPTL Device Audit
Burned Sources: None
Flags: .spec device pattern analysis pending ICR cross-reference
═══════════════════════════════════════════════════════════════

═══════════════════════════════════════════════════════════════
[PPTL-AUD-2026-07-06-001: DATABASE QUERY RESULTS]
SOURCE: Prometheus Technologies Limited - Regulatory Compliance Division
DATE/TIME: 2026-07-06 16:42:33 EST
CLASSIFICATION: SUMMIT COUNCIL - AUDIT ACCESS (Level 3)
CONTEXT: Query submitted via Summit Council oversight protocol.
         Audit access provides device deployment metadata.
         Patient-identifying information requires institutional
         release or judicial warrant.
═══════════════════════════════════════════════════════════════

QUERY PARAMETERS
----------------
Device Suffix:     .spec (custom specification builds)
Date Range:        2024-01-01 through 2026-07-06
Institution:       ALL (filtered post-query by deployment site)
Status:            ALL (active, decommissioned, recalled)

QUERY EXECUTION: 2026-07-06 16:42:33
RECORDS RETURNED: 847
FILTER APPLIED: ICR Sites (all)
FILTERED RESULTS: 23

SECONDARY FILTER: ICR Site-17 (Blackwood Campus)
FILTERED RESULTS: 4

═══════════════════════════════════════════════════════════════
RESULTS: ICR SITE-17 .SPEC DEPLOYMENTS
═══════════════════════════════════════════════════════════════

RECORD 1 of 4
-------------
Serial:            PPTL-SRV-VII-2024-0892.spec
Device Class:      Series VII Adaptive Learning
Housing:           [REDACTED - Req. Institutional Release]
Deployment Date:   2024-03-14
Deployment Site:   ICR Site-17
Authorized By:     [REDACTED - Req. Institutional Release]
Subject ID:        [REDACTED - Req. Judicial Warrant]
Status:            DECOMMISSIONED
Decom Date:        2024-11-02
Decom Reason:      SUBJECT DECEASED - UNRELATED MEDICAL EVENT
Decom Auth:        T. Sevron, MD (Site Medical Director)
Final CFL Reading: 0.00 (flatline)

[SHEPHERD FLAG: "Unrelated medical event" requires verification.
 Device operational 233 days. Cross-reference with ICR mortality
 records recommended. Authorization: T. Sevron on deployment AND
 decommission - unusual pattern for standard protocol.]


RECORD 2 of 4
-------------
Serial:            PPTL-SRV-VI-2024-1204.spec
Device Class:      Series VI Standard
Housing:           Series VI Standard
Deployment Date:   2024-08-22
Deployment Site:   ICR Site-17
Authorized By:     [REDACTED - Req. Institutional Release]
Subject ID:        [REDACTED - Req. Judicial Warrant]
Status:            ACTIVE
Current CFL:       [REDACTED - Req. Institutional Release]
Last Calibration:  2026-06-28
Calibration Auth:  T. Sevron, MD

[SHEPHERD FLAG: .spec suffix on Series VI Standard is anomalous.
 Standard Series VI does not typically require custom builds.
 Specification details not available at this access level.
 Duration: 684 days and counting. Exceeds standard SAFE program
 graduation timeline (180-365 days recommended).]


RECORD 3 of 4
-------------
Serial:            PPTL-SRV-VII-2025-0156.spec
Device Class:      Series VII Adaptive Learning
Housing:           [REDACTED - Req. Institutional Release]
Deployment Date:   2025-06-03
Deployment Site:   ICR Site-17
Authorized By:     [REDACTED - Req. Institutional Release]
Subject ID:        [REDACTED - Req. Judicial Warrant]
Status:            ACTIVE
Current CFL:       [REDACTED - Req. Institutional Release]
Last Calibration:  2026-07-01
Calibration Auth:  T. Sevron, MD

[SHEPHERD FLAG: Series VII Adaptive deployed 11 months prior
 to official recall date (April 19, 2025). Pre-recall deployment
 of recalled device class requires review. Duration: 399 days
 and counting.]


RECORD 4 of 4
-------------
Serial:            PPTL-SRV-VII-2026-0341.spec
Device Class:      Series VII Adaptive Learning
Housing:           [REDACTED - Req. Institutional Release]
Deployment Date:   2026-03-31
Deployment Site:   ICR Site-17
Authorized By:     T. Sevron, MD
Subject ID:        [REDACTED - Req. Judicial Warrant]
Status:            ACTIVE
Current CFL:       [REDACTED - Req. Institutional Release]
Last Calibration:  2026-07-05
Calibration Auth:  T. Sevron, MD

[SHEPHERD FLAG: HIGH PRIORITY
 - Deployment date matches Blake emergency transfer timeline
 - Series VII deployed AFTER official recall (April 19, 2025)
 - Post-recall deployment of Series VII requires TSB exemption
 - No TSB exemption on file for this serial number
 - Calibration performed 1 day prior to emergency transfer
 - Authorizing physician (Sevron) is subject of multiple
   ethics complaints regarding this patient cohort]


═══════════════════════════════════════════════════════════════
PATTERN ANALYSIS
═══════════════════════════════════════════════════════════════

SITE-17 .SPEC DEPLOYMENT SUMMARY:
- Total .spec devices deployed at Site-17: 4
- Currently active: 3
- Decommissioned: 1 (subject deceased)
- Deployment authorization by T. Sevron: 4/4 (100%)
- Calibration authorization by T. Sevron: 4/4 (100%)

ANOMALY FLAGS:
1. Single-physician authorization pattern (Sevron) across ALL
   .spec deployments at Site-17 is statistically significant
   (p < 0.01 against site-wide authorization distribution)

2. Series VII devices deployed before AND after recall date
   without TSB exemption documentation

3. One .spec subject deceased; cause listed as "unrelated"
   but verification unavailable at this access level

4. Average deployment duration: 439 days (active devices)
   Standard SAFE graduation timeline: 180-365 days

5. Housing field redacted on 3/4 devices suggests potential
   device modification data available only at institutional level

LIMITATION NOTICE:
This query provides deployment metadata only. The following
information requires elevated access:

- Patient identity and medical records → Judicial warrant
- Device housing specifications → Institutional release or warrant
- Calibration parameters and logs → Institutional release or warrant
- Full authorization chain → Institutional release or warrant
- CFL telemetry history → Institutional release or warrant
- Mortality records cross-reference → Judicial warrant

═══════════════════════════════════════════════════════════════
CROSS-REFERENCE OPPORTUNITIES (Pending Authorization)
═══════════════════════════════════════════════════════════════

WITH ICR DATABASE ACCESS:
- Match Subject IDs to patient records
- Verify housing configurations (VII in VI housing pattern)
- Review calibration logs for punishment-response patterns
- Cross-reference deceased subject with mortality documentation
- Audit ethics complaint timeline against deployment dates

WITH PPTL ENGINEERING ACCESS:
- Retrieve .spec modification specifications
- Verify firmware versions and custom parameters
- Audit failsafe configuration documentation

WITH TSB RECORDS:
- Verify exemption status for post-recall Series VII deployments
- Review any variance requests filed by Site-17

═══════════════════════════════════════════════════════════════
---
SHEPHERD METADATA
---
Query Execution Time: 0.847s
Records Scanned: 12,847
Cache Status: Fresh
Cross-Reference Queue: ICR-17-MORTALITY, TSB-VARIANCE-LOG
Priority Flag: ACTIVE - Pending Blake device telemetry capture
Pattern Match: 87% confidence - coordinated deployment pattern
Next Action: Await warrant authorization post-Aria assessment
═══════════════════════════════════════════════════════════════
