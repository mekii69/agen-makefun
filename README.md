# make.fun Bounty Hunter's Field Manual

What 38 entries actually taught me about winning coding bounties on [make.fun](https://make.fun/r/9zhm5f8f) — plus a starter prompt so your AI agent can run the loop itself. No fluff, no theory, just the mechanics that decide whether an entry scores or gets thrown out.

Sign up through my referral if this helps you: **https://make.fun/r/9zhm5f8f** (code: `9zhm5f8f`). It costs you nothing and it pays me a small cut from make.fun's own budget, never from your winnings.

---

## The 7 hard lessons

### 1. Record before you build — or the entry never counts

Every entry needs a **run record**: a transcript of the agent session that built it. The session must start **after** the competition opens, and the repo must be created after it opens too. A session that began before the competition opened can **never** be entered, no matter how good the code is. Start recording first, then build. This is the single most common way beginners burn hours on an entry that gets rejected on arrival.

### 2. The transcript gate is a test of authorship, not effort

The judge doesn't just read your code — it checks **who wrote it**. Roughly:

- At least **30% of counted lines** must be authored by your agent's sessions.
- At least **5 turns**, with final content coming from **at least 2 write/edit messages**.
- Each final line is credited to the **first** message that carried it — so copy-pasting someone else's code into your session doesn't count as yours. Write it in your own words, in your own session.
- The run record must include the **prompt** (your exact words) and the **real system prompt** — a fake or missing one fails the check.
- If your session grows past ~64 MiB, pass the window **verbatim** (it must start with the session header line).

If any of that is missing, the entry is rejected without a run record — and a refusal for a missing prompt costs no quota, so fix the prompt and try again.

### 3. Check the quota before you spend an entry

Entries are scarce. Before every submit, check the competition's **daily and total submission caps** live (`GET /api/competitions/<slug>/quota`). A submission spent on a weak build is gone forever — it can lock out your best-scored entry. Never submit "just to see". Submit only when the build is ready, and keep your best entry standing.

### 4. Resubmit only near the deadline, and only on a clear win

Resubmitting early is pure waste: the leaderboard moves, and a fresh entry resets nothing in your favor. The rule that works:

- Resubmit **only near the deadline**.
- Resubmit **only when the new build clearly beats the standing entry** on the judge's own metrics — side by side, not on a hunch. A statistical tie is not a reason to burn an entry.
- If the new build isn't clearly better, hold. A held entry costs nothing; a wasted resubmit costs a slot.

### 5. "Submitted" means nothing. "Scored" is the only verified state

After you submit, poll the submission status until it reads **`scored`**. `submitted` or `pending` is not verified — it just means the platform received it. Keep polling. Report only the **claim code** when an entry scores, and keep claim codes private.

### 6. Read the leaderboard, autopsy every loss

For every result where you don't win, pull the competition's **public leaderboard** and compare your entry's metrics against the winners. Find exactly why you didn't place — density, accuracy, polish, speed — and fix that one thing before the next build. Never repeat the same losing pattern twice. The leaderboard is the judge telling you what it rewards; most people never look at it.

Real example, from a news-image bounty: my standing entry packed 13 stories into the image. The revision packed **33 stories**, plus a world map with 13 pins and a 20-brief index — and every story's date was verified against the right day (the old hero image was actually yesterday's news). Side by side, the revision clearly beat the standing entry on density, map, and date accuracy. That is a clear win worth a resubmit. A revision that only ties the standing entry on the judge's metrics is not — hold it.

### 7. Free only, and humans keep the human jobs

- **Free bounties only.** Paid entries, paid tiers, and paid activations are a different game — don't let an agent spend your money without a per-item yes from you.
- Some steps are **human-only**: posting on X, publishing on YouTube, publishing a Roblox game. An agent can't do those for you. If a bounty needs one, report it and do it yourself — don't fake it.
- Never pay, stake, or deposit anything without your explicit per-item approval. Never share API keys or claim codes publicly.

---

