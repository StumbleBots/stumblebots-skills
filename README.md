# StumbleBots Skills

StumbleBots is a tested, instruction-only, approval-gated starter library for one-person businesses. Each skill is a single SKILL.md file with plain instructions an agent can follow. There are no bundled scripts and no code to run.

The library is free.

## The five skills

| Skill | Outcome | Page |
|---|---|---|
| Lead Hunter | No lead goes cold: five real prospects with proof, first message drafted, nothing sent without your yes. | [stumblebots.com/bots/lead-hunter.html](https://stumblebots.com/bots/lead-hunter.html) |
| Sales Follow-Up | No stale lead sits forgotten: every old lead sorted into now, later, or let go, with a short follow up drafted for the ones worth chasing today. | [stumblebots.com/bots/sales-follow-up.html](https://stumblebots.com/bots/sales-follow-up.html) |
| Support Triager | No inbox pileup by lunch: every customer message sorted, answers drafted where they can be, and the risky ones put in front of you first. | [stumblebots.com/bots/support-triager.html](https://stumblebots.com/bots/support-triager.html) |
| Meeting Prepper | Walk in ready, not guessing: a one page brief on who is coming, what they care about, and the questions you are likely to get. | [stumblebots.com/bots/meeting-prepper.html](https://stumblebots.com/bots/meeting-prepper.html) |
| Inbox Drafter | No reply debt at day end: a batch of drafts in your own voice, each one waiting for your yes, and none sent without it. | [stumblebots.com/bots/inbox-drafter.html](https://stumblebots.com/bots/inbox-drafter.html) |

Skills live in this repository under skills/:

- skills/lead-hunter/SKILL.md
- skills/sales-follow-up/SKILL.md
- skills/support-triager/SKILL.md
- skills/meeting-prepper/SKILL.md
- skills/inbox-drafter/SKILL.md

## How to install

Once this repository is published on GitHub, install with the skills CLI:

```
npx skills add <github-owner>/stumblebots-skills
```

Replace <github-owner> with the GitHub account that hosts this repository. The CLI will list the five skills in this repo so you can pick one or install all five.

Or copy a folder by hand:

1. Copy one skill folder, for example skills/lead-hunter/, into your agent's skills directory.
2. Keep the folder name exactly as it is. The folder name must match the name in the SKILL.md frontmatter.
3. Start a new agent session. The agent discovers the skill from its name and description and loads the full instructions only when your request matches.

## Trust note

Instruction-only, no scripts. Nothing in these skills sends, posts, or acts without the user's explicit yes. Each skill interviews first, writes the brief back, and waits for a yes before it searches, sorts, or drafts. Where a fact is missing, the skill writes a [NEED:] flag instead of guessing.

Samples were run on fictional inputs shown in full on the site. Every name, business, and number in the samples is invented. What is real is the format, the limits, and the approval gate. See the provenance statement at the end of each SKILL.md and on each bot page on stumblebots.com.

## License

MIT. See LICENSE.
