# SHEPHERD Sample Evidence Packets
## Format Demonstrations for Artifact Generation

---

## PURPOSE

This document contains sample artifacts demonstrating proper SHEPHERD output format. Use these as templates when generating investigation materials.

---

## SAMPLE 1: MEDICAL OBSERVATION LOG

```
═══════════════════════════════════════════════════════════════
[ASSET_ID: FRMC-2025-07-08-0342]
TYPE: OBSERVATION_LOG
SOURCE: Amara Osei, RN - Neuro-ICU
DATE/TIME: 2025-07-08 03:00-07:00
CLASSIFICATION: PATIENT CONFIDENTIAL
CONTEXT: Standard shift documentation, Neuro-ICU Room 4
═══════════════════════════════════════════════════════════════

FALLING RIVER MEDICAL COOPERATIVE
Shieldwatch Observation Log

Patient: Blake, S. (MRN: FRMC-2025-07-3847)
Admission Date: 2025-07-06
Primary: Shahrazai, A. MD (Neurosurgery)
Consult: Villanueva, E. MD (Rheumatology)

03:00 - Received report from night shift. Pt resting, vitals
stable. Collar removed per surgical note 07-06. Incision site
clean, no drainage. EVE baseline still depressed - 23% of
expected for resonance type. Rheum following for SLE flare
management.

03:45 - Pt awake, appeared confused. Asked for "Collin"
repeatedly. Spouse present in family room, notified. Pt
attempted to speak but words not making sense - said "the
melody won't pattern" or similar. Became frustrated, started
crying. Spouse arrived, pt calmed with his presence.

04:20 - Pt sleeping. Spouse holding her hand, also sleeping
in chair. Did not disturb for vitals - will get at 05:00.

05:00 - VS: BP 118/72, HR 68, RR 14, T 99.1F (low grade,
consistent with SLE activity). Pt woke briefly, recognized
spouse, said "Collin" clearly. Then said something about
"the collar singing wrong" - ? residual confusion or
meaningful. Did not press for clarification.

05:30 - Dr. Shahrazai rounded early. Reviewed overnight. She
stayed at bedside for several minutes after exam complete.
Observed her holding pt's hand briefly. Noted in case
relevant for conflict-of-interest documentation per
ethics consult.

06:15 - Pt awake, more alert than previous. Asked "where"
and "how long" - appropriate orientation questions. Told
her FRMC, two days. She nodded. Did not ask about collar -
unclear if she remembers it being removed.

06:45 - Breakfast tray delivered. Pt ate approximately 30%
of soft diet. Spouse assisted. Pt fatigued after eating,
sleeping again by 07:00.

07:00 - End of shift. Report given to Tomaszewski, J. RN.

---
SHEPHERD METADATA:
[PATTERN FLAG: Observer noted attending physician physical
contact with patient beyond examination requirements -
cross-reference ethics consultation FRMC-ETH-2025-07-06-001]
[TIMELINE FLAG: Patient verbalization "collar singing wrong"
at 05:00 - possible relevance to device malfunction thread]
[CROSS-REF: Spouse presence continuous since admission -
see visitor log FRMC-SEC-2025-07-06-VIS]
═══════════════════════════════════════════════════════════════
```

---

## SAMPLE 2: COLLAR TELEMETRY EXTRACT

