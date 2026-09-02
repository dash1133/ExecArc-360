# ARC Demo Video — New Scope Mapping

How the Stage 1 / 2 / 3 scope (see `ARC_Roadmap_Scope.md`) lands on the existing
seven-scene video. The seven-step spine is unchanged: **Set up · Collect ·
Prepare · Review · Discuss · Plan · Track**. Only the nuances inside each step
move.

Capability IDs below (1.3, 2.2, …) refer to the tables in `ARC_Roadmap_Scope.md`.

---

## 1. Conflicts — the video currently claims Stage 2 capability as if it ships in Stage 1

These are the ones that matter. Left as-is, the video over-promises against the
September 26 build.

| # | Scene | Video says today | Scope says | Fix |
|---|---|---|---|---|
| C1 | 1 · Set up | "Assistant recommends respondents — with a reason for each" | **1.3** evaluator-*confirmed* lists; agent-generated is **2.2** | Rewrite to evaluator building/confirming the list. Screen must not show agent suggestions. |
| C2 | 1 · Set up | "Evaluator stays in control: approve & launch" + callout "One-click launch" | **1.1** cycles are **admin**-launched | Launch authority moves to admin. Evaluator's control is over the respondent list, not the launch. |
| C3 | 3 · Prepare | Competency grid has a **"Last cycle"** column and a **"Last cycle vs. current"** chip | **1.5** explicitly *without* a historical trend view; cross-cycle is **2.3 / 2.6** | Remove the column and the chip from the Figma screen. Grid = Self · Respondents · Your rating. |
| C4 | 6 · Plan | "Assistant drafts activities from the discussion" + callout "AI-drafted, human-approved" | **2.5** goals-from-transcript is Stage 2; Stage 1 is **1.7** employee-facing goal-setting | Rewrite to employee-led goal-setting, assistant-supported — not transcript-derived. |
| C5 | 5 · Discuss | "Transcript captured, uploaded & processed" (a `.vtt` shown as uploaded) | **2.4** *live* capture is Stage 2; manual upload is not listed in Stage 1 | **Open question — see Q1.** |

## 2. Gaps — Stage 1 scope with no screen time at all

| # | Capability | Where it should live | Note |
|---|---|---|---|
| G1 | **1.2** Manual evidence attachment for self-evaluations | Scene 2 · Collect | Biggest gap. There is no self-evaluation anywhere in the current video, yet Scene 3's grid has a "Self" column that depends on it. Self-eval must happen before the evaluator writes, so it belongs in Collect — as a second screen in that scene, keeping the seven-step spine intact. |
| G2 | **1.5** *Two versions* of the evaluator draft | Scene 3 · Prepare | Video shows a single draft report. Needs a version switch / "v1 · v2" affordance on the screen. |
| G3 | **1.4** *Secure* transcripts | Scene 2 · Collect | The AI-led interview is shown well; the security and handling of the resulting transcript is not. One bullet + a visual cue. |

## 3. Not in the video — later stages

| # | Capability | Recommendation |
|---|---|---|
| N1 | **2.7** Informal feedback prompted by collaboration signals (max 3 touches/person/year, no formal write-up) | Genuinely new surface, not a nuance on an existing step. Belongs in a roadmap scene, not in the seven-step walkthrough. |
| N2 | **Stage 3** Year-end adaptation | Same — roadmap scene. |

## 4. Recommended structure

**Keep the seven scenes Stage-1-true, then add one closing roadmap scene.**

Every screen and every bullet in scenes 1–7 reflects only what exists on
September 26. Stage 2 and Stage 3 capabilities (agent-generated lists, cross-cycle
trends, live capture, goals-from-transcript, informal feedback, year-end) are
collected into a single "What comes next" scene at the end, on the Stage 2 /
Stage 3 timeline.

Why this over badging each capability inline with a "Stage 2" chip: the demo's
credibility rests on the viewer believing everything they just watched is real
in September. Mixing shipped and future capability inside the same screen, even
labelled, blurs that — and small on-screen chips are the first thing lost when
someone screenshots a frame for a deck.

## 5. Figma screens needed

One export per screen, 2x scale, ≥2000px wide, ~3:2 aspect, no Figma chrome, no
baked-in drop shadow.

| File | Scene | Must show / must not show |
|---|---|---|
| `s1_setup.png` | 1 · Set up | Admin-launched cycle; evaluator confirming a respondent list. **No** agent-suggested respondents. |
| `s2a_collect_interview.png` | 2 · Collect | AI-led feedback interview; anonymity + secure transcript cue. |
| `s2b_collect_selfeval.png` | 2 · Collect | **New.** Self-evaluation with manually attached evidence. |
| `s3_prepare.png` | 3 · Prepare | Competency grid: Self · Respondents · Your rating. Draft report with **v1 / v2** version switch. **No** "Last cycle" column, **no** trend chip. |
| `s4_review.png` | 4 · Review | Evaluatee reviewing feedback; goal progress; coach support. |
| `s5_discuss.png` | 5 · Discuss | Pending Q1 — either manual transcript upload, or cycle-on-hold with no transcript. |
| `s6_plan.png` | 6 · Plan | Employee-led goal-setting, assistant-supported. **Not** drafted from a transcript. |
| `s7_track.png` | 7 · Track | Mobile progress tracking. Closest to correct today. |
| `s8_roadmap.png` | 8 · What comes next | Optional — can be drawn natively rather than designed. |

## 6. Open questions

1. **Scene 5 (Discuss) — what happens to the feedback discussion in Stage 1?**
   Stage 1 lists secure transcripts for the *AI-led feedback interviews* (1.4) but
   says nothing about the evaluator–evaluatee discussion; live capture is Stage 2
   (2.4). Is manual transcript upload in the September build, or does the cycle
   simply pause for an off-system conversation with nothing captured?
   *Working assumption until told otherwise: manual upload is in, live capture is
   not.* This decides both the Scene 5 screen and whether Scene 6 has any
   transcript to reference.
2. **"2 versions of evaluator drafts" (1.5)** — two AI-generated alternatives the
   evaluator picks between, or v1/v2 revisions of one draft over time? Changes the
   Scene 3 screen.
3. **Admin-launched cycles (1.1)** — is the admin a new persona on screen in Scene 1,
   or off-screen setup with the evaluator picking up a cycle already launched? The
   scene's persona line ("Evaluator + Assistant Agent") depends on this.
