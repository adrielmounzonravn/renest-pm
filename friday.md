# ReNest Delivery, Communication & Final Presentation — Adriel Mounzón Baspineiro

**Project repository:** [github.com/adrielmounzonravn/renest-pm](https://github.com/adrielmounzonravn/renest-pm)
**Demo video:** [Watch on Google Drive](https://drive.google.com/file/d/101C2Fwn3lHLN2rXVRxHaciLzw01SJPIB/view?usp=sharing)

## Context carried from Thursday
- Confirmed MVP: Condition badge on the listing; minimum real photos required to publish; "doesn't match description" report.
- #1 feature (top-ranked, RICE #1): Condition badge on the listing.
- North Star: Weekly completed purchases with no condition-related dispute or return.

## 1. Acceptance criteria (MVP — all 3 confirmed features)

### Condition badge on the listing
- *Given* a seller is publishing an item, *when* they tap "Publish" without having selected a condition status, *then* publishing is blocked and the condition field is highlighted as required. *(unhappy path)*
- *Given* a listing has a condition status selected, *when* a buyer opens that listing, *then* the condition badge is visible on both the listing card and the item detail view, next to the photos and price, showing the exact status the seller chose. *(happy path)*
- *Given* a condition badge is displayed, *when* it renders on any background, *then* its color and text meet WCAG AA contrast so the status is distinguishable without relying on color alone. *(happy path — accessibility)*

### Minimum real photos required to publish
- *Given* a seller is publishing an item with fewer than 3 photos attached, *when* they tap "Publish," *then* publishing is blocked and the seller is told how many more photos are needed before they can continue. *(unhappy path)*
- *Given* a seller has attached 3 or more photos, *when* they tap "Publish," *then* the listing goes live with all attached photos, and the photo count is no longer flagged. *(happy path)*
- *Given* a seller is uploading a photo on a 4G connection, *when* the upload completes, *then* it does so in under 5 seconds so the requirement doesn't stall the publish flow. *(happy path — performance)*

### "Doesn't match description" report
- *Given* a buyer has a completed order, *when* they open the report flow within the eligibility window after pickup/delivery and select a reason (e.g. condition worse than described, wrong item), *then* the report is filed and logged against that order. *(happy path)*
- *Given* a buyer tries to file a report either without an underlying completed order or after the eligibility window has closed, *when* they attempt to submit it, *then* the report flow is blocked and the buyer is shown why (no eligible order / window expired). *(unhappy path)*
- *Given* a buyer opens the report flow, *when* they try to submit without picking a reason from the list, *then* submission is blocked until a reason is selected. *(unhappy path)*
- *Given* a report has been filed, *when* up to 24h pass, *then* it is reflected in the North Star metric (weekly completed purchases with no condition-related dispute or return) so the team can see the impact without a manual pull. *(happy path — measurement)*

## 2. Top 3 risks

### Condition badge on the listing

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Sellers pick an optimistic status (e.g. "good condition" for a visibly worn item) | High | High | Show a short description/example next to each status option so the choice isn't purely subjective |
| The badge blends visually with other listing tags (free shipping, featured) and buyers don't notice it | Medium | Medium | Dedicated design review before build, with clear visual hierarchy for the badge vs. other tags |
| Buyers still don't trust the badge and keep hesitating to contact sellers | Low | High | Monitor weekly completed purchases (North Star) in the first two weeks post-launch; if it doesn't move, the root-cause hypothesis was wrong, not the badge itself |

### Minimum real photos required to publish

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Sellers get frustrated at the 3-photo minimum mid-flow and abandon the listing entirely rather than take more photos | Medium | High | Surface the requirement upfront (before the seller starts filling out the listing), not just as a block at publish time; track % of sellers who complete the publish flow as a guardrail |
| Photo uploads are slow or fail on poor connections, and the 5s-on-4G target isn't met in real conditions | Medium | Medium | Client-side compression before upload, retry-on-failure, and a progress indicator so the seller isn't left guessing whether it's stuck |
| Sellers satisfy the minimum with junk photos (duplicates, stock images, screenshots) that don't actually show real condition | Medium | High | Out of scope for MVP validation (resolution/authenticity checks are deferred to "mandatory high-resolution photos"), but monitor the North Star and report volume closely — if disputes stay high despite the minimum being met, this is the likely cause |

### "Doesn't match description" report

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Buyers under-report because filing feels like effort, undermining the only source of dispute data the MVP relies on to measure itself | Medium | High | Keep the report flow to a couple of taps (pick a reason, optional note) and surface it proactively post-delivery rather than requiring the buyer to hunt for it |
| Buyers file false or exaggerated reports (e.g. buyer's-remorse claims) that unfairly penalize sellers or pollute the dispute data | Medium | Medium | Restrict filing to completed orders within a fixed window and require a specific reason; route disputed reports to manual review before any seller-facing consequence |
| The 24h reflection-in-North-Star pipeline breaks or lags, so the team is flying blind on whether badge + photos are actually working | Low | High | Add a monitoring alert on the report-to-metric pipeline; treat pipeline health as a launch-blocking dependency, not a nice-to-have |

## 3. Go / no-go call

### Condition badge on the listing
- Ship criteria: the condition badge's acceptance criteria (happy + unhappy path) pass in testing, and the condition-status descriptions/examples have been reviewed by at least one real seller.
- Decision owner: the squad's PM, with design sign-off on the badge's visual hierarchy against other listing tags.
- Rollback trigger: if weekly completed purchases with no condition-related dispute (the North Star) drop below the current baseline in the two weeks after launch.
- What we'll monitor (tie to North Star): weekly completed purchases with no condition-related dispute or return (North Star), plus % of buyers who message a seller after viewing a listing as an earlier support signal.
- Recommendation: **GO** — because the highest-impact risk (buyers still don't trust the badge) is covered by early North Star monitoring, and the other two risks (optimistic seller input, visual confusion with other tags) are mitigated by content and design work already planned before launch.

### Minimum real photos required to publish
- Ship criteria: the photo-minimum acceptance criteria (happy + unhappy path) pass in testing, upload times hold under 5s on 4G in real-network testing, and the "why" messaging at the block point has been reviewed for clarity.
- Decision owner: the squad's PM, with engineering sign-off on upload reliability/performance under poor connectivity.
- Rollback trigger: if % of sellers who complete the publish flow drops meaningfully against the current baseline in the two weeks after launch, indicating the requirement is driving abandonment rather than better listings.
- What we'll monitor (tie to North Star): % of sellers who complete the listing/publish flow (guardrail), plus weekly completed purchases with no condition-related dispute or return (North Star) to confirm more photos are actually reducing disputes.
- Recommendation: **GO** — the abandonment risk is the highest-impact one, and it's directly covered by the publish-completion guardrail; the performance risk is mitigated by compression/retry work already scoped, and photo quality is explicitly deferred rather than solved here.

### "Doesn't match description" report
- Ship criteria: the report's acceptance criteria (happy + unhappy path) pass in testing, and the report-to-North-Star pipeline is verified to reflect a filed report within 24h in staging.
- Decision owner: the squad's PM, with a defined escalation path (who reviews disputed/flagged reports) signed off by support/ops before launch.
- Rollback trigger: if the report-to-metric pipeline lags or fails to reflect filings within 24h, or if report volume is high enough to suggest sellers are being unfairly penalized by unreviewed reports.
- What we'll monitor (tie to North Star): weekly completed purchases with no condition-related dispute or return (North Star, measured *via* this feature), plus raw report volume and reason breakdown as an early read on whether the badge and photo minimum are working.
- Recommendation: **GO** — this is the MVP's measurement instrument, not a preventer, so shipping it isn't optional; the false-report risk is mitigated by requiring a completed order, a window, and a specific reason, and the under-reporting risk is mitigated by keeping the flow to a couple of taps.

## 4. Story arc outline (for the final video)
1. The problem — Buyers on ReNest can't tell whether a listed item's actual condition matches its photos and description, so they hesitate to contact the seller and often drift to other platforms instead.
2. Who + North Star — Sonia, furnishing her apartment on a tight budget, has shown up to pickups to find items more worn than pictured. Success is measured as weekly completed purchases with no condition-related dispute or return.
3. The MVP + why — Condition badge, minimum real photos, and a "doesn't match description" report. The first two attack the trust gap directly and are the cheapest build for the most immediate impact; the report is included because it's the only source of dispute data — without it we can't tell if the other two are actually working.
4. What "done" means (#1 feature) — For the condition badge: a seller can't publish without picking a status, and buyers see that exact status on the card and detail view, in accessible color/text.
5. Go/no-go recommendation — GO, with the highest-impact risk (buyers still not trusting the badge) covered by early North Star monitoring rather than left unaddressed.
6. What's next — Now: badge, minimum photos, report. Next: seller response-time indicator, "ask a question" template. Later: high-resolution photos, verified-seller badge — deferred because they depend on data or history that doesn't exist yet.