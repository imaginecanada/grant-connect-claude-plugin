# Grant Connect for Claude

Prospect research for Canadian nonprofits and charities, using
Grant Connect by Imagine Canada.

Ask Claude questions like "Which foundations fund youth mental health in
Winnipeg?" or "Who funds equipment for a food bank in Halifax?". Claude searches
Grant Connect, checks each funder's programs, deadlines and past gifts, leaves
out funders already in your pipeline, and links every funder to its full
Grant Connect profile. French requests work too.

## What's included

- **Skill: prospect research.** Tells Claude how to find, rank and qualify
  funders the way an experienced prospect researcher would.
- **Connector: Grant Connect.** Read-only access to Grant Connect funder
  profiles, gift history and your organization's pipeline.

## Requirements

An active Grant Connect subscription. After installing, open the plugin's
**Connectors** tab and sign in with your Grant Connect account. The connector
only reads data; it never changes anything in Grant Connect.

## Install

- **Claude (web or desktop):** Customize > Plugins > Add > Add marketplace,
  then enter this repository.
- **Claude Code:**

  ```
  claude plugin marketplace add imaginecanada/grant-connect-claude-plugin
  claude plugin install grant-connect@grant-connect
  ```

## Help

Connector documentation: <https://api.grantconnect.ca/mcp/docs>
([français](https://api.grantconnect.ca/mcp/docs/fr)).
Support: grantconnect@imaginecanada.ca

Privacy policy: <https://imaginecanada.ca/en/privacy>
