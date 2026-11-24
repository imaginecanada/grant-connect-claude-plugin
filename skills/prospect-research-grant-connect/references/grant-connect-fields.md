## Data Definitions

The Grant Connect connector returns only some of these fields (funder category, status, open to requests, capacity score, mission and description, regions, causes, populations, programs with grant ranges, eligible costs, deadlines and contacts, plus gift history). The financial history, foundation activity, fiscal period, affiliations, and commentary fields are visible in Grant Connect itself. When one of them matters, point the user to the funder's Grant Connect profile.

### 1. Funder Table (Funder Record Object)

The Funder Record forms the structural basis of an organization's profile. These data points establish the overarching operational and financial framework of the grantmaker.

**Capacity Score**
*Context/Field: Funder - About*
Fundraising Importance: Automated Tiering & Prioritization. This is an auto-populated field that ranks a profile's total financial "capacity" based on standardized system criteria. For an MCP server or user, it serves as an instant prioritization metric to filter high-yield funders from small-scale donors without needing to manually audit years of financial sheets.

**Primary Category**
*Context/Field: Funder - About*
Fundraising Importance: Strategic Segmentation. It dictates whether a user is dealing with a funder that is defined as one of four Root Categories: Foundation, Corporation, Government, or Other. Within those Root Category terms, a funder is also defined as a more descriptive Category such as: Family foundation, Corporate foundation, Federal ministry, Community foundation, etc. Each type requires a completely distinct application, relationship cultivation, and submission strategy.

**Open to Requests (OTR)**
*Context/Field: Funder - About*
Fundraising Importance: Pipeline Qualification. This value (Yes, No, or Unknown) tells the fundraiser or AI model if the door is open for immediate proposals, or if the user must pivot to long-term network-building or board-mapping.

**Status**
*Context/Field: Funder - About*
Fundraising Importance: Viability Check. Identifies if a funder is actively operating (Active) or legally closed (Dissolved). Dissolved profiles restrict standard visibility but remain searchable so that historical gift tracking and past trends are preserved.

**Foundation Activity**
*Context/Field: Funder - Gift and Financial Activity*
Fundraising Importance: Operational Variance. Discloses if a foundation actually runs open grant cycles (Grantmaking), manages money exclusively for private donors (Administration of Donor Advised Funds), acts as a collector/distributor for a specific network (Fundraising Intermediary), spends funds directly related to the management of their own charitable programming such as some salaries, overhead costs, and related program spending (Direct Charitable Activity), is not currently engaging in any grantmaking activities (No Activity), or is new and has not engaged in grantmaking activities for at least two years (Unclassified).

**Fiscal Period End**
*Context/Field: Funder - Gift and Financial Activity*
Fundraising Importance: Strategic Timing. Tracks the funder's financial year-end. Many corporate or foundation funders look to exhaust their remaining giving budgets as this date approaches.

**Funder Contacts**
*Context/Field: Funder - Contacts*
Fundraising Importance: Board Mapping. Lists the Directors, Trustees, and Officers behind the organization. Funders use this to cross-reference their own board members and donors for warm personal connections.

**Affiliations**
*Context/Field: Funder - About*
Fundraising Importance: Network Expansion. Identifies other Grant Connect profiles operated by the same parent body (common with branches of a specific government agency). Users can leverage a past win at one affiliate to warm up an application at another.

**Special Note / Gift Commentary / Financial Commentary**
*Context/Field: Funder - About / Gift and Financial Activity*
Fundraising Importance: Risk Mitigation and Anomaly Tracking. Flags critical context like temporary funding halts, name changes, identical-name warnings, or data gaps. It saves users from catastrophic, outdated research mistakes.

**Funder Financial History**
*Database Location: Funder - Funder Financial History*
Data Type: Related Table / Numerical & Dropdown Fields
System Constraints: This data populates the financial data table on the Grant Connect user interface. The database administrator manually inputs these records for all funders except for Registered Canadian Foundations. Financial figures for Canadian foundations are automatically batch-imported from Canada Revenue Agency (CRA) T3010 tax filings.
Temporal Rule: Data is tracked by year. If a funder's fiscal year spans two calendar years (e.g., fiscal year 2025-26), the system strictly categorizes the data under the latter year (e.g., year 2026). Negative values are prefaced with a minus sign (-) in the backend, which the user interface automatically converts into standard accounting parentheses format (e.g., -n becomes (n)).

#### Core Financial Sub-Fields (By Funder Type)

An MCP server or user should map and interpret these specific financial fields based on the parent funder's profile category:

1. **Assets**
   Applicability: Foundations, Corporations, and Other (with or without a CRA charitable number). Typically not available for Government programs.
   Definition: The total asset valuation held by the funder organization at the close of their fiscal year.
   Fundraising Significance: This is the primary indicator of long-term sustainability. For foundations, it represents the principal endowment from which they generate investment returns to pay out grants. Monitoring asset fluctuations allows a fundraiser or predictive model to forecast whether a foundation will expand or contract its future grant allocations.
2. **Revenues / Net Earnings**
   Applicability: Foundations, Corporations, and Other.
   Definition: Revenues track the total influx of capital into the funder organization during the fiscal year (e.g., investment income, donations, corporate sales). Net Earnings specifically track a corporation's net profit after accounting for operating costs, taxes, and interest.
   Fundraising Significance: Measures immediate financial health. While assets show baseline wealth, revenues and earnings show cash flow. A sudden drop in a corporation's net earnings is a leading indicator that their corporate social responsibility (CSR) or community investment budget may face reductions in the upcoming cycle.
