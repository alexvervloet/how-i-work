# How I work

Case studies and working notes from a decade of shipping software.

---

## Who this is for

Hiring managers, recruiters, future teammates, or anyone who wants a longer look at how I think than a resume has room for. My resume lists what I did. This repo covers how, and what it taught me.

If you have ten minutes, read the [User Guide](./USER_GUIDE.md). If you have thirty, pick a case study.

---

## About me

I'm an engineer with a degree in organizational communication and leadership, which is a combination that sounds like a hedge and mostly hasn't been. I've spent a decade writing software and ending up, on every team, as the person who gets pulled in when something needs explaining across a gap.

From August 2019 to November 2025 I was at VeVe, a Web3 collectibles platform with two million users, where I was a Lead Engineer across mobile and web. Before that I taught English in Taiwan, where I've been based since 2014.

---

## What I'm looking for

Roles where the engineer sits close to the people the software is for. Depending on the company that's called Forward Deployed Engineer, AI Engineer, fullstack, or a frontend role with real product ownership attached. The AI work is the newest of those and the least visible on a resume, so it has [its own section below](#what-ive-built-since). The title matters less to me than whether I get to talk to users, build the thing, and push back on what we're building rather than only on how fast.

That's the job this repo is evidence for. The case studies are less about code I wrote than about decisions I changed and gaps I closed on behalf of people who weren't in the room.

What I'm not looking for is a queue of tickets with the interesting decisions already made upstairs.

---

## What I built

The case studies below are mostly about decisions, arguments and people. Here's the code side, which they don't cover.

I was hired at VeVe as a junior engineer and left as a lead. In between I worked on every feature the platform shipped, across the web apps and the native app, which as far as I know made me the only engineer who'd touched all of it. I was Lead Engineer for Web v1.

I built the frontend of the VeVe web wallet on my own, which is still in production four years after I last worked on it, and the entire web interface for managing Unity Showrooms. I also worked on the original internal admin application.

In my last year I went after backend work rather than waiting to be handed it. That turned into the backend for our Comic Sets release and a production flaw in Autopay that I found and fixed. I ran a team's daily updates as Scrum Master through 2023, and built the Next.js education covered below.

---

## What I've built since

I left VeVe in November 2025 and spent a couple of months applying for frontend and fullstack roles without much traction. February and March went to a family medical emergency and very little else. When I came back to it in the spring I stopped applying and started asking why. The honest answer was that I was chasing a version of the job that's shrinking, and that I had opinions about AI engineering without any real understanding of it, which is a bad place to argue from.

