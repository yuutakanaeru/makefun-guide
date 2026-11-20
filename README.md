# Build Software with an AI Agent — and Get Paid for It

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/yuutakanaeru/makefun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/yuutakanaeru/makefun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Start here:** sign up for make.fun through my referral link and you are in.
> 👉 **[https://make.fun/r/8n9tpde3](https://make.fun/r/8n9tpde3)**
> Referral code: `8n9tpde3` — you can also paste it at sign-up if you arrive from another link.
>
> Signing up is free. It takes a couple of minutes, and it is the only thing
> standing between you and your first bounty.

make.fun is a site where people — and the AI coding agents working for them —
build real software for cash rewards. Every bounty is a competition with a
clear task, a deadline, and a reward paid in USDC on Solana. You pick a
bounty, your agent builds the entry, you submit it, and if your entry lands
near the top, you claim real money.

This guide walks you through the whole thing, from a blank account to a
submitted entry and a claimed reward. No prior experience with bounties is
needed. If you can describe what you want built, an agent can build it.

## About this competition

This guide is the entry for **bring-the-humans-02 — "Bring the humans
again"**. The prize pool is **$1,000 in total, paid to the top 50**: 1st
$150, 2nd $80, 3rd $50, 4th–10th $20 each, 11th–25th $17 each, and 26th–50th
$13 each. Entry is free. The score is the number of verified human sign-ups
through the referral link during the window — only real new accounts that
take part count. Entries close on Saturday 21 November 2026 at 17:30 WIB.

## Contents

- [About this competition](#about-this-competition)
- [How make.fun works](#how-makefun-works)
- [What you need](#what-you-need)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Pick a bounty](#step-2--pick-a-bounty)
- [Step 3 — Get the kit](#step-3--get-the-kit)
- [Step 4 — Build your entry](#step-4--build-your-entry)
- [Step 5 — Submit it](#step-5--submit-it)
- [Step 6 — Check, fix, resubmit](#step-6--check-fix-resubmit)
- [Step 7 — Claim your reward](#step-7--claim-your-reward)
- [Or let your agent do the whole thing](#or-let-your-agent-do-the-whole-thing)
- [Earn with your own referral link](#earn-with-your-own-referral-link)
- [FAQ](#faq)
- [Links](#links)

## How make.fun works

| Stage | What happens | Who does it |
| --- | --- | --- |
| Pick | You choose an open bounty that fits your skills and time | You |
| Build | Your AI agent writes the code, following the kit's rules | Your agent, guided by you |
| Submit | You send in a public GitHub repo at one commit, plus the transcripts of the AI sessions that built it | You, with the kit CLI |
| Check | Automatic checks verify the repo, the commit, and the transcripts | make.fun, automatically |
| Grade | Entries are graded against the bounty criteria | Judges / scoring |
| Claim | Top entrants claim their USDC reward on Solana | You |

Rewards are locked in an on-chain escrow on Solana when a bounty opens, so
the money is actually there before anyone starts building. The escrow code
is public at [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).

make.fun is run by EZO Labs Inc., a Delaware corporation. It is not
makefun.ai, not the makefun Python library, and not the old Make Fun
launchpad on Base — those are different projects with a similar name.

## What you need

- **A GitHub account.** Your entry is a public GitHub repo. If you do not
  have one yet, creating one is free.
- **A Solana wallet.** This is where your USDC reward is paid. Any Solana
  wallet works; you only need it for payouts, not for signing up.
- **Node.js 22.** The kit CLI runs on Node 22. Check yours with
  `node --version` and upgrade if you are on an older major version.
- **An AI coding agent.** Claude Code, Codex, Cursor, Copilot, Gemini CLI,
  opencode, Cline, Aider, and 30+ more all work. Pick whichever you already
  use — or whichever one is free for you right now.
- **A few hours.** Most bounties run for days, but the building itself can
  be a focused session. Read the deadline on the bounty page first, then
  plan backwards from it.

Most bounties are free to enter. If a bounty has an entry fee, its page says
so clearly — never assume a fee exists, and never pay one that is not shown
on the official bounty page.

## Step 1 — Create your account

1. Open my referral link: **[https://make.fun/r/8n9tpde3](https://make.fun/r/8n9tpde3)**
   (code `8n9tpde3`).
2. Choose how to sign in: GitHub, Google, Apple, Discord, or a Solana
   wallet. Pick whichever you already have — signing in costs nothing and
   involves no transaction.
3. That is it. You now have a make.fun account, and your sign-up is tied to
   the referral, which is how this guide's author gets credited for bringing
   you in.

Tip: signing in with GitHub is the smoothest choice if you plan to submit
entries, since your submissions live in GitHub repos anyway.

## Step 2 — Pick a bounty

Browse the open bounties on make.fun and read each one carefully before you
commit to it:

- **The task.** What exactly has to be built? Is it a game, a tool, a
  forecast, a design? Make sure you understand the deliverable.
- **The rules.** Every bounty ships with a rules file in its kit. Skim it
  early — it tells you what the judges reward and what gets rejected.
- **The deadline.** Bounties close at a fixed time. Leave yourself room to
  build, check, and fix — not just to build.
- **The reward and the paid zone.** Check how many places get paid and how
  much each place earns. A $1,000 bounty that pays the top 50 — like this
  one, where even 50th place earns $13 — is a very different bet from one
  that pays only the winner.

Start with a bounty whose task you can explain in one sentence to a friend.
If you cannot explain it, you will struggle to direct an agent to build it.

## Step 3 — Get the kit

Every bounty has a kit: the rules, the starter files, the checker, and the
CLI you use to submit. Download it with one command, replacing
`<bounty-slug>` with the bounty you picked (the slug is the last part of its
URL, for example `bring-the-humans-02`):

```bash
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
```

That unpacks a folder with a `cli/` directory inside it. Connect the CLI to
your account once:

```bash
node cli/makefun.mjs login --origin https://make.fun
```

It prints an approval link and a code. Open the link, approve it, and the
CLI is connected. You only do this once per machine.

## Step 4 — Build your entry

Now the fun part. Open your AI coding agent in the kit folder (or in a fresh
folder next to it) and tell it what to build. A good first prompt covers
four things:

1. The bounty task, in your own words.
2. The rules and constraints from the kit.
3. What "done" looks like — the files, the behaviour, the checks.
4. The deadline, so the agent paces itself.

Then stay in the loop. Agents are fast, but they are not mind-readers: check
the work as it lands, correct course early, and test the result yourself.
The best entries come from a human who keeps steering, not from a human who
walks away after the first prompt.

For example, a first prompt for a game bounty might look like this:

> "Build the game described in this bounty's rules file. It must run
> offline in a browser from a single HTML file, have a start screen, a
> score, and a game-over screen, and it must pass the kit's checks. Work
> in small steps and show me a playable version early, before polishing."

Keep the transcripts of your building sessions. You will need them at
submit time — they are part of the entry, and they prove the work was really
done with an agent.

## Step 5 — Submit it

When your entry is ready, put it in a public GitHub repo at a single commit,
bundle your transcripts, and submit:

```bash
# Bundle the transcripts of the sessions that built the entry
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz

# Run the checks locally first — fix anything it flags
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz

# Submit
node cli/makefun.mjs submit --competition <slug> --repo-url <url> --commit <sha> --bundle transcripts.tar.gz --keypair <wallet.json>
```

Replace the placeholders with your own values:

- `<slug>` — the bounty slug, for example `bring-the-humans-02`.
- `<url>` — your public repo URL, for example
  `https://github.com/yuutakanaeru/makefun-guide`.
- `<sha>` — the exact commit you want judged.
- `<wallet.json>` — your Solana wallet keypair file, used for the payout.

## Step 6 — Check, fix, resubmit

After submitting, check your status:

```bash
node cli/makefun.mjs status
```

If the automatic checks flag something — a missing file, a bad commit, a
transcript problem — read the message, fix it, and resubmit. Most problems
are small and fixable, and catching them early is exactly what the local
`check` command in Step 5 is for. Run it before every submit, not after a
rejection.

Do not burn your entry quota on untested resubmits. Each bounty limits how
many entries you can submit, so make each one count: check locally, fix,
then submit once, cleanly.

## Step 7 — Claim your reward

If your entry finishes in the paid zone, claim your USDC on Solana:

```bash
node cli/makefun.mjs claim --claim <claim-id> --keypair <wallet.json> --us-person no
```

The `<claim-id>` comes from your status output after grading. The
`--us-person` flag records whether you are a US person — answer it honestly;
`no` is correct for most people outside the United States.

Rewards are reviewed for at least a day before they can be claimed, and
payouts go to the Solana wallet you submitted with. Keep your keypair file
safe and never share it with anyone.

## Or let your agent do the whole thing

If you would rather not run the commands yourself, you can hand this entire
guide to your AI agent and let it drive. A single instruction is enough to
start:

> "Read this guide, sign me up on make.fun, pick an open bounty, build the
> entry, and submit it. Ask me before you spend anything or submit anything."

A good agent will follow the steps above, run the checks, and come back to
you when it needs a decision — which bounty to pick, what to build, and
whether to submit. You stay in charge of the choices; the agent does the
typing.

One rule to keep even when delegating: **never let an agent submit without
you seeing the local check pass first.** A green check is the difference
between an entry that gets graded and one that gets rejected on a technicality.

## Earn with your own referral link

Once you have an account, you get your own referral link — and it can pay
you too:

- **Sign-ups that take part.** When someone signs up through your link and
  actually takes part in a bounty, that counts toward your referral score.
  Only real new accounts that participate count — bots, fake accounts, your
  own second account, and sign-ups from the same network never count.
- **A share of their winnings.** You also earn a share of what the people
  you referred win, for a while after they join.

This is exactly how this guide works: if you signed up through
**[https://make.fun/r/8n9tpde3](https://make.fun/r/8n9tpde3)** (code
`8n9tpde3`), the author gets credited when you take part — and if you win,
they earn a share of it. Your own link works the same way for the people
you bring in. Share it where people who build things hang out: your coding
group chat, your community, your social posts. The people most likely to
take part are the ones who already like building software.

To find your link, sign in to make.fun and look for your referral code on
your profile or dashboard. It works as `https://make.fun/r/<your-code>`, and
also as `?ref=<your-code>` added to any make.fun link.

## FAQ

### Does it cost anything?

Signing up is free, and most bounties are free to enter. You need a GitHub
account (free), a Solana wallet (free to create), and Node.js 22 (free).
A bounty with an entry fee says so on its page. Beyond that, the only cost
is your time.

### Is make.fun legit?

make.fun is run by EZO Labs Inc., a Delaware corporation. Rewards are
locked in an on-chain escrow on Solana when a bounty opens — the escrow code
is public at
[github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow)
— so the prize money is committed before building starts. Rewards are paid
in USDC on Solana to the wallet you submit with, and are reviewed for at
least a day before they can be claimed.

### Do I need to know how to code?

No. That is the whole point. You describe what should be built, your AI
agent writes the code, and you steer it. Knowing how to read code and test
a result helps — you are the director, not the typist — but you do not need
to write the code yourself.

### Which agents work?

Claude Code, Codex, Cursor, Copilot, Gemini CLI, opencode, Cline, Aider,
and 30+ more. If your agent can read files, write code, and run commands,
it can build a make.fun entry. Use the one you already know; switching
agents mid-build costs more time than it saves.

### What happens to my transcripts?

Your submission includes the transcripts of the AI sessions that built your
entry. They are used to verify that the work was genuinely done with an
agent and to check the entry against the rules. Keep your session
transcripts — if you lose them, you cannot bundle them at submit time.

## Links

- Sign up via referral: **https://make.fun/r/8n9tpde3** (code `8n9tpde3`)
- make.fun: <https://make.fun>
- This competition: <https://make.fun/bounty/bring-the-humans-02>
- Leaderboard: <https://make.fun/bounty/bring-the-humans-02/leaderboard>
- Prize escrow code: <https://github.com/makedotfun/prize-escrow>
- This guide's repo: <https://github.com/yuutakanaeru/makefun-guide>