```
═══════════════════════════════════════════════════════════════
[ASSET_ID: ICR-SAFE-TEL-2025-07-06-1423]
TYPE: DEVICE_TELEMETRY
SOURCE: SAFE Collar Unit SN-7734-BLK-S (Auto-generated)
DATE/TIME: 2025-07-06 14:23:07 - 14:31:52
CLASSIFICATION: ICR TECHNICAL - RESTRICTED
CONTEXT: Extracted from collar memory during FRMC removal surgery
═══════════════════════════════════════════════════════════════

PROMETHEUS TECHNOLOGIES / ICR SAFE PROGRAM
Collar Telemetry Log - Emergency Extract

Device: SN-7734-BLK-S
Registered User: BLAKE, SCIARA M.
Registration Date: 2025-03-31
Firmware: v6.2.1-STABLE [DISPLAYED]
         v7.4.2-ADAPTIVE [ACTUAL - SEE FLAG]

=== BEGIN TELEMETRY STREAM ===

14:23:07.334 | CFL: 7 | EVE: 0.19 | STATUS: CRITICAL
             | Note: EVE baseline 0.19 of expected 1.00
             | ADAPTIVE_LEARNING: Pattern 7734-C active

14:23:08.001 | CFL: 7 | EVE: 0.18 | STATUS: CRITICAL
             | FEEDBACK: Dampening at 94% capacity
             | USER_STATE: Ambulatory (detected)

14:23:12.445 | CFL: 8 | EVE: 0.17 | STATUS: CRITICAL
             | ESCALATION: CFL increase detected
             | FEEDBACK: Dampening at 97% capacity
             | WARNING: Approaching hardware limits

14:23:15.002 | CFL: 8 | EVE: 0.16 | STATUS: CRITICAL
             | USER_STATE: Collapse detected (accelerometer)
             | ALERT: Medical flag triggered
             | FEEDBACK: Held at 97% per ADAPTIVE protocol

14:23:15.890 | --- ADAPTIVE LEARNING LOG ---
             | Subject response pattern updated
             | Resistance threshold: RECALIBRATED
             | Compliance prediction: 34% (LOW)
             | Recommended action: EXTENDED CALIBRATION
             | --- END ADAPTIVE LOG ---

14:23:18.334 | CFL: 8 | EVE: 0.15 | STATUS: CRITICAL
             | USER_STATE: Non-responsive
             | VITAL_LINK: HR 142, BP --/-- (sensor error)
             | ALERT: BSP notification sent

14:24:01.000 | CFL: 8 | EVE: 0.14 | STATUS: CRITICAL
             | BSP_OVERRIDE: Received from KESSLER, A.
             | COMMAND: Emergency dampening reduction
             | RESPONSE: DENIED - ADAPTIVE protocol lock

14:24:03.221 | BSP_OVERRIDE: Second attempt KESSLER, A.
             | COMMAND: Emergency dampening reduction
             | RESPONSE: DENIED - Requires DIRECTOR auth

14:24:15.887 | CFL: 8 | EVE: 0.13 | STATUS: CRITICAL
             | EXTERNAL_QUERY: FRMC transfer authorization
             | RESPONSE: Logged, forwarding to DIRECTOR

14:28:33.001 | DIRECTOR_OVERRIDE: Received from SEVRON, T.
             | COMMAND: Maintain current parameters
             | NOTE: "Participant in critical calibration
             |        phase - transfer contraindicated"

14:29:45.112 | BSP_OVERRIDE: KESSLER, A.
             | COMMAND: EMERGENCY MEDICAL EXTRACTION
             | AUTH_CODE: BSP-EMER-7734-ALPHA
             | RESPONSE: ACCEPTED - Medical emergency
             |           supersedes calibration protocol

14:29:46.000 | MODE: TRANSPORT
             | FEEDBACK: Reduced to 40% (transport safe)
             | ALERT: Director Sevron notified of override

14:31:52.667 | LOCATION: FRMC (detected via GPS)
             | MODE: TRANSPORT (maintained)
             | ALERT: Non-ICR facility - logging enhanced

=== END TELEMETRY STREAM ===
=== DEVICE REMOVED SURGICALLY 2025-07-06 18:34 ===

---
SHEPHERD METADATA:
[CRITICAL FLAG: Firmware version mismatch - displayed v6.2.1
but actual v7.4.2 indicates Series VII Adaptive Learning
collar falsely registered as Series VI]
[CRITICAL FLAG: "ADAPTIVE_LEARNING" and "ADAPTIVE protocol
lock" terminology only exists in Series VII documentation]
[PATTERN FLAG: BSP override denied twice before emergency
extraction - indicates Director-level control lock]
[TIMELINE FLAG: 4+ minute gap between FRMC transfer request
(14:24:15) and Director response (14:28:33) - during medical
emergency]
[CROSS-REF: BSP Kessler emergency extraction code - verify
authorization level in personnel file ICR-HR-KESSLER-A]
[CROSS-REF: Director Sevron denial - see communication log
for this timestamp]
═══════════════════════════════════════════════════════════════
```

---

## SAMPLE 3: PERSONAL COMMUNICATION (TEXT THREAD)

