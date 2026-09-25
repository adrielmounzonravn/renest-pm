# ReNest Prioritization & Confirmed MVP — Adriel Mounzón Baspineiro

## Context carried from Tuesday/Wednesday
- North Star: Weekly completed purchases with no condition-related dispute or return.
- Supporting signals: % of buyers who message a seller after viewing a listing · seller response rate within 24h · % of sellers who complete the listing/publish flow.
- Draft MVP hypothesis (Tuesday):
  - In: Condition badge on the listing + minimum real photos required to publish + "doesn't match description" report.
  - Out: Mandatory high-resolution photos; seller response-time indicator; verified-seller badge; "ask a question" template.

## 1. RICE scores

| Feature | Reach | Impact | Confidence | Effort | RICE = (R×I×C)/E | Rank |
|---|---|---|---|---|---|---|
| Condition badge on the listing | 9 | 3 | 90% | 1 | 24.3 | 1 |
| Minimum real photos required to publish | 9 | 2 | 85% | 1 | 15.3 | 2 |
| "Doesn't match description" report | 9 | 2 | 90% | 2 | 8.1 | 3 |
| Seller response-time indicator | 6 | 2 | 70% | 2 | 4.2 | 4 |
| Quick "ask a question" template | 5 | 1 | 75% | 1 | 3.75 | 5 |
| Mandatory high-resolution photos | 9 | 0.5 | 60% | 2 | 1.35 | 6 |
| Verified-seller badge | 5 | 1 | 50% | 3 | 0.83 | 7 |

*(Impact: 3 massive · 2 high · 1 medium · 0.5 low · 0.25 minimal. Confidence as %. Effort in person-weeks. Reach = relative weekly reach across buyers/sellers, 1–10 scale for comparison.)*

---

## 2. MoSCoW (for the MVP)

- **Must:** Condition badge on the listing; minimum real photos required to publish; "doesn't match description" report.
- **Should:** Seller response-time indicator.
- **Could:** Quick "ask a question" template.
- **Won't (for now):** Mandatory high-resolution photos; verified-seller badge.

## 3. Value vs. Effort

- **Quick wins:** Condition badge on the listing; minimum real photos required to publish.
- **Big bets:** "Doesn't match description" report; seller response-time indicator.
- **Money pits (avoid):** Mandatory high-resolution photos; verified-seller badge.
- **Filler (low value, low effort):** Quick "ask a question" template.

*(Kano lens)*

| Feature | Kano tag |
|---|---|
| Condition badge on the listing | Basic |
| Minimum real photos required to publish | Basic |
| "Doesn't match description" report | Basic |
| Seller response-time indicator | Performance |
| Mandatory high-resolution photos | Performance |
| Quick "ask a question" template | Delighter |
| Verified-seller badge | Delighter |

## 4. North Star check (no orphans)

| Feature | Metric it moves (NSM / supporting) | Keep / defer / cut |
|---|---|---|
| Condition badge on the listing | North Star direct — closes the gap between listed and actual condition, the exact driver of disputes/returns | Keep |
| Minimum real photos required to publish | North Star direct — same mechanism, forces evidence of actual condition | Keep |
| "Doesn't match description" report | North Star direct, but as the measurement instrument, not a preventer — it's the only source of dispute data; without it the North Star can't be tracked at all | Keep |
| Seller response-time indicator | Supporting — moves "seller response rate within 24h" and, indirectly, "% of buyers who message a seller" | Keep, as support |
| Quick "ask a question" template | Supporting — lowers friction on "% of buyers who message a seller after viewing a listing" | Keep, as support |
| Mandatory high-resolution photos | Supporting, weak and redundant — minimum-photos already forces real evidence; resolution adds marginal clarity, low confidence it changes dispute rate | Defer |
| Verified-seller badge | Supporting, weak — a "reliable history" badge speaks to general trust, not specifically whether *this* item's condition matches its listing | Defer |

## 5. Confirmed MVP

- **In:** Condition badge on the listing; minimum real photos required to publish; "doesn't match description" report.
- **Out (and why):**
  - Seller response-time indicator — Should in MoSCoW, Big bet in Value-vs-Effort, Keep-as-support in the North Star check. Real value, but not essential to launch; moves to Next, not Won't.
  - Quick "ask a question" template — Could / filler / weak support across all three frameworks. Moves to Next.
  - Mandatory high-resolution photos — Won't (for now); redundant with the minimum-photos rule, low confidence it changes dispute rate.
  - Verified-seller badge — Won't (for now); Delighter, doesn't speak to condition accuracy specifically.
- **Changed since Tuesday (and why):** The core in/out call didn't change — badge, minimum photos, and the report were "in" on Tuesday and stay in today. What changed is the strength of the reasoning: on Tuesday the report was included mostly because "the North Star can't be measured without it," a single justification. Today it's confirmed independently by RICE (rank #3, RICE 8.1), MoSCoW (Must), and the North Star check (Keep, as the measurement instrument) — four lenses converging on the same call is stronger ground than one instinct. The other change is a resolution, not a reversal: the response-time indicator stays out of the MVP, but it's now explicitly marked as the top Next candidate (Should + Big bet + Keep-as-support all agree it has real value), distinct from the ask-question template, high-res photos, and verified badge, which only ever scored weak.

## 6. One defended call

**Feature:** "Doesn't match description" report — in, and the trade-off being made.

> This is the priciest, least obviously user-facing piece of the MVP, and the fair question is "why spend 2 person-weeks on a report tool instead of a fourth trust signal buyers can actually see?" It ranked #3 on RICE (8.1) and Must on MoSCoW, but that score isn't about preventing disputes — it's about measuring whether the badge and minimum-photos rule are actually working. Without a way for buyers to flag a mismatch, the North Star ("completed purchases with no condition-related dispute") is unmeasurable, and we'd be shipping the two trust features on faith with no way to tell if they moved anything. The trade-off: two weeks that could go toward the response-time indicator — the strongest Next candidate — are spent instead on the only source of ground-truth data on whether this MVP is working at all. Shipping the fix without a way to check whether it fixed anything isn't a real launch, it's a guess.
