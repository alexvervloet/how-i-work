# Closing the Next.js knowledge gap before it cost us months

> A case study in teaching a team something before they need it.

**Role:** Lead Frontend Engineer, web platform
**Company:** VeVe (Orbis Blockchain Technologies)
**Timeframe:** 2024
**Skills:** Knowledge gap identification · Cross-functional teaching · Onboarding design

---

## The situation

In 2024 leadership decided to rebuild our React web app as a 2.0 in Next.js. The reasoning held up: we wanted server-side rendering, we badly needed SEO that the existing client-rendered app was never going to give us, and Next.js was the obvious route.

The problem nobody was raising was that the App Router had only been stable for about a year, and it wasn't a new API so much as a different way of thinking about a React app. Server components, server actions, the caching model, the client/server boundary. None of it mapped onto the mental model our engineers had built over years of client-side React, and some of it actively contradicted it.

The team was days from starting. Leadership assumed everyone was ready. In one-on-one conversations, most engineers admitted they weren't. That gap was going to cost us weeks of false starts and rework, and I thought there was a real chance of months.

## What I set out to do

Close it before we hit it. The target was the whole engineering team fluent enough to work confidently from day one, not just the frontend and fullstack engineers writing most of the code. I also wanted leadership and PMs in the room, because several of the new architectural concepts had direct product consequences they'd need to understand to scope anything sensibly.

Nobody asked me to do this. It was going to slow us down if I didn't.

## What I did

I built a full teaching presentation. The technical core covered the features, the syntax, and specifically the gotchas I knew the team would otherwise find the hard way. I picked for what trips people up in practice rather than trying to cover the documentation.

Then I did something less obvious. I opened with a section on the history of web architecture: PHP-era server rendering, the shift to client-side single-page apps and the reasons for it, and why the pendulum was swinging back toward the server. I wanted the team to know why Next.js exists and what it's a reaction to, not only how to use it.

That history section turned out to be the part that mattered. Engineers who understood the why picked up the how much faster. PMs and leadership could follow it, because the story was anchored in something concrete instead of framework vocabulary.

I also leaned on humor, on purpose. Dense technical material lands better when people are enjoying themselves, and several of the new Next.js paradigms have genuinely funny edge cases once you know where to look. I pitched each idea so a PM with no React experience could follow it, then layered the depth on top for the engineers.

I presented to the whole engineering org. Backend, infrastructure, leadership, and any PM who wanted to come. Everyone left with the same baseline.

## What happened

The team was building productively within days rather than weeks, and the initial 2.0 app went from kickoff to a working version in **weeks rather than the months** a migration of that scope usually takes.

The shared baseline paid off in ways I hadn't planned for. PMs used Next.js terminology correctly in tickets from the start. Backend engineers asking about caching knew which questions were the right ones. Code review and architecture discussions started higher up, because we weren't spending the first ten minutes establishing common ground. People were still referring back to the history framing months later.

The deck became a reference doc, and we used it to onboard engineers who joined the project after the rollout.

## What I took from it

**Closing a gap nobody has labeled a blocker is underrated leadership.** Most teams have one at any given time. A technology nobody fully understands, a corner of the codebase everyone routes around, a process everyone agrees is broken and nobody owns. Fixing one of those beats shipping a visible feature, and far fewer people are competing for the work.

**Teach the why and the how comes cheap.** Give someone the historical and conceptual context for a tool and they can reason about situations you never showed them. Give them only the syntax and they're stuck the moment reality diverges from the example.

**Include the people who don't technically need it.** Putting PMs and leadership in a technical session is unconventional and it pays for itself in every conversation afterward. Better decisions, better questions, better tickets.

**If you can't make it interesting, you don't understand it well enough yet.** Anyone can recite the docs. Finding the right metaphor or the right joke is the part that requires actually knowing the material.

---

[← Back to case studies](../README.md)
