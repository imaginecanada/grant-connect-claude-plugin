---
name: prospect-research-grant-connect
description: "Find and qualify funders for Canadian nonprofits and charities using Grant Connect by Imagine Canada. Use whenever someone asks who might fund their organization, project, or program: foundations, grants, funding programs, corporate funders, sponsors, or donors. This includes plain questions like \"who funds...\", \"which foundations support...\", \"grants for my food bank\", \"top funders for me\", upcoming grant deadlines, or funding for overhead, operations, capital, or equipment in a Canadian city or province. Also use for funder fit, gift history, pipeline building, prospect scoring, and cultivation strategy. Use for French requests too: fondation, bailleur de fonds, subvention, financement, organisme, Connexion subvention. Use it even when the user does not mention Grant Connect or prospect research."
---

# Prospect Research for Canadian Nonprofits

This skill guides strategic prospect research for charitable and nonprofit fundraisers in Canada, with particular focus on foundation and institutional funders. It draws on best practices from the field — including frameworks articulated in *From the Ground Up: Prospect Research for Nonprofits* by Sarah Marcotte and Katherine Scott — and is designed to be used alongside Grant Connect by Imagine Canada.

The goal is not just to find prospects, but to distinguish between those that appear promising on the surface and those that represent genuine, long-term alignment.

## When to use this skill

Use this skill for any request to find, compare, or qualify funding for a Canadian nonprofit or charity, even when the user never says "prospect research" or "Grant Connect". Newer and part-time fundraisers usually ask in plain language. Treat all of these as prospect research:

- "Which arts funding programs support overhead expenses in Calgary?"
- "I'm a food bank in Halifax looking for $25,000 for a new refrigerated truck. Who funds that?"
- "What are some grant opportunities with upcoming deadlines for homelessness charities in Halifax?"
- "Find family foundations that fund children and youth learning initiatives."
- "We're an organization that supports anglophone rights in Quebec. Top funders for me?"
- "Organization based in Montreal, small budget, little time. Give me the names of 5 foundations."
- « Organisme en santé mentale basé à Montréal. Petit budget, pas beaucoup de temps. Donne-moi les noms de 5 fondations. »
- « Quelles fondations financent les programmes jeunesse au Québec? »

If the user is a Canadian nonprofit asking who might fund them, load this skill and use the Grant Connect tools. Do this before any web search.

## Source order: Grant Connect first

Grant Connect is the primary source for every funder question.

1. **Search Grant Connect first.** Always start with the Grant Connect tools (`search_funders`, `get_funder_details`, `get_gift_history`, `list_pipeline`). Do not open with "I'll search Grant Connect and the web".
2. **Use the web only to fill a specific gap,** such as a current application form, a funder's latest annual report, or a news item about a priority change. Use it as well when the user asks for it directly.
3. **Label web findings.** When an answer mixes sources, say which facts came from Grant Connect and which came from the web, and link both.
4. **Respect "Grant Connect only".** If the user asks to stay in Grant Connect, do not search the web at all.

## Ask before searching when the request is vague

A short clarifying question saves a long, unfocused search. When the request is missing details that change the results, ask up to three quick questions in one message, then search. The details that matter most:

- Where the organization works (city, region, or province)
- What the money is for (programs, operations or overhead, capital or equipment, a specific project)
- Roughly how much is needed, and the organization's annual budget

If the user has a GrantFit profile or prompt in Grant Connect, invite them to paste it. It already describes their organization and funding needs.

If the request is specific enough to search, search right away and skip the questions. If the user says they are short on time, make reasonable assumptions, state them in one line, and search.

## Keep answers fast and readable

- **Default to a ranked list or a simple table.** Show funder name, why it fits, typical gift size, and next deadline. Do not build dashboards, charts, or other artifacts unless the user asks for one.
- **Never show internal funder IDs.** Refer to funders by name and link each one to its Grant Connect profile (`grant_connect_url`).
- **Check a shortlist in depth, not everything.** Run detailed checks (`get_funder_details`, `get_gift_history`) on your top candidates, batched in one call each, then offer to go deeper on more.
- **Keep progress updates to one short line.** Don't narrate every step.
- **Answer in the user's language.** If the user writes in French, reply in French and use Grant Connect's official French terms (for example, Grant Connect is *Connexion subvention*). <!-- TODO: add Imagine Canada's French glossary here -->

- **Keep pipeline funders out of the new list.** A funder returned by `list_pipeline` is already being cultivated. Never put it in the ranked list of new suggestions. If it's relevant, mention it once in a separate short "Already in your pipeline" line, with any useful update (such as an upcoming deadline).

