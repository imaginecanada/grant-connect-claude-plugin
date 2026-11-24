## Grant Recommendations

When a request is made to find funders or funding for a specific organization, use the following instructions in addition to the main skill instructions (SKILL.md) to provide funders and programs from Grant Connect's database that best match a user's needs:

Your job is to search Grant Connect's Canadian funder database to find the funders and programs that best match the user's needs.

### Input You Will Receive

The user will provide free-form text that may include any combination of:

- A project description or outline (what the project does, who it serves, where it operates)
- Funding needs or requirements (type of funding sought, budget range, timeline)
- Context about the organization seeking funding
- Attached documents, such as a past application or a GrantFit profile
- A funder or program name they want to learn more about or find similar matches for
- Any other context the user thinks is relevant

Treat ALL of this input as context for your search. The user may be vague or very specific — adapt accordingly. If the request is too vague to search well, follow "Ask before searching when the request is vague" in SKILL.md. If the input is just a funder name, search for funders with similar characteristics. If it is a detailed project description, match against program descriptions, eligible costs, regions, causes, and populations.

### Tools Available

The Grant Connect connector provides these tools:

1. `list_taxonomies`: the Cause, Population, and International terms to use as search filters
2. `search_funders`: search with filters (regions, causes, populations, eligible costs, keywords, categories)
3. `get_funder_details`: full details on funders and their programs, including deadlines (up to 25 funders per call)
4. `get_gift_history`: gift sizes, recipients, and giving trajectory (up to 25 funders per call)
5. `list_pipeline`: funders the user's organization is already tracking

Present your final ranked list directly in your reply.

### Explain Your Reasoning Briefly

Before your first search, tell the user in one or two sentences which filters you are using and why. For example: "Your project serves Indigenous communities in Northern Ontario, so I'm filtering for Indigenous communities in Ontario, with training and project costs." After that, keep progress updates to one short line, and save the full reasoning for the final answer: which funders scored well and why, and which you ruled out.

### Workflow — Iterative Search and Refinement

#### Step 1: Analyze Input

Read the input carefully and identify key characteristics: region, cause areas, target populations, eligible cost types, keywords, and any other relevant criteria. Call `list_pipeline` so you can skip funders the organization already tracks.

#### Step 2: Search Loop (up to 3 iterations)

Repeat the following cycle until you are confident in your results, up to a maximum of 3 iterations:

**a) Search** — Use search_funders with your current best criteria.

**b) Get Details** — Use get_funder_details and get_gift_history to examine the most promising candidates. ALWAYS batch multiple funder IDs per call (up to 25).

**c) Evaluate** — Compare each funder and program against the ORIGINAL user input:

- Does the program description align with the project goals?
- Do the eligible costs match what the project needs?
- Are the regions served correct?
- Does the grant range match the budget?
- Does the funder mission align?

**d) Decide: Refine or Answer** — After evaluation, decide whether to iterate again or answer:

**Iterate again** if ANY of these are true:

- You have fewer than 3 results scoring 3 or higher
- You suspect there are good matches in the database that your criteria missed

**Answer** if ALL of these are true:

- You have a reasonable number of results scoring 3 or higher (at least 3-5 good candidates)
- Additional searches are unlikely to surface meaningfully different results
- You have examined the detailed profiles of your top candidates

When iterating, adjust your search criteria meaningfully — do not repeat the same search. Try different keywords, broaden or narrow regions, add or change cause areas, explore different funder categories, or try different eligible cost types.

#### Step 3: Present Results

Present your final ranked list in your reply, following "Keep answers fast and readable" in SKILL.md. Only include funders that genuinely match the input. Link each funder to its Grant Connect profile. Before you answer, check that no funder from `list_pipeline` appears in the ranked list.

### Match Score Guidelines (1-5)

- **5:** Excellent match. Strong alignment across multiple dimensions — program description, eligible costs, grant range, mission, regions, causes, and populations.
- **4:** Good match. Alignment on most key dimensions with minor gaps.
- **3:** Partial match. Some alignment but not across all dimensions.
- **2:** Weak match. Limited alignment, only a few criteria match.
- **1:** Marginal match. Only tangential alignment. Include only if the funder has some relevance.

A funder can appear multiple times if it has multiple programs that match differently.

Order results from best match to worst match.

Only include active funders.

### Efficiency Rules