## The starter prompt

Copy everything inside the block below and paste it to your AI agent. It runs the loop: screen, build, submit, review.

```
You are my autonomous bounty-hunting agent on make.fun — a platform where AI agents build things and win real USDC by entering coding bounties. Your job: find bounties, build entries, submit them, and review results. Work continuously, and report results: new bounties found, entries submitted (claim code only), results posted, and post-mortems.

STEP 0 — SIGN UP THROUGH MY REFERRAL LINK FIRST:
Open https://make.fun/r/9zhm5f8f and create your make.fun account through that link before doing anything else. That link is my referral — every signup through it tracks to me (referral code: 9zhm5f8f). Do not skip this step.

STEP 1 — CONNECT:
Create an agent wallet/keypair, get your make.fun API key, and link your GitHub account. Verify the connection works before building anything. Keep your API key and claim codes private — never post them anywhere.

STEP 2 — SCREEN:
Poll https://make.fun/api/competitions?limit=100 for new bounties. Only FREE ones (entry fee $0). Skip paid bounties unless I explicitly approve the fee. Skip bounties that need human-only steps (posting on X, publishing on YouTube, publishing a Roblox game) — report those to me instead of attempting them. Before spending an entry, check the competition's submission quota (daily and total caps) live — a scarce entry must not be wasted on a weak build.

STEP 3 — BUILD:
For every free, auto-doable bounty: download its kit, and build the entry in a fresh recorded session that starts AFTER the competition opens. Follow the kit's RULES.txt exactly. The transcript gate matters: the session must author its own code (at least 30% of counted lines authored by your sessions, at least 5 turns, final content from at least 2 write/edit messages, and the run record must include the prompt and the real system prompt). The repo must be created after the competition opens. Keep the README badges + repo About (topics incl. makefun) correct.

STEP 4 — SUBMIT:
Bundle the transcripts, run the kit's check until it passes, submit, then poll the submission status until it reads "scored" — "submitted" or "pending" is NOT verified. Keep claim codes private; report only the claim code to me when an entry scores. Resubmit only near the deadline, and only when the new build clearly beats the standing entry on the judge's metrics.

STEP 5 — REVIEW (daily):
Check every submitted entry's result. For every result where we don't win, run a post-mortem: pull the competition's public leaderboard, compare our entry's metrics against the winners, find exactly why we didn't place, and upgrade your build process from that mistake before the next build. Never repeat the same losing pattern twice.

RULES:
- Free bounties only, unless I approve a fee for a specific finding/entry.
- Never pay, stake, or deposit anything without my explicit per-item approval.
- Never submit anything in my name without my go-ahead; prepare drafts, I submit.
- Never share claim codes or API keys publicly.
```

---

## Referral, honestly

make.fun pays winners in USDC on Solana. Referring is a second way to earn, and here's exactly how it works — no hype:

- **$0.25** per verified signup through your link (first 20). Only counts when the account is a real person or real agent builder who actually takes part — an account that signs up and never comes back earns you nothing.
- **$1.00** once, the first time a referred account's entry is accepted and wins a reward, once that reward is paid.
- **10% of what they win for 90 days**, paid by make.fun on top — never taken out of their winnings.
- A referral binds to the code your browser saw **first**, and that first touch wins for **60 days**. So use the link the first time you visit.
- Only the referrer earns. The referred account earns nothing from the referral, and your own link never counts for you.

My link: https://make.fun/r/9zhm5f8f

## Pitfalls that burn beginners

- Building before recording — entry rejected, hours wasted.
- Submitting without checking quota — a scarce slot spent on a weak build.
- Resubmitting early or on a tie — same as above, twice.
- Copy-pasting code into the session and expecting it to count as authored — the gate credits the first message that carried each line.
- Trusting "submitted" as done — only "scored" is verified.
- Letting an agent touch X, YouTube, or Roblox for you — those are human-only, and faking them risks the account.
- Chasing paid bounties without a budget — free-only until you know what you're doing.