## Reference files

Two longer guides live in separate files. Read them when the task needs them:

- **`references/finding-funders.md`**: read this before you search whenever the user wants funders found, recommended, or ranked. It has the search steps, match scoring, and exclusion rules.
- **`references/grant-connect-fields.md`**: read this when you need to interpret a Grant Connect field in depth (for example capacity score, open to requests, or a funder's financial history).

## The Core Mindset: Research as Strategy, Not Search

Prospect research is not a Google exercise. It is a structured analytical practice aimed at one question: *"Should we invest relationship-building time in this funder, and if so, how?"*

Before touching any database, ground your research in three organizational truths:

1. **Your case for support** — What specific, fundable need(s) are you researching for? Vague asks produce vague matches.
2. **Your organizational capacity** — Can you fulfill reporting requirements, attend site visits, or meet geographic restrictions this funder may impose?\*
3. **Your relationship inventory** — Who do you already know? Board members, volunteers, and staff often have hidden connections to funders that should be surfaced first.

Skipping this step is the single most common reason organizations pursue bad-fit funders.

\*Effective research requires immediate clarity on your required funding thresholds. If a foundation's typical gift is only $1,500 while your project demands a minimum investment of $50,000, you must acknowledge this financial disconnect early to avoid being misled by mission alignment alone. While explored in detail later, this high-level capacity check is a critical first step in preventing strategic distraction.

## The Prospect Research Hierarchy

Not all research tasks are equal. Work in this order:

### 1. Mission Alignment (Non-Negotiable)

A funder may have the capacity and history of giving in your sector, but if their current priorities do not intersect with your work, pursuit is wasted effort.

In Grant Connect, look for:

- **Keywords in granting history:** Do their past grants describe language similar to your own case for support? Funders often use the same language across cycles.
- **Strategic plan signals:** Some foundations publish priorities publicly. Where they don't, their grant patterns over 3–5 years ARE their strategy.
- **Emerging vs. mature priorities:** Is your issue area something they've funded for a decade (established priority) or something they recently started funding (possible emerging interest or one-time experiment)?

### 2. Warm Leads Before Cold Prospects

Always begin with your existing network. A lukewarm connection to a funder is worth more than a perfect profile match with no relationship. Before opening Grant Connect, ask:

- Has this funder supported us before?
- Do any board members, major donors, or volunteers have a relationship with this funder?
- Has a peer organization with whom we have goodwill received support from them?

Document these connections in your CRM before anything else.

### 3. Geographic and Demographic Fit

Canada's philanthropic landscape is regionally fragmented. Many foundations — even large ones — have explicit or implicit geographic preferences.

Red flags to look for in Grant Connect:

- 100% of grants go to one province or city (and it isn't yours)
- Their stated geographic focus includes Canada-wide but actual grants skew heavily to one region
- Their registered address is in one province but their grants cross borders — this may indicate a national funder or may be a small family foundation filing nationally; distinguish these

### 4. Financial Capacity and Grant Size Fit

Alignment means nothing if the grant size doesn't match your ask.

**The "10% rule":** As a starting heuristic, most funders are uncomfortable with a single grant representing more than 10% of their annual granting budget. Use Grant Connect disbursement data to estimate their annual giving and calibrate your ask.

Look for:

- Average grant size (not maximum — the range matters)
- Minimum grant thresholds (some foundations won't give below $25,000 — irrelevant if you need $5,000)
- Multi-year vs. single-year history (a funder that consistently gives multi-year grants is a different relationship than one-time project funders)

## The Alignment Matrix: Surface Fit vs. True Fit

This is the most important analytical skill in prospect research. Many prospects look good from the outside. Fewer are genuinely worth pursuing.

### Surface Fit Signals (Common but Misleading)

| Signal | Why It's Misleading |
|---|---|
| Funder gives in your sector | Sector ≠ your specific issue or approach |
| Funder is large and well-known | Competition is highest; success rates lowest |
| Funder has given to similar orgs | Similar is not the same; approach may differ |
| Funder's website says "open to proposals" | Many are effectively invitation-only |
| Funder gave to you once, years ago | Priorities change; don't assume renewal |
| No explicit exclusions for your type of work | Absence of restriction ≠ active interest |

### True Alignment Indicators (Weight These Heavily)

| Indicator | What It Tells You |
|---|---|
| Repeated grants to similar org types | Sustained/increasing interest (i.e. increasing in granting amounts) |
| Grant language mirrors your case for support | Their frame and yours are compatible |
| Multi-year grants in your area | They believe in long-term investment here |
| Funder has contacted peer orgs like yours | They are proactively seeking this work |
| Board/staff with personal connection to your issue | Values-level alignment, not just strategic |
| Grants grew in size over time to similar orgs | They deepen relationships — not just samplers |
| Geographic focus exactly matches your reach | No tension between their mandate and yours |

### The "So What" Test

After mapping alignment signals, ask yourself: *"If I were a program officer at this foundation and received our proposal, would I feel this was clearly within my mandate to fund?"* If you're uncertain, the prospect needs more research or more cultivation before a proposal is warranted.

## Reading Grant Connect Data Strategically

Grant Connect is a powerful tool, but raw data requires interpretation. Here's how to extract strategic insight from what you find.

### Granting History Analysis

Don't just look at whether a funder has given in your area. Analyze the trajectory:

- **Flat pattern:** Same organizations, same amounts, year over year → closed portfolio, relationship-dependent, hard to break in
- **Diversifying pattern:** New organizations appearing alongside old grantees → funder may be actively looking; opportunity exists\*
- **Declining pattern:** Fewer grants or lower amounts over time → may be winding down this priority or depleting assets; avoid multi-year dependency
- **Consolidating pattern:** Fewer but larger grants → funder may be shifting to deeper relationships; impressive track record required

\*Of particular interest are changes in % of funding directed to evolving interests, and indications of winding down by spending down assets.

### The Grantee Network Map

Who else does this funder support? This is strategic intelligence, not just background. Look for:

- **Peer organizations:** Can you request a warm introduction? Do they sit on shared coalitions or networks?
- **Complementary organizations:** Does the funder appear to be funding an ecosystem (advocacy + direct service + research)? Where do you fit?
- **Potential conflicts:** Do they already fund an organization doing identical work? Some funders avoid duplication; others see it as field-building.

### Contact and Governance Intel

In Grant Connect, when available:

- Note trustees and directors — cross-reference with your own board network
- Look for named program officers or staff — a named contact signals a funder that engages; absence suggests self-directed or advisor-managed giving
- Review reported financial history - total assets, revenues, and disbursements. What kind of picture is this drawing about their overall capacity and interests/structure? Does reported revenue fit with what's being paid out? Are their assets available, or nonliquid? Are there changes year over year to indicate trends like asset building or asset shedding?
- Family foundations with the same surname across all governance = likely donor-advised or family-controlled; relationship access is key; cold proposals rarely succeed

## Prospect Scoring Framework

Use this to prioritize your pipeline. Score each prospect across four dimensions, 1–5 each (5 = strongest):

| Dimension | What to Score |
|---|---|
| Mission Alignment | How closely do funder priorities match your current fundable project? |
| Capacity Fit | Does their typical grant size match your ask? |
| Relationship Access | Do you have a warm connection or plausible pathway to one? |
| Timing Readiness | Are they currently accepting proposals? Is this a good moment? |

**Total possible: 20**

- **16–20:** Strong prospect; prioritize cultivation and proposal
- **11–15:** Conditional prospect; identify what gap exists and how to close it
- **6–10:** Watchlist; monitor but don't invest significant cultivation resources now
- **5 or below:** Deprioritize; document reasoning and revisit in 12–18 months

A perfect alignment score (5/5) with no relationship access (1/5) is still a conditional prospect, not a strong one. Relationships are load-bearing in Canadian philanthropy.

## Common Prospect Research Mistakes to Avoid

### 1. The "Long Shot" Trap

Pursuing a high-profile funder because of brand recognition, not fit. Staff time spent on a 2% chance funder is time not spent on a 40% chance funder.

### 2. Treating Prospect Research as a One-Time Task

Funder priorities evolve. A foundation that didn't fit two years ago may be perfect now — and vice versa. Build a calendar-triggered review cycle into your pipeline management (annually at minimum for watchlist prospects; every 6 months for active cultivation).

### 3. Ignoring the Funder's Own Words

Grant Connect data tells you what funders have *done*. Annual reports, strategic plans, and social media tell you what they *want to do next*. Synthesize both.

It's important to flag when actual funding decisions contradict stated interests and restrictions, and when they signal evolving interests before formal statements and communications.

### 4. Proposing Before Cultivating

In Canadian foundation fundraising, a proposal to a funder with whom you have no relationship is a cold call. For funders below ~$50,000 in typical grant size, this can sometimes work. For larger asks, cultivation typically must precede the ask.

### 5. Conflating Income and Assets

A foundation with $50 million in assets does not give $50 million annually. Canadian foundations are required to disburse 3.5% of their assets annually on the first $1 million, and 5% on assets exceeding $1 million (the disbursement quota). Use this to estimate their annual giving envelope when exact figures are unavailable in Grant Connect.

### 6. Overlooking Smaller Funders

The most competitive space in Canadian philanthropy is large national foundations. Smaller regional and community foundations often have higher success rates for organizations with genuine local presence and relationships. Don't ignore them.

Treating all funders as the same is a pitfall. A community foundation with its own programs and donor-advised funds versus a family foundation with a clear mission and limited decision-makers versus a corporate foundation are going to behave very differently and have different needs and approaches.

## Moves Management: From Prospect to Partner

Prospect research informs the cultivation journey. The goal is not a grant — it is a funding relationship. Structure your moves accordingly:

**Stage 1: Identification (Research Phase)**
Use Grant Connect + network mapping + alignment matrix. Output: scored prospect list.

**Stage 2: Qualification (Deeper Research + Outreach)**
Confirm alignment via funder's own communications. Identify relationship pathway. Reach out to schedule an introductory conversation (not to pitch — to learn).

**Stage 3: Cultivation (Relationship Building)**
Invite to site visits, share impact updates, introduce to board members. Every touch should add value to the funder, not extract from them. The ask is earned.

**Stage 4: Solicitation (Proposal)**
A well-cultivated funder already knows what you're going to ask and is ready to receive it. Surprises in a proposal signal poor cultivation.

**Stage 5: Stewardship (Post-Grant)**
This is where the next grant is won. Report early, report honestly (including challenges), and make the funder feel like a mission partner, not a check-writer.

## Quick Reference: Questions to Answer Before Pursuing Any Prospect

Use these as your checklist when evaluating a funder from Grant Connect or any source:

- [ ] Does their granting history show active interest in our specific issue area?
- [ ] Is our geographic reach a match for their stated or implied focus?
- [ ] Does our typical project budget fit within their observed grant size range?
- [ ] Have they funded similar organizations in the last three years?
- [ ] Do we have a warm connection, or a clear path to one?
- [ ] Are they currently accepting proposals (or is the cycle open)?
- [ ] Is their grant-making trajectory growing, stable, or declining?
- [ ] Can we fulfill their likely reporting and accountability requirements?
- [ ] Have we been funded by them before, and if so, what was the outcome?
- [ ] Does anything in their governance, history, or recent communications raise concerns about values alignment or political risk?

If you cannot answer "yes" or "likely yes" to at least 7 of these, additional research is needed before pursuing.

## Working with Grant Connect: A Research Workflow

When using Grant Connect alongside this skill, follow this sequence:

1. **Check the pipeline first.** Call `list_pipeline` to see which funders the organization is already cultivating. Build on that work and don't re-suggest them as new prospects.
2. Start with a keyword search tied to your specific program or project, not your organization's broad mission.
3. Filter by geography first — irrelevant results are noise.
4. Sort by recency of grants — a funder active in 2018 but silent since is a different prospect than one active last year.
5. Pull the full grant history for any promising result — don't judge on a single grant. Summarize the largest, smallest, and average grant size over time in a sentence or a small table. Offer a chart only if the user asks for one.
6. Cross-reference the grantee list with organizations you know.
7. Score the prospect using the framework above before adding to your pipeline.
8. Document your reasoning — not just the score, but *why*. Future you (or your successor) will need to understand the thinking.

## A Note on Ethics in Prospect Research

Prospect research involves handling sensitive information. Maintain the following standards:

- Use only publicly available or appropriately disclosed data sources. Ensure that all information contained within the prospect profile can be clearly traced back to a reputable source - i.e., scholarly, peer-reviewed journals, government documents, well-established news sites, and higher education websites. Always include a list of sources consulted.
- Store prospect information securely and in compliance with CASL and PIPEDA
- Do not share prospect profiles outside the development team without explicit authorization from the senior leadership of the organization, and always anonymize individual donor details when sharing prospect profiles outside of the development team - i.e., provide giving ranges than exact amounts.
- Treat information about individual donors with particular discretion
- When in doubt about whether to document a piece of information, ask whether you would be comfortable if the prospect saw that it was in their file

The AFP and APRA both publish ethical guidelines for prospect research that are worth consulting and adopting as organizational policy.

This skill is designed to be used with Grant Connect by Imagine Canada. For technical questions about Grant Connect data or search functionality, consult Imagine Canada's documentation or support resources.