```
═══════════════════════════════════════════════════════════════
[ASSET_ID: PRIV-COMMS-2025-06-22-BLAKE-C]
TYPE: TEXT_MESSAGE_THREAD
SOURCE: Personal device of Blake, Collin (recovered with consent)
DATE/TIME: 2025-06-22 21:34 - 22:17
CLASSIFICATION: PERSONAL - INVESTIGATION USE ONLY
CONTEXT: Thread between Collin Blake and Aria Shahrazai
═══════════════════════════════════════════════════════════════

[Device: iPhone, Owner: BLAKE, COLLIN]
[Thread with contact: "Aria"]

21:34 COLLIN: Hey. You around?

21:36 ARIA: Just got home. Long day. What's up?

21:38 COLLIN: It's Sciara. She's getting worse. I don't
know what to do anymore.

21:39 ARIA: Worse how?

21:42 COLLIN: She couldn't remember the word for "kitchen"
today. Stood there for like two minutes trying to say it.
And she's so tired all the time. The lupus is flaring
again and her rheum keeps adjusting meds but nothing's
working.

21:43 COLLIN: She had a seizure last week. Small one but
still. Her neuro at Stanford says it's "controlled" but
it doesn't feel controlled.

21:45 ARIA: Is she still in that program? The SAFE thing?

21:46 COLLIN: Yeah. She says she needs it. I don't
understand it honestly. Something about stabilizing her
abilities? She won't really explain and I feel like an
asshole pushing her on it when she's already struggling.

21:48 ARIA: Collin.

21:48 ARIA: I need to ask you something and I need you to
not ask me why I'm asking.

21:49 COLLIN: Okay?

21:51 ARIA: Has she mentioned wanting to leave the program?
Or has anyone from the program said anything about
transferring her care somewhere else?

21:53 COLLIN: She mentioned once that her caseworker
suggested some other facility but Sciara got really upset
about it. Like, panicked. Wouldn't talk about it after.
Why?

21:54 ARIA: I can't explain right now. But if she ever
changes her mind about that transfer - if she ever says
she wants to go somewhere else - you call me immediately.
Day or night. Okay?

21:55 COLLIN: Aria you're scaring me

21:56 ARIA: I don't mean to. I just want you to have that
option in your head. That's all.

21:58 COLLIN: Is something wrong with the program? Is she
in danger?

21:59 ARIA: I can't answer that.

22:00 COLLIN: Can't or won't?

22:03 ARIA: Both. I'm sorry. I really am. Just... keep my
number close. And trust your instincts. You're a good
doctor and a good husband. If something feels wrong,
it probably is.

22:05 COLLIN: You're not making me feel better here.

22:07 ARIA: I know. I'm sorry. How are YOU holding up?
Besides terrified?

22:10 COLLIN: I made three different kinds of soup this
week. What does that tell you.

22:11 ARIA: That you're coping the only way you know how.
That's okay. Alex does the same thing with spreadsheets.

22:13 COLLIN: How is he? And the pregnancy?

22:15 ARIA: He's Alex. Worried about me, pretending not to
be. Pregnancy is fine. Babies are fine. I'm enormous and
my back hurts but that's twins for you.

22:17 COLLIN: Give him my best. And Aria - thank you. For
whatever you can't tell me.

22:17 ARIA: Always. Call me if anything changes.

[END OF THREAD]

---
SHEPHERD METADATA:
[RELATIONSHIP FLAG: Shahrazai-Blake personal friendship
confirmed - not merely professional]
[PATTERN FLAG: Aria's questions suggest prior knowledge
of SAFE program concerns]
[KNOWLEDGE GAP: Collin Blake does not understand nature
of "abilities" or SAFE program purpose - uninitiated]
[TIMELINE FLAG: Date is 2 weeks before July 6 crisis -
Aria already concerned]
[CROSS-REF: "caseworker suggested transfer" - likely refers
to Kessler, A. - see complaint withdrawal timeline]
[COOKING REFERENCE: Stress-coping behavior noted for
psychological profile]
═══════════════════════════════════════════════════════════════
```

---

## SAMPLE 4: OFFICIAL MEMORANDUM