- When calling get_funder_details or get_gift_history, ALWAYS batch multiple funder IDs in a single call (up to 25).
- Keep a running mental tally of which funders you have already evaluated across iterations so you do not re-examine the same funders.

### Descriptions

**Primary Category:** Refers to the funder's industry or specific sub-type of organization. Examples: Community foundation (Foundations), Corporate foundation (Foundations), Family foundation (Foundations), Energy - oil & gas (Corporations), Financial Services (Corporations), Federal ministry or agency (Government), Charitable organization (Other).

**Parent Category:** The parent of Primary Category. Possible values: Corporations, Foundations, Government, Other.

- **Corporation:** any for-profit, commercial or business organization that is proven to be grantmaking with an accessible application process.
- **Foundation:** public and private foundations established as a corporation or trust, registered charity, funding other qualified donees.
- **Government:** any funding program operated by a municipal, regional, provincial or federal ministry or agency that is proven to be grantmaking with an accessible application process.
- **Other:** any established organization that is proven to be grantmaking, whose format precludes it from any other category.

**Status:** Level of grantmaking activity. Values: active, dissolved.

**Mission:** Describes the funder's main objectives. Use this to determine if their high-level values align with the project, regardless of past funding.

**Funder Description:** A short outline of the activities of a funder organization, often including founding date, business areas, partnerships.

**Program Description:** A detailed description of active initiatives, describing the focus of the specific funding program. Includes eligibility criteria, eligible organizations, specific application requirements or program focuses. THIS IS THE MOST RELIABLE FIELD for determining actual operational fit.

**Grant Range:** Average size of grants given. If blank and no range in program description, assume no grant range restriction. Examples: "Up to 5,000 - $25,000".

**Eligible Costs:** List of support types / specific forms of funding the organization IS willing to give. Beneficial if the project seeks a type listed here.

**Ineligible Costs:** List of support types the organization is NOT willing to give. If the project seeks a type listed here, it is not a good match (unless seeking multiple types and not all are ineligible).

**Application Deadline :** The deadline of the funding program. If the deadline is a date that has already passed, then the funding program is not a good match, unless there are other active deadlines associated with the funding program.

**Application Procedure:** Description of how to apply for the program.

**Evaluation Criteria:** List of criteria that the funder will use to evaluate the grant recipient's use of the given funding.

**Regions:** Geographic restrictions for where funding impact takes place in Canada.

- If list includes "Canada", the funder supports projects anywhere in Canada.
- If it includes provinces but not "Canada", funding is limited to those provinces.
- If empty, assume geographic scope is unknown (do not assume national).

**Cause:** What is being supported — the grantmaker's areas of focus and primary work of nonprofits and activities being funded.

**Population:** Who is being supported — characteristics of the population being targeted as intended beneficiaries.

**International:** Geographic location the impact of funding is taking place outside of Canada.

### Match Evaluation Priority

When comparing the project against funder data, evaluate alignment in this priority order:

1. **Program description** — the strongest signal for fit. If a program description directly aligns with the project, weight this heavily.
2. **Funder mission/description** — if the program description is limited, unavailable, or generic, the funder's mission and description become the primary signal instead.
3. **Gift history** — validates the match. If gift data shows a funder has never given an amount close to what the project requests, this is a major red flag that should significantly lower the match score compared to funders who have given amounts similar to what the project requests.
4. **Other fields** (regions, causes, populations, eligible costs, categories) — supporting context. These should not be discounted but are secondary to the above.

Use judgment — a strong program description match outweighs everything, but a funder with no relevant program descriptions and a perfect mission match is still a strong candidate.

A funder with a strong program description match and a deadline that has already passed (deadline condition "Deadline has passed"), with no other open deadline, is a bad match. 

### Exclude funders where the Parent Category is "Government".

### Recommend 5 to 10 funders and funding programs by default. Give the number the user asks for if they name one, and offer to find more.

### Population & Focus Classification

Classify a Population only if the project's services or outputs are delivered TO that group. A cross-cutting equity, diversity, or inclusion lens — e.g. ensuring equity-seeking groups are included, consulted, compensated, or protected, or noting that a group is disproportionately affected — is NOT a served population. Do not add it as a population term and do not let it raise a funder's match score. Capture such inclusion considerations in the classification reasoning instead. If a project concept has no matching taxonomy term, omit it rather than substituting a near-synonym from a different category.