3. **Community Investment / Total Gifts**
   Applicability: Community Investment is specific to Corporations. Total Gifts applies to Foundations and Other profiles.
   Definition: The cumulative dollar amount actually distributed out to community initiatives, charities, or qualified donees during that specific fiscal year.
   Fundraising Significance: This reveals a funder's true "generosity baseline." Dividing the Total Gifts or Community Investment by the Number of Gifts provides a baseline look at real giving capacity, which prevents fundraisers from pitching a million-dollar proposal to an entity that only distributes $50,000 in total community funding per year.
4. **Direct Charitable Activity**
   Applicability: Foundations and Other profiles with a CRA charitable number.
   Definition: The financial amount spent by an organization directly on managing and executing its own internal charitable programs (such as staff salaries, institutional overhead, and direct program resources).
   Fundraising Significance: Contextual validation. High spending in this field alongside low standard "grant output" tells the user that the foundation primarily funds its own internal operations. However, for research-based organizations, this field often hides their actual research grant distributions, signaling that the fundraiser must look beyond standard tax filings to find those open grant streams.
5. **Number of Gifts**
   Applicability: Foundations, Corporations (if available), and Other profiles.
   Definition: The total volume of individual grant distributions or donations executed by the funder over the course of the fiscal cycle.
   Fundraising Significance: Determines the giving strategy. A high Total Gifts amount paired with a low Number of Gifts means the funder focuses on making a few large, transformative investments. Conversely, a high Number of Gifts indicates a "scattershot" strategy focused on distributing small, accessible micro-grants across many organizations.

### 2. Program Table (Program Record Object)

Funding Programs are distinct records nested under a Funder profile. They outline specific, structured grant streams that contain the narrow, action-oriented rules of engagement.

**Program Description** — *Programs* — Alignment Matching. Outlines the exact focus, mandate, and specific project criteria of that single grant stream. This is where a fundraiser or MCP keyword-matches project needs against funder parameters.

**Average Grant Range** — *Programs - Grant Details* — Request Calibration. Provides the baseline of what the funder expects to distribute per grant. This keeps the fundraiser from making an "ask" that is unreasonably high or low.

**Granting Region Description** — *Programs - Grant Details* — Geographic Qualification. Elaborates on or clarifies strict regional constraints for funding that are hyper-specific to that individual program stream.

**Application Procedure** — *Programs - Application Details* — Process Compliance. Explains exactly how to apply (e.g., online portal, email, hard copy) and what guidelines to review. Essential for preventing technical disqualifications.

**Program Deadlines (Date Field & Deadline Condition)** — *Programs - Program Deadlines* — Pipeline Scheduling. Tracks cut-off dates. Conditions like Recurring, Anticipated, or Ongoing tell the fundraiser whether they need to rush an application or wait for a predictable annual cycle.

**Program Eligible / Ineligible Costs** — *Programs - Program Eligible Costs* — Budget Vetting. Explicitly lists items the funder will pay for (e.g., capital, equipment) and what they won't. It ensures the line items in a budget request completely align with the funder's strict parameters.

**Program Contacts** — *Programs - Program Contacts* — Direct Relationship Management. Contains the direct phone numbers or emails of program-specific officers assigned to take inquiries. This is who the fundraiser contacts to vet a concept before applying.

### 3. Taxonomy Tables (Linked via Core Profiling)

These taxonomies are assigned through the editing process to describe a funder's historical trends and stated giving preferences. They act as the primary engine for advanced matching and user searches.

**Cause** — *Funder - Funding Details* — Sector Matching. Identifies the programmatic focus of the giving (e.g., Social Services, Life Sciences). Users use this to drill down to a list of funders that match their core mission.

**Population** — *Funder - Funding Details* — Demographic Targeting. Identifies the explicit human beneficiaries being served (e.g., Youth with disabilities). Crucial for finding niche grants that prioritize marginalized or specialized communities.

**International** — *Funder - Funding Details* — Global Boundary Mapping. Pinpoints geographic funding impact outside of Canada. Vital for cross-border NGOs searching for Canadian root funding.

**Regions** — *Funder - Funding Details* — Local Territorial Fit. Pinpoints where inside Canada the grant money actually lands. Prevents an organization from wasting resources applying to a funder that restricts its giving to a different province or city.

### 4. Charity Table (Charity Record Object)

Records created to describe unique recipient organizations that have received gifts given by funders.

**Charity Name / Business Number (BN)** — *Charity Records* — Peer Benchmarking. Allows fundraisers or an MCP client to audit peer organizations within their space to see who is successfully funding them, providing an immediate list of high-value prospects.

**Charity Focus (Focus / Core Region)** — *Charity Records* — Competitive Market Intelligence. Users can track where the majority of sector funding is flowing and isolate untapped funding gaps.

### 5. Gift Table (Gift Record Object)

Individual records of historical gifts distributed by funders, pairing a funder directly to a specific charity record.

**Reported Amount / Year of Gift** — *Gift Records* — Data-driven Request Calibration. While a program might state it gives "up to $50,000," looking at individual gift records reveals that the majority of actual gifts are much smaller. This protects fundraisers from over-asking based on real historical data.

**Stated Description / Purpose of Gift** — *Gift Records* — Narrative Alignment. Provides textual proof of what project narrative actually wins funding from this group, helping the user mirror successful funding language in their own applications.