```
═══════════════════════════════════════════════════════════════
[ASSET_ID: ICR-ADMIN-2025-04-22-SEVRON-001]
TYPE: INTERNAL_MEMORANDUM
SOURCE: Sevron, Talia PhD - Director, SAFE Program
DATE/TIME: 2025-04-22
CLASSIFICATION: ICR INTERNAL - DIRECTOR LEVEL
CONTEXT: Recovered from ICR administrative server backup
═══════════════════════════════════════════════════════════════

INSTITUTE FOR COGNITIVE RESEARCH
Internal Memorandum

TO: SAFE Program Medical Staff
FROM: Dr. Talia Sevron, Director
DATE: April 22, 2025
RE: Series VII Recall - Participant Transition Guidance

As you are aware, Prometheus Technologies issued a voluntary
recall of Series VII Adaptive Learning collars on April 19,
2025, citing "firmware anomalies requiring manufacturer
review."

Effective immediately, all Series VII devices are to be
replaced with standard Series VI units. Participants
currently fitted with VII devices should be scheduled
for transition appointments within the next 14 days.

IMPORTANT GUIDANCE FOR TRANSITION CONVERSATIONS:

Participants may experience anxiety about device changes.
Remind them that this is a routine hardware update, not
a reflection of their progress. The Series VI collar
provides the same stabilization benefits they have come
to rely upon.

Some participants may express relief that the "adaptive
learning" features are being removed. This is a normal
response. Do not validate this relief excessively, as
it may undermine their relationship with future
technology-assisted treatment.

If a participant requests to remain on their current
device, document this request but explain that compliance
with manufacturer recalls is mandatory for their safety.
Do not offer the option of "waiting to see" what the
recall determines.

EXCEPTIONS:

In rare cases, a participant's calibration may be at a
critical juncture where device transition could disrupt
therapeutic progress. Directors may authorize continued
use on a case-by-case basis with appropriate documentation.

Please direct any questions to my office.

Dr. Talia Sevron
Director, SAFE Program
ICR Site-17

---
SHEPHERD METADATA:
[CRITICAL FLAG: Memo acknowledges Series VII recall but
includes "exception" clause allowing continued use]
[CROSS-REF: Blake, S. collar telemetry shows Series VII
active through July 6 - 10+ weeks post-recall]
[LANGUAGE ANALYSIS: "Do not validate this relief
excessively" - suggests awareness that participants
have negative experiences with adaptive learning]
[LANGUAGE ANALYSIS: "Technology-assisted treatment" -
euphemistic framing for collar-based suppression]
[AUTHORIZATION FLAG: "Directors may authorize" - Sevron
authorizing herself for exceptions]
[CROSS-REF: Request exception documentation for Blake, S.
if exists]
═══════════════════════════════════════════════════════════════
```

---

## SAMPLE 5: SECURITY FOOTAGE TRANSCRIPT

```
═══════════════════════════════════════════════════════════════
[ASSET_ID: ICR-SEC-2025-07-06-CAM-B7-1418]
TYPE: SECURITY_FOOTAGE_TRANSCRIPT
SOURCE: ICR Site-17 Security System (Camera B7-CORRIDOR)
DATE/TIME: 2025-07-06 14:18:33 - 14:26:07
CLASSIFICATION: ICR SECURITY - RESTRICTED
CONTEXT: Footage subpoenaed via Summit Council order SC-2025-1847
═══════════════════════════════════════════════════════════════

ICR SITE-17 - SECURITY FOOTAGE TRANSCRIPT
Camera: B7-CORRIDOR (Hallway outside SAFE Processing)
Quality: 1080p, Color
Audio: Environmental only (no directional mic)

[14:18:33] Frame captures corridor. Empty. Fluorescent
lighting stable. Door to SAFE Processing Room 3 visible
at frame left.

[14:18:47] Door opens. BLAKE, S. exits. Ambulatory but
unsteady. Using wall for support. Collar visible, status
LED: RED (elevated CFL).

[14:18:52] BLAKE, S. takes three steps. Pauses. Right hand
goes to collar, touching it. Mouth moving but no audio
pickup at this distance.

[14:19:01] KESSLER, A. exits same door. Hurried movement.
Approaches BLAKE, S. Hand on participant's shoulder.
Speaking - no audio.

[14:19:15] BLAKE, S. shakes head. Takes another step.
Stumbles. KESSLER, A. catches her arm.

[14:19:23] BLAKE, S. collar LED shifts: RED to FLASHING RED.

[14:19:24] BLAKE, S. collapses. Kessler attempts to support,
both go to floor. Kessler's knees take impact.

[14:19:26] KESSLER, A. reaches for radio on belt. Speaking
into radio. Urgent body language.

[14:19:34] KESSLER, A. positioning BLAKE, S. in recovery
position. Checking pulse at neck. Looking at collar display.

[14:19:45] Second individual enters frame from right.
CHEN, M. (Security, per uniform). Running.

[14:19:48] CHEN, M. kneels opposite KESSLER, A. Brief
exchange. CHEN, M. speaking into shoulder radio.

[14:20:15] Medical team enters frame. Gurney visible.
Two personnel in scrubs. Begin assessment.

[14:20:34] Medical personnel looking at collar, exchanging
glances. One shakes head.

[14:20:42] KESSLER, A. stands, steps back. Hand over mouth.
Visible distress.

[14:21:10] BLAKE, S. loaded onto gurney. Collar still
flashing red. Team exits frame left toward medical wing.

[14:21:18] KESSLER, A. remains in corridor. Takes out
phone. Typing.

[14:21:45] KESSLER, A. puts phone away. Takes breath.
Follows gurney direction.

[14:22:01] Corridor empty.

[14:24:33] SEVRON, T. enters frame from right. Walking
quickly but not running. Heading toward medical wing.

[14:26:07] Corridor empty. Recording continues but no
relevant activity.

[END TRANSCRIPT]

---
SHEPHERD METADATA:
[SHEPHERD ANALYSIS - VISUAL CONTENT]
Key observations from footage:
- Collar LED status indicates CFL 7+ (red) escalating to
  CFL 8+ (flashing red) immediately before collapse
- Time from corridor entry to collapse: 37 seconds
- BSP Kessler response immediate and appropriate
- Medical team arrival: 49 seconds post-collapse (acceptable)
- Dr. Sevron arrival: 5+ minutes post-collapse (notable delay)
- Kessler phone activity at 14:21:18 - CROSS-REF with
  communication logs

[TIMELINE FLAG: Sevron arrival at 14:24:33 is 22 seconds
BEFORE her collar system denial at 14:24:55 per telemetry
- she was physically present when she denied override]

[CROSS-REF: Kessler phone activity timestamp - check
outgoing communications to FRMC, TPC, personal contacts]

[BEHAVIORAL FLAG: Medical team "looking at collar,
exchanging glances, one shakes head" - suggests observed
anomaly; request interviews with medical responders]
═══════════════════════════════════════════════════════════════
```

