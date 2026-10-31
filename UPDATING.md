# How to update my profile README

Copy a template, fill the brackets with true facts, paste it into `README.md`, and commit.

Update the README:
- whenever you ship a project;
- whenever you change roles;
- whenever you get a number worth sharing, such as users, tests, uptime, money processed or time saved;
- at least once a month.

## Rules that keep the page attractive to anyone hiring
1. **Most impressive first.** Order projects by impact, not by date. Recruiters read the top third of the page.
2. **Every project answers three questions:** What is it? What did *I* do? What happened as a result (a number, if you have one)?
3. **Numbers you can defend in an interview,** such as "150 students, zero failures" or "about 2,000 tests". Never round up or invent.
4. **Plain, global English.** Short sentences, no slang, and no local abbreviations without explaining them (e.g. write "NYSC (National Youth Service Corps)").
5. **Links that work.** Click every link after each update. Remove dead ones rather than leaving them.
6. **Keep it to 6–8 featured projects.** Move older ones into a one-line "More projects" list.
7. **No private information:** phone numbers, home address, client secrets, or confidential employer metrics.
8. **Match your CV and LinkedIn.** Titles and dates must be identical everywhere.

---

## Template: project card
Paste it under **Featured work** at the right position (most impressive first).

```markdown
### [Project name]: [what it is, in under 10 words] · [link to live site or repo]
**[Your role, if it was a job: Role, Company · Mon YYYY – Mon YYYY]**
`[Tech 1]` `[Tech 2]` `[Tech 3]` `[Tech 4]`
- [What it does and who uses it, in one sentence. Include scale if true: N users / N schools / N transactions.]
- [The hardest technical problem you solved and how: e.g. "Credits each payment exactly once using webhooks, row locks and a reconciliation sweep."]
- [A result or measurement: performance, reliability, tests, money, time saved, users.]
- [Optional: AI / security / testing detail that matches the roles you're targeting.]
```

**Short version** (for a smaller project or one still in development):
```markdown
### [Project name] *(in development, YYYY)*
`[Tech 1]` `[Tech 2]` `[Tech 3]`
[One or two sentences: what it does and the most interesting thing about how it's built.]
```

**"More projects" one-liner** (for older projects moved off the featured list):
```markdown
- **[Project name]**: [what it is] · `[main tech]` · [link]
```

---

## Template: open-source or learning project (for the AI/ML curriculum)
```markdown
### [EvalForge / project name]: [what it is] · [repo link]
`[Python]` `[tech]` `[tech]`
- [What problem it solves and for whom.]
- [What's implemented so far: features, tests, CI.]
- [Proof: stars / users / a benchmark / a write-up link, only if real.]
```

---

## Template: new job or role change
1. In **Experience**, add a row at the top:
```markdown
| [Role] | [Organisation] · [remote / city, hybrid] | [Mon YYYY] – present |
```
2. Change the previous role's end date from "present" to the month you left.
3. Update the title line at the top of the README if your level or focus changed.
4. Add a project card for your main work there, without confidential details.

---

## Template: "What I'm learning now"
Update it when you finish a track or a milestone:
```markdown
## What I'm learning now
[Topic you're deepening, e.g. "LLM evaluation and production AI"]. Recently shipped: [thing + link]. Next: [next milestone]. I share what I build on [X](https://x.com/awosome_dev) and [LinkedIn](https://linkedin.com/in/agbaje-abdulakeem-seun).
```

---

## Template: "Why teams hire me" bullet
Keep 3–5 of these, each with proof:
```markdown
- **[Strength in plain words].** [Proof: what you did + number/result.]
```

---

## Template: tech stack row
Only add tools you've used in a real project:
```markdown
| **[Area]** | [Tool], [Tool], [Tool] |
```

---

## Checklist before each commit
- [ ] Facts and dates match the CV and LinkedIn
- [ ] Every link opens
- [ ] Most impressive project is first
- [ ] No phone number, address or confidential data
- [ ] Read it once on a phone screen (GitHub mobile)
- [ ] Commit message such as: `Profile: add [project]` / `Profile: new role at [company]`
