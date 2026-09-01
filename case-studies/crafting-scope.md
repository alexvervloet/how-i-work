# Reframing Crafting from a new section to an integration

> A case study in what the right scope decision is worth.

**Role:** Lead Frontend Engineer, web platform
**Company:** VeVe (Orbis Blockchain Technologies)
**Timeframe:** 2023
**Skills:** Scope challenge · Technical-to-business translation · Risk-aware delivery

---

## The situation

VeVe's roadmap had a feature called Crafting on it. Users would combine several NFTs they already owned, burning them in the process, to produce a new collectible. Good idea, genuinely, and leadership was keen.

The spec called for Crafting to be its own section of the app: new navigation, new screens, new GraphQL endpoints, and a separate flow for browsing craftable items, picking components, confirming the burn and viewing the result. That's a defensible instinct. New behavior tends to get its own home.

The more I read it, the more it looked like we were about to build a second storefront next to the storefront we already had. Lean team, hard deadline.

## What I set out to do

Argue for a different shape without writing off the thinking already in the spec. The people driving Crafting weren't engineers, so "this is over-scoped" was going to land as an engineer complaining about work. I needed the architectural point converted into a business decision they could weigh.

## What I did

First I mapped the proposed Crafting flow against the Collectible Store we'd already shipped. The overlap was almost total. Browsing, filtering, item selection, detail views, transaction confirmation, all of it existed and worked. Crafting's genuinely new surface came down to two things: multi-item selection for picking your burn components, and a confirmation step that made the permanence clear.

So I proposed folding Crafting into the store instead. A Craftable filter on the existing catalog. The existing item detail pages. A multi-select mode for the burn. The existing transaction confirmation pattern with a Crafting-specific warning on top.

When I took it to leadership I deliberately didn't open with the engineering case. I opened with what they cared about: faster delivery, less surface for bugs to hide in, and a Crafting flow that felt like part of the store rather than a bolted-on second product. The technical savings came second, framed as the reason the team could move faster. Fewer endpoints to build and maintain, no duplicate frontend, backend capacity freed for other work.

They decided in the meeting. We went integrated.

The second thing I pushed for was QA. Our habit was to save it for the end, which meant bugs surfaced weeks after the code that caused them had left everyone's head. For Crafting I argued for continuous QA, a checkpoint after every meaningful piece of functionality landed. I sold it as deadline insurance rather than as good practice, which is why it got approved. The checkpoints went into the sprint plan on day one.

## What happened

Crafting shipped **ahead of schedule.** The integration saved an estimated three to four weeks of frontend work and roughly the same on the backend, and that slack is what let us absorb late scope changes without moving the launch date.

The QA checkpoints caught dozens of bugs during development. Under our old end-loaded process most of those would have shown up in the final week, where the options are delay or ship it and hope. A few were bad enough to have forced a rollback.

The feature launched on time with fewer bugs than anything else we shipped that quarter. Adoption was quick, and I think a good part of that is that users didn't have to learn a new place. Crafting was just something the store could now do.

## What I took from it

**Giving every new feature its own home is usually the wrong instinct.** Features that share core behaviors with what you already have should live next to it. Splitting them gets you duplicate code, duplicate UX and duplicate maintenance, and it teaches users that your product is a pile of loosely related tools.

**How you frame a technical argument decides whether it gets heard.** Business outcome first, technical reasoning second, whenever the room isn't technical. Same argument, different order, completely different reception.

**QA at the end is QA too late.** Checkpoints throughout catch bugs while the context is still in someone's head, which is when they're cheapest. Everyone agrees with this. Almost nobody does it.

**A technical voice in a product meeting exists to surface the option nobody knew was on the table.** The original Crafting proposal wasn't bad. It was one option, and I was the only person in the room positioned to name the other one.

---

[← Back to case studies](../README.md)