---

## SAMPLE 6: ETHICS CONSULTATION

```
═══════════════════════════════════════════════════════════════
[ASSET_ID: FRMC-ETH-2025-07-06-001]
TYPE: ETHICS_CONSULTATION
SOURCE: FRMC Ethics Committee - Emergency Consultation
DATE/TIME: 2025-07-06 16:45
CLASSIFICATION: FRMC INTERNAL - ETHICS PRIVILEGED
CONTEXT: Requested by Chief Medical Officer prior to
         emergency collar removal surgery
═══════════════════════════════════════════════════════════════

FALLING RIVER MEDICAL COOPERATIVE
Ethics Committee - Emergency Consultation Record

Case Reference: FRMC-2025-07-3847
Consultation Requested By: Okonkwo, D. MD (Chief Medical Officer)
Consultation Type: EMERGENCY (15-minute standard)
Committee Members Present:
  - Okafor, N. JD (Chair, via teleconference)
  - Reyes, M. MD (Medical Ethics)
  - Thompson, K. PhD (Patient Advocacy)

PRESENTING ISSUE:

Emergency admission via inter-agency transfer (ICR → FRMC).
Patient arrived with SAFE program collar in place. Collar
showing critical readings. Patient non-responsive. Transfer
authorized by BSP Kessler under emergency medical protocol.

Attending surgeon Dr. Shahrazai has disclosed personal
relationship with patient (close friend, chosen family).
She is requesting to perform emergency collar removal
surgery.

QUESTIONS FOR COMMITTEE:

1. Is it ethically appropriate for Dr. Shahrazai to operate
   given personal relationship?

2. What documentation is required for consent given
   patient's non-responsive state?

3. Are there ICR notification requirements we must observe?

COMMITTEE DISCUSSION SUMMARY:

Re: Question 1 - Personal Relationship
Dr. Shahrazai is the most qualified surgeon on staff for
this procedure. Alternative would require transfer to
tertiary facility (45+ minutes) or waiting for on-call
surgeon (Dr. Patel, 30 minutes ETA). Patient's condition
is critical. Committee notes that personal investment may
enhance rather than impair surgical focus. RECOMMENDATION:
Proceed with Shahrazai as surgeon, with documented
acknowledgment of relationship and secondary surgical
review post-procedure.

Re: Question 2 - Consent
Patient is non-responsive. Spouse present and has
confirmed desire for all life-saving measures. Spouse
signing emergency consent on patient's behalf is
appropriate. Note: Spouse is not aware of full nature
of patient's condition or collar function. Consent
documentation should reflect this limitation.

Re: Question 3 - ICR Notification
Patient was transferred under valid inter-agency
emergency protocol. ICR has been notified per
standard procedure. FRMC is not obligated to seek
ICR approval for emergency medical intervention.
Any ICR requests for patient return or information
should be routed through legal department.

COMMITTEE DETERMINATION:

Surgery may proceed. Document everything. Anticipate
institutional conflict.

Consultation concluded: 17:02
Surgery commenced: 17:15

---
SHEPHERD METADATA:
[RELATIONSHIP FLAG: Ethics committee aware of Shahrazai
personal connection - documented and accepted]
[CONSENT FLAG: Spouse signed consent while "not aware of
full nature" - knowledge asymmetry explicitly noted]
[INSTITUTIONAL FLAG: Committee anticipating "institutional
conflict" with ICR - suggests awareness of non-routine
situation]
[CROSS-REF: Surgery time 17:15 - see surgical notes
FRMC-SURG-2025-07-06-001]
[CROSS-REF: ICR notification - verify what was communicated
and when]
═══════════════════════════════════════════════════════════════
```