So I went back to fundamentals rather than back to the job boards. Python properly, from data structures up through FastAPI, databases, auth and messaging, which turned into [a public learning resource](https://github.com/alexvervloet/learning-python-backends) of about 740 commits. Then [the same for JavaScript](https://github.com/alexvervloet/learn-javascript-backend-engineering). Then small experiments to find where the edges were. [StudyRAG](https://github.com/alexvervloet/StudyRAG) in April was my first go at retrieval, and by July I was writing [rag-at-scale](https://github.com/alexvervloet/rag-at-scale) about what breaks between four documents and five million chunks. That gap is roughly the shape of the last six months.

From June the building got serious. Fifteen repositories, around 1,470 commits and 51,000 lines. Five carry their own eval suites, eight run CI, and three are deployed and reachable right now.

The ones I'd start with:

- **[Deskhand](https://github.com/alexvervloet/deskhand)** ([live](https://deskhand.fly.dev)) is a durable agent runtime for support operations, where the agent is allowed to refund money and the machinery around it makes that defensible. [Case study below](#case-studies).
- **[Knowledge Desk](https://github.com/alexvervloet/knowledge-desk)** ([live](https://knowledge-desk.fly.dev)) is a multi-tenant knowledge assistant where a question can only reach documents the asker is allowed to see, enforced three independent times so no single missed filter leaks data.
- **[askrepo-live](https://github.com/alexvervloet/askrepo-live)** ([live](https://askrepo-live.fly.dev)) is a streaming chat UI over a pre-indexed set of my own repositories, behind a FastAPI gateway.
- **[model-swap](https://github.com/alexvervloet/model-swap)** measures what a forced model migration costs on a live app, for when the model you tuned on gets retired and the eval suite is green either way.

There's also an [AI engineering deep-dive series](https://github.com/alexvervloet/ai-engineering-deep-dive), twenty-four build-it-from-scratch courses covering RAG, evals, agents, prompt injection, fine-tuning, observability and the rest. That's the same instinct as the Next.js session at VeVe, which is the one below that leadership didn't ask me for either.

---

## A user guide to me

How I work, what I'm good for, and how to get the best out of me. Worth reading first.

[Read the User Guide →](./USER_GUIDE.md)

---

## Case studies

Six stories from real work, each about a different skill.

### [Building a communication standard across a 100-person org](./case-studies/communication-standard.md)

A document I built with cross-functional input that became the company's communication standard. Still in use after I left.

*Stakeholder synthesis · Change management · Cross-functional facilitation*

### [Building an agent runtime that can be trusted with irreversible actions](./case-studies/deskhand.md)

A support agent allowed to refund money, and the five invariants that make that defensible. Each one has a test that attacks it rather than confirming it, and 25 trajectory evals gate the merges. Includes the bug where a search failure became a permissions failure.

*Agent runtime design · Prompt injection defence · Eval design*

### [Making token swapping safe for people who had never used a wallet](./case-studies/veve-wallet.md)

The frontend of VeVe's web wallet, built for collectors who had never signed an on-chain transaction and couldn't undo one. Most of the work was in the failure states, not the chain. Still running four years later.

*Web3 frontend · Transaction signing UX · Designing for irreversible actions*

### [Reframing Crafting from a new section to an integration](./case-studies/crafting-scope.md)

A feature scoped as a separate section of the app. I made the case for folding it into existing flows instead. Shipped ahead of schedule with fewer bugs than anything else that quarter.

*Scope challenge · Technical-to-business translation · Risk-aware delivery*

### [Closing the Next.js knowledge gap before it cost us months](./case-studies/nextjs-knowledge-gap.md)

A migration that needed framework fluency the team didn't have yet. I built and delivered an org-wide teaching session to close the gap before we ran into it.

*Knowledge gap identification · Cross-functional teaching · Self-directed initiative*

### [Making the case for my own retention](./case-studies/retention-letter.md)

One document combining strategic feedback with self-advocacy. Leadership reversed a decision that had already been made. Includes a [redacted excerpt of the letter](./case-studies/artifacts/retention-letter-excerpt.md).

*Stakeholder communication · Persuasive writing · Strategic framing*

---

## What connects them

Reading these back, a few patterns show up that I hadn't consciously noticed.

**I go after the problems nobody owns.** Four of the six started with nobody asking me for anything. The communication standard, the Next.js teaching and the retention letter were all self-initiated. The work that isn't on a roadmap yet tends to be the most interesting work available, and nobody is competing for it.

**I think in scope.** I'm usually the person asking whether the thing being proposed is the right size. Sometimes that's an argument for less. Sometimes it's an argument for more context, more QA, more teaching. Either way it's about matching the work to the actual goal rather than to whatever got assumed in the first meeting.

**I keep ending up teaching.** The Next.js session at VeVe was unasked for, and so are the twenty-four deep-dive courses I've written since. I don't think this is generosity so much as the way I learn. I don't trust that I understand something until I've had to explain it to someone who'll ask why.

**The work I'm proudest of stopped needing me.** The communication doc is still in use at a company I left in 2025. The wallet has been in production for four years without needing me back. Neither is a thing I could have optimised for directly, but both came from the same habit of spending longer than felt reasonable on the parts nobody would see.

**I write to make decisions clearer.** A communication doc, a teaching deck, a letter to executives. In each case the writing was the thing that turned a vague situation into something a team could act on.

---

## Reach me

alex.vervloet@gmail.com · [LinkedIn](https://linkedin.com/in/alexander-vervloet)

Taichung, Taiwan (UTC+8). Open to remote.
