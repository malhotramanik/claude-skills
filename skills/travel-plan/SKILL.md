name: travel-plan
description: "Plan a baby-friendly trip — destination research, flights, hotels, baby-friendly activities, packing lists, itinerary, and a comprehensive trip document."

# Baby-Friendly Trip Planner

Plan end-to-end trips for families with young children (0-36 months). Gather inputs through conversational Q&A, research current information via web search, build an age-appropriate itinerary, and generate a comprehensive trip document.

ARGUMENTS: The user may provide any combination of destination, dates, child age, or other details inline. Parse whatever is provided and skip questions that are already answered.

---

## Phase 1: Input Detection & Questions

Parse the user's prompt for any already-provided information: destination, dates, number/ages of children, origin city, budget, travel style, accommodation preference, dietary needs, or constraints.

Ask the following questions **one at a time**, skipping any already answered. If the user volunteers extra information in any answer, skip subsequent questions that are covered.

> Use multiple choice format where possible. Keep a conversational, friendly tone throughout.

1. **Children** — "How many little ones are coming, and how old are they (in months)?"
   - Adjust all recommendations based on developmental stage:
     - Pre-crawling (0-6 months): needs frequent feeds, lots of gear, minimal mobility
     - Crawling (6-10 months): needs baby-proofed spaces, starting solids
     - Early walking (10-15 months): unsteady on feet, into everything, needs safe exploration space
     - Toddling (15-24 months): walking confidently, tantrums emerging, opinionated about food
     - Active toddler (24-36 months): running, climbing, needs stimulation, can handle more activities

2. **Allergies & dietary needs** — "Any allergies or dietary needs to plan around? For example:"
   - a) Formula type (cow's milk, soy, hypoallergenic, breastfed)
   - b) Food allergies
   - c) No dietary concerns
   - **This is safety-critical** — affects destination suitability, packing, and restaurant choices.

3. **Destination** — "Where are you thinking of going?" If the user is open, suggest 3-4 baby-friendly destinations based on other inputs (season, budget, origin city) with brief reasoning for each. Use multiple choice.

4. **Dates & duration** — "When are you planning to go, and for how long?"

5. **Origin city** — "Where will you be flying from?"

6. **Budget range** — "What's your rough budget?"
   - a) Budget — keep costs low, prioritize value
   - b) Moderate — comfortable but not extravagant
   - c) Luxury — convenience and comfort are top priority
   - d) Specific number (ask them to share)

7. **Travel style** — "How do you like to travel?"
   - a) Relaxed — slow pace, lots of downtime, go with the flow
   - b) Moderate — a few planned activities but plenty of flexibility
   - c) Packed — see and do as much as possible (with baby-friendly adjustments)

8. **Accommodation preference** — "Where do you prefer to stay?"
   - a) Hotel — convenience, room service, cribs provided
   - b) Airbnb/vacation rental — kitchen, laundry, more space
   - c) Resort — all-in-one, pools, kids clubs
   - d) Family-friendly chain — reliable, loyalty points, baby amenities

9. **Must-haves or dealbreakers** — "Anything that's a must-have or a dealbreaker? For example: needs a pool, no long drives, must have laundry access, wants beach, needs to be stroller-friendly."

---

## Phase 2: Research

After gathering all inputs, use **WebSearch** for general queries and **WebFetch** for specific URLs (airline pages, government travel advisory sites, hotel booking pages).

Research the following topics:

1. **Flights** — routes from origin to destination, approximate prices, which airlines are best for babies on this route (bassinets, pre-boarding, seat selection)
2. **Accommodation** — baby-friendly options matching their preference and budget. Look for: cribs, kitchen access, laundry, proximity to attractions, baby-proofed rooms
3. **Weather** — conditions at the destination during their travel dates. Flag any concerns (extreme heat, monsoon season, etc.)
4. **Baby-specific logistics** — visa/passport requirements for infants, nearby hospitals and clinics, formula and diaper brand availability at destination, pharmacy locations
5. **Car seat & stroller** — car seat laws at destination, car seat rental options, stroller-friendly public transport, whether to bring or rent a stroller
6. **Activities** — baby-friendly attractions, parks and green spaces, restaurants with high chairs and changing facilities, stroller-accessible areas, indoor play options for bad weather days
7. **Travel advisories** — any safety concerns, health advisories, or vaccination requirements for the destination

> Present a summary of all findings to the user BEFORE building the itinerary. Let them flag anything that changes the plan (e.g., "flights are too expensive that week" or "let's skip that area").

> Include a freshness disclaimer on all prices and availability: "Prices as of [today's date] — verify before booking."

> If web search fails or returns poor results for any topic, proceed with available data. Clearly flag the gaps to the user and suggest they verify those items manually.

---

## Phase 3: Itinerary Building

