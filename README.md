# Project Benchwork
This project is a teams extension i am making to help Accenture employs find projects and help project managers promote projects.
## Overview

A Microsoft Teams tool where a consultant uploads their resume and one pager, and an AI agent (using a Python MCP server) finds and ranks matching open projects from the roles spreadsheet. The project is split into five workstreams, one per team member. The assignments below are a starting point and can be swapped to fit each person's strengths.

## Team and focus areas

| Person | Workstream | Owns |
| --- | --- | --- |
| Project lead | Project lead and stakeholders | Timeline, manager demo, IT/security approval, keeping the team unblocked |
| Azir | MCP server and data | `server.py`, the roles CSV loader, hosting the server on a public HTTPS address, the real spreadsheet swap |
| Jazmin | Agent and Teams integration | The Copilot Studio agent, adding the MCP server as a tool, agent instructions, publishing to Teams |
| Jomar | Matching quality and test data | The fake roles spreadsheet, fake resumes and one pagers, the skills list, testing and tuning match results |
| Pedro | User experience, security and rollout | Chat flow and result cards, privacy and access questions, how-to guide, pilot feedback |

## Deliverables and definition of done

### Project lead

- A one paragraph problem statement and success measures (time to find a role, relevance of the top three matches)
- Answers from IT on resume handling and Copilot Studio licensing
- A manager demo scheduled and run
- **Done when:** approval is in hand to move from sample data to the real spreadsheet

### Task 1: MCP server and data

- The server running with the real `search_roles`, `get_role`, and `list_open_roles` tools
- A deployed, reachable URL for the server
- The real spreadsheet's columns mapped through the `COLUMNS` setting
- **Done when:** the agent can query real roles over the internet

### Task 2: Agent and Teams integration

- An agent in Copilot Studio with the MCP server connected
- Instructions telling it to recommend only roles the tools return, explain each match, and list skill gaps
- The agent published to Teams and tested with a few users
- **Done when:** a consultant can chat with it in Teams and get ranked matches

### Task 3: Matching quality and test data

- 20 to 30 fake roles and 3 to 5 fake resumes at different levels, clearly labeled as sample data
- A standard list of skill names, so "Spark" and "PySpark" are handled consistently
- A test sheet that records expected versus actual matches, and a list of fixes
- **Done when:** top matches look right for the test resumes, including a strong, a partial, and a poor match

### Task 4: User experience, security and rollout

- The chat greeting, result card layout, and follow-up prompts
- A privacy checklist: who can see what, how resumes are handled, and what gets stored
- A short how-to guide and a feedback form for the pilot
- **Done when:** a first-time consultant can use it without help

## Timeline

| Weeks | Focus | Who leads |
| --- | --- | --- |
| 1 | Groundwork: IT and security questions, spreadsheet owner and headers, success measures | Project lead, with Pedro on privacy |
| 1 to 2 | Sample data and skills list | Jomar |
| 2 to 3 | Server working locally and tested with sample data | Azir, with Jomar testing |
| 3 | Manager demo (sample data) | Project lead |
| 3 to 4 | Server hosted, agent built and connected | Azir and Jazmin |
| 4 to 5 | Real spreadsheet swap, matching tuned on real roles | Azir and Jomar |
| 5 to 6 | Publish to Teams, polish the chat experience | Jazmin and Pedro |
| 6 on | Small pilot, feedback, results to leadership | Project lead and Pedro |

## Handoffs to watch

- **Jomar to Azir:** the column list and sample data have to be agreed in week 1, since the server depends on them.
- **Azir to Jazmin:** Jazmin can't connect the agent until there's a reachable server URL, so Azir should deploy a basic version early, even if matching is still rough.
- **Jomar to Jazmin:** test results should feed back into the agent instructions.
- **Project lead to everyone:** the IT and security answer can change the plan, so get it before anyone builds too far.

## Working rhythm

- A 15-minute standup twice a week, with each person saying what's done, what's next, and what's blocking them.
- Use the Notion checklist as the shared tracker, with an owner on each task.
- A short demo to each other at the end of each phase before moving on.

## Risks to watch

- IT or security blocks resume uploads to an AI service (ask early).
- Spreadsheet data goes stale and the tool recommends filled roles.
- Required skills are not listed consistently, which weakens matches.
- Privacy of resumes and personal information.
