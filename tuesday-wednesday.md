# ReNest Mini-PRD — Adriel Mounzón Baspineiro

## Problem Frame
- Problem statement: Buyers can't tell whether a listed item's actual condition matches its photos and description, which makes them hesitant to contact the seller and pushes them toward other platforms.
- Persona: Sonia, 30, furnishing her new apartment on a tight budget. She can't verify an item's actual condition from photos and descriptions alone, and has arrived at pickups to find items visibly more worn or damaged than pictured — wasting a trip and eroding her trust in listings.
- North Star Metric: Weekly completed purchases with no condition-related dispute or return — a buyer contacts a seller, buys the item, and the transaction closes without the buyer flagging that the item didn't match its photos or description.
- Value proposition: For buyers on a tight budget who can't judge a used item's real condition from a listing, ReNest surfaces enough trustworthy signal — clear condition details, real photos, responsive sellers — that they can reach out with confidence. Less time wasted on misrepresented items, more good sofas found nearby.

## Goals & success metrics
- North Star: Weekly completed purchases with no condition-related dispute or return.
- Supporting signals:
  1. % of buyers who message a seller after viewing a listing.
  2. Seller response rate within 24h.
  3. % of sellers who complete the listing/publish flow once started — guardrail to catch drop-off from the added badge/photo steps.

## Candidate features
1. Condition badge on the listing — seller picks a status (new / good condition / visible wear) shown on the card and item detail.
2. Minimum real photos required to publish — app blocks publishing if there are fewer than a set minimum of photos.
3. Seller response-time indicator — shows how fast that seller replies on average.
4. Quick "ask a question" template — buyer can send a pre-built question about condition before committing.
5. "Doesn't match description" report — buyer can flag a listing after purchase.
6. Verified-seller badge — visual check for sellers with a reliable history.
7. Mandatory high-resolution photos — enforces a minimum photo resolution.

## Sample requirements

Feature: Condition badge on the listing
- Functional: seller must choose a status from a closed list (new / good condition / visible wear) before publishing.
- Functional: the badge is visible on both the listing card and the item detail view.
- Non-functional: the badge must be distinguishable by color and text, meeting WCAG AA contrast.

Feature: Minimum real photos required to publish
- Functional: system blocks publishing if the listing has fewer than 3 photos.
- Non-functional: each photo upload completes in under 5 seconds on a 4G connection.

Feature: Mandatory high-resolution photos
- Functional: system rejects photo uploads below a minimum resolution (1080px on the shortest side).
- Non-functional: resolution validation completes in under 1 second per photo.

Feature: "Doesn't match description" report
- Functional: buyer can only file the report from a completed order, within a set window after pickup/delivery.
- Functional: buyer must pick a reason (e.g., condition worse than described, wrong item) before the report is submitted.
- Non-functional: a filed report is reflected in the North Star metric within 24h.

## MVP hypothesis
- In: Condition badge on the listing + minimum real photos required to publish + "doesn't match description" report.
- Out: Mandatory high-resolution photos; seller response-time indicator; verified-seller badge; "ask a question" template.
- Why: the core problem is that Sonia can't judge an item's real condition from the listing. Badge + minimum photos attack that directly and are the cheapest build for the most immediate impact. The report is also included despite adding scope, because without it the North Star can't be measured at all — it's the only source of dispute data. The rest stay out because they depend on historical data that doesn't exist yet or solve a later step in the journey.

## Rough roadmap — Now / Next / Later
- Now: Condition badge on the listing; minimum real photos required to publish; "doesn't match description" report.
- Next: Seller response-time indicator; quick "ask a question" template.
- Later: Mandatory high-resolution photos; verified-seller badge.