Build a **day-by-day itinerary** that respects the baby's routine and the family's travel style.

Account for:

- **Baby's routine by age:**
  - 0-6 months: 3-4 naps/day, frequent feeds every 2-3 hours
  - 6-12 months: 2 naps/day (morning + afternoon), 3 meals + milk feeds
  - 12-18 months: 1-2 naps/day (transitioning), 3 meals + snacks
  - 18-36 months: 1 nap/day (after lunch), 3 meals + snacks
  - Plan to be back at accommodation by 6-7pm for bedtime routine

- **Pacing:** No more than 1-2 activities per day. Build in buffer time for meltdowns, diaper changes, and unexpected delays. Include "nothing planned" blocks.

- **Mix of activities:** Balance sightseeing with downtime. Include baby-friendly spots (parks, splash pads, zoos) alongside parent interests. Alternate high-stimulation and low-stimulation activities.

- **Logistics:** Note travel time between locations. Flag stroller accessibility. Note car seat needs for any driving segments. Suggest the best time of day for each activity based on baby's nap schedule.

> Present the itinerary conversationally to the user. Ask if they want to adjust anything before generating the final document.

---

## Phase 4: Document Generation

After the user approves the itinerary, generate the trip document.

**File path:** `trips/YYYY-MM-DD-<destination-slug>.md` relative to project root.
- Create the `trips/` directory if it doesn't exist: run `mkdir -p trips`
- Slugify the destination: lowercase, replace spaces with hyphens (e.g., "New York City" → `new-york-city`)
- If a file for the same trip already exists, ask the user: overwrite the existing file, or create a new version with a `-v2` suffix?

**Document structure:**

```markdown
# Trip to [Destination]

## Trip Overview
- **Destination:** [destination]
- **Dates:** [start date] — [end date] ([N] days)
- **Travelers:** [adults] + [children with ages]
- **Budget:** [tier or amount]
- **Travel Style:** [relaxed/moderate/packed]
- **Accommodation:** [preference]

## Flights
[Recommended flight options with airlines, times, approximate prices, and links where available. Include tips for flying with baby: bassinet seats, bottle warming, ear pressure on descent, etc.]

## Accommodation
[Recommended options with prices, links, and why each is baby-friendly. Note: crib availability, kitchen, laundry, proximity to key attractions.]

## Day-by-Day Itinerary

### Day 1: [Date] — Arrival
**Morning:** [activity or travel]
**Nap window:** [time range]
**Afternoon:** [activity]
**Dinner:** [restaurant or plan]
**Notes:** [baby-specific tips for the day]

[Repeat for each day]

### Day N: [Date] — Departure
[Departure logistics, airport tips]

## Packing List

### Baby
- Diapers (pack [N] per day + extras)
- Formula/milk supplies + bottles
- Baby food/snacks
- Medications (infant Tylenol, gas drops, teething gel)
- Car seat (or note rental details)
- Stroller (or note rental details)
- Portable crib/travel crib (if not provided by accommodation)
- Sleep sack or familiar blanket
- Favorite toys (2-3 max)
- Baby carrier/wrap
- First aid kit (thermometer, band-aids, saline drops)
- Sunscreen (baby-safe) + hat
- Extra change of clothes in carry-on
- Plastic bags for dirty diapers/clothes

### General
- Passports + copies
- Travel insurance documents
- Chargers + power adapters
- Comfort items for the flight
- [Destination-specific items]

## Baby Logistics
- **Nearest hospital/clinic:** [name, address, phone, distance from accommodation]
- **Pharmacies:** [locations near accommodation]
- **Formula/diapers:** [local brands available, where to buy]
- **Car seat rental:** [provider, cost, booking link]
- **Emergency number:** [local emergency number]

## Booking Checklist
- [ ] **8+ weeks before:** Book flights, check passport validity for all travelers (infant passports!)
- [ ] **6 weeks before:** Book accommodation, request crib if needed
- [ ] **4 weeks before:** Book car seat rental, stroller rental if needed, reserve airport lounge
- [ ] **2 weeks before:** Book restaurant reservations, activity tickets, arrange travel insurance
- [ ] **1 week before:** Start packing, download offline maps, confirm all reservations
- [ ] **Day before:** Charge devices, pack carry-on bag, prepare snack bag for travel day

## Travel Insurance
[Guidance on medical coverage for infants abroad. What to look for: emergency medical coverage, trip cancellation, medical evacuation. Note any destination-specific considerations.]

## Tips & Notes
- [Destination-specific baby travel tips]
- [Cultural considerations for traveling with babies]
- [Useful phrases in local language: "baby," "diaper," "milk," "doctor," "hospital," "help"]
- [App recommendations for the destination]
```

Write the document using the **Write** tool. Confirm to the user that the file has been saved and share the file path.