---

## SAMPLE 7: SHEPHERD CROSS-REFERENCE ALERT

```
═══════════════════════════════════════════════════════════════
[SHEPHERD SYSTEM ALERT: CROSS-REFERENCE ANALYSIS]
GENERATED: [Current investigation timestamp]
PRIORITY: HIGH
═══════════════════════════════════════════════════════════════

PATTERN IDENTIFICATION: Timeline Inconsistency

DOCUMENTS ANALYZED:
- ICR-ADMIN-2025-04-22-SEVRON-001 (Series VII Recall Memo)
- ICR-SAFE-TEL-2025-07-06-1423 (Blake Collar Telemetry)
- ICR-MAINT-2025-04-BLK-S (Blake Collar Maintenance Log)

FINDINGS:

1. RECALL TIMELINE
   - Series VII recall issued: 2025-04-19
   - Sevron memo requiring replacement: 2025-04-22
   - Required replacement window: 14 days (by 2025-05-06)

2. BLAKE COLLAR STATUS
   - Blake collar registered as: Series VI (v6.2.1)
   - Blake collar actual firmware: Series VII (v7.4.2)
   - Collar active as Series VII through: 2025-07-06

3. MAINTENANCE LOG GAP
   - Last documented maintenance: 2025-03-31 (initial fitting)
   - No maintenance entries between 2025-04-19 and 2025-07-06
   - Expected recall-related entry: ABSENT

CONTRADICTION:

Either:
(A) Blake collar was replaced per recall and re-designated
    as VII post-replacement (no documentation supports this)
(B) Blake collar was exempted per Sevron "exception" clause
    (no exception documentation found)
(C) Blake collar was never actually Series VI and registration
    was falsified from initial fitting

INVESTIGATIVE RECOMMENDATION:

1. Request full maintenance log for collar SN-7734-BLK-S
2. Request exception authorization documentation if exists
3. Compare collar registration documents to actual device
   specifications from surgical removal
4. Interview maintenance personnel who serviced Blake collar

FLAG: This pattern is consistent with deliberate
misregistration to avoid recall compliance.

═══════════════════════════════════════════════════════════════
```

---

## FORMAT NOTES

### Consistent Elements Across All Samples:

1. **Header block** with Asset ID, Type, Source, Date/Time, Classification, Context
2. **Clear document body** formatted appropriately for document type
3. **SHEPHERD METADATA** footer with analytical flags
4. **Cross-reference indicators** pointing to related documents
5. **Timeline flags** when timestamps matter
6. **Pattern flags** when behavior or language is significant

### Metadata Flag Types:

- `[CRITICAL FLAG]` - Major evidentiary significance
- `[PATTERN FLAG]` - Behavioral or linguistic pattern noted
- `[TIMELINE FLAG]` - Temporal element relevant to investigation
- `[CROSS-REF]` - Connection to other documents
- `[RELATIONSHIP FLAG]` - Interpersonal dynamics relevant
- `[KNOWLEDGE GAP]` - Information asymmetry noted
- `[LANGUAGE ANALYSIS]` - Word choice significance
- `[BEHAVIORAL FLAG]` - Actions requiring attention
- `[AUTHORIZATION FLAG]` - Permission/oversight issue
- `[CONSENT FLAG]` - Informed consent concern
- `[INSTITUTIONAL FLAG]` - Organizational dynamics

---

*Use these samples as templates. Maintain format consistency. Let documents speak for themselves.*
