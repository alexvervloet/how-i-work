# Making token swapping safe for people who had never used a wallet

> A case study in building for users who can't undo their mistakes.

**Role:** Frontend Engineer, web wallet
**Company:** VeVe (Orbis Blockchain Technologies)
**Timeframe:** 2021-2022
**Skills:** Web3 frontend · Transaction signing UX · Designing for irreversible actions

---

## The situation

VeVe's main app was built around NFT collectibles. Buy them, own them, show them off. It hid nearly all of the blockchain underneath on purpose, because the people using it were collectors who cared about comics and figures rather than about chains.

OMI, the platform's token, didn't fit inside that app. Token holders needed balances, layer swapping, and transaction signing, and signing is the one thing you can't abstract away. It's the moment the user has to understand what they're approving, because once it's on chain nobody can take it back.

So it needed to be its own application, separate from the collectibles product. I built the frontend of it.

## What I set out to do

A wallet our actual users could operate, which is a different brief from a wallet that works.

Our audience wasn't crypto-native. Most of them arrived for the collectibles and ended up holding OMI as a consequence, which meant a large share of the people about to sign an on-chain transaction had never used a wallet and had no model for what signing even was. That inverts the normal wallet design problem. Most wallets are built by crypto people for crypto people and assume you know what a pending state, a rejected transaction, or a chain mismatch is. I couldn't assume any of it, and the price of a user misreading a screen was their own money, permanently.

## What I did

React on the frontend, ethers.js and web3.js against contracts I didn't write. The surface was a dashboard, on-chain asset display, balance checks, layer swapping for OMI, and transaction signing.

The part that took the most care was the handshakes. Every interaction between the page and a user's wallet is an async negotiation with more failure modes than success ones. The user rejects the request. They're on the wrong network. The request stalls with no response. They switch tabs and come back to a dead prompt. They hit the button again because nothing appeared to happen.

For a crypto-native audience you can leave some of those states ambiguous and the user will work out what happened. Mine couldn't. Every one of those branches needed a state in the interface that told a non-technical person what was true right now and what to do about it, and it needed to be impossible to submit the same transaction twice by mashing a button that looked unresponsive. Most of the engineering effort in this project went into that state handling rather than into anything on chain.

## What happened

It shipped, and it was the wallet VeVe token holders used for OMI through 2021 and 2022. I kept extending it across that period.

The clearest signal was what didn't happen. A wallet aimed at people who've never used one is a support-load problem waiting to happen, and the failure mode I was most worried about, users stuck mid-transaction with no idea what state they were in, never turned into the flood it could have been.

## What I took from it

**Irreversibility changes the entire design brief.** In most software a confusing screen costs the user a minute. Here it cost them money that no one could refund. That single property should drive every decision about confirmation steps, wording, and how loudly the interface states what's about to happen. It's the reason this was harder than the feature list makes it look.

**In web3 frontend work the chain is rarely the hard part.** Reading a balance is straightforward. Modelling every way a wallet handshake can stall, fail, or get interrupted, and giving each of those a state the user can act on, is where the real work is. I'd say that generalises past crypto to any interface sitting in front of a slow, failure-prone system someone else operates.

**This is the same job as the rest of this repo, written in code.** Every other case study here is about translating between people who have the context and people who don't. This one is the same problem with the audience on the other side of a screen instead of across a meeting room.

---

[← Back to case studies](../README.md)
