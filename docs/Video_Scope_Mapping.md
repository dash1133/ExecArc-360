# ARC360 Demo Video — Scope Mapping

How the agreed nine-stage build plan (see `ARC_Roadmap_Scope.md`) lands on the
existing demo video. Supersedes the earlier seven-step reading.

**Headline: the video's spine is wrong.** The current cut is built on seven steps
— Set up · Collect · Prepare · Review · Discuss · Plan · Track — with a seven-dot
progress rail and a title card reading "7 KEY INTERACTION SCENARIOS". The agreed
plan has nine stages. The rail, the title card and the scene count all change.

---

## 1. Seven scenes to nine

| Video today | Becomes | Note |
|---|---|---|
| 1 · Set up | **1 · Launch the Cycle** *and* **3 · 360 Survey Prep** | One scene splits into two. Admin launches and nominates; the evaluator confirms later, as a separate step with a separate actor. |
| — | **2 · Self-Evaluation** | Entirely new scene. |
| 2 · Collect | **4 · Feedback Collection** | Holds. Add secure transcript storage. |
| 3 · Prepare | **5 · Evaluator Preparation** | Holds, with two corrections. |
| 4 · Review | **6 · Evaluatee Preparation** | Holds as designed. |
| 5 · Discuss | **7 · Feedback Discussion** | **Deferred in Stage 1** — loses its entire payload. |
| 6 · Plan | **8 · Development Planning** | Holds, with one correction. |
| 7 · Track | **9 · Track Progress** | Holds as designed. |

Net: two new scenes to build, one scene to hollow out, four to correct, three
that hold.

## 2. Corrections — the video claims capability Stage 1 will not have

| # | Scene | Video says today | Agreed Stage 1 | Fix |
|---|---|---|---|---|
| C1 | 1 · Launch | "Assistant recommends respondents — with a reason for each" | The **administrator** nominates respondents | Nomination is a human admin act, not an agent recommendation. Agent-generated lists are Stage 2. |
| C2 | 1 · Launch | "Evaluator stays in control: approve & launch" + "One-click launch" callout | The **administrator** launches; employee and evaluator are *notified* | Launch authority and the persona line both change. The evaluator's moment moves to scene 3. |
| C3 | 5 · Evaluator Prep | Competency grid carries a **"Last cycle"** column and a **"Last cycle vs. current"** chip | "Two drafts anchored to this cycle only — **no historical trend view**" | Remove the column and the chip. Grid is Self · Respondents · Your rating. |
| C4 | 8 · Development Planning | "Assistant drafts activities from the discussion" | "Goals sourced from **Evaluator Preparation**" | Goals derive from the evaluator's write-up, not the conversation. Rewrite the bullet and the callout. |
| C5 | 7 · Feedback Discussion | "Transcript captured, uploaded & processed" — a `.vtt` shown mid-upload, callout "Nothing gets lost" | **Deferred — no meeting transcript capture** | The scene's entire payload is Stage 2. See §4. |

## 3. Additions — agreed Stage 1 capability with no screen time

| # | Scene | Capability | Note |
|---|---|---|---|
| A1 | **2 · Self-Evaluation** | Employee rates themselves against competencies; evidence attached manually | A whole new scene, and a load-bearing one: scene 5's grid has a *Self* column that this stage produces. |
| A2 | **3 · 360 Survey Prep** | Evaluator reviews nominations and confirms the final respondent list | New scene, though it inherits the respondent-list screen from the old scene 1 — reframed from agent-recommends to evaluator-confirms. |
| A3 | 4 · Feedback Collection | Transcripts stored securely | One bullet and one visual cue on an otherwise strong scene. |
| A4 | 5 · Evaluator Prep | *Two* drafts | The video shows one. See Q1. |

## 4. What to do with scene 7

The Feedback Discussion is a real stage of the cycle but has no Stage 1 system
capability. Three options, in order of preference:

1. **Keep it, honestly.** The conversation happens; ARC holds the cycle while it
   does. Cut the transcript upload, the processing bar and "Nothing gets lost".
   The scene becomes a short beat: the cycle pauses for a human conversation. This
   keeps the nine-stage spine visible and sets up Stage 2 naturally.
2. Keep it as a roadmap beat, visibly marked as Stage 2.
3. Cut it and show eight scenes — not recommended: the rail would no longer match
   the agreed plan the client signed off.

Recommendation: **option 1.**

## 5. Stage 2 and Stage 3

Every Stage 2 capability attaches to a stage in the nine — including informal
feedback, which sits under stage 1, Launch the Cycle. Stage 3 spans the whole
cycle. Recommendation is unchanged from the earlier draft: keep scenes 1–9
Stage-1-true and collect Stage 2 and Stage 3 into a single closing "What comes
next" scene, rather than badging future capability inline where a screenshot
would strip the label.

## 6. Figma exports needed

2x scale, >=2000px wide, ~3:2 aspect, no Figma chrome, no baked-in drop shadow.

| File | Scene | Must show · must not show |
|---|---|---|
| `s1_launch.png` | 1 · Launch the Cycle | Admin launching and nominating; employee + evaluator notified. **No** agent recommendations, **no** evaluator launch button. |
| `s2_selfeval.png` | 2 · Self-Evaluation | **New.** Employee rating against competencies; manually attached evidence. |
| `s3_surveyprep.png` | 3 · 360 Survey Prep | **New.** Evaluator reviewing admin nominations, confirming the final list. |
| `s4_collection.png` | 4 · Feedback Collection | Anonymous AI-led interview; secure transcript storage cue. |
| `s5_evalprep.png` | 5 · Evaluator Preparation | Grid: Self · Respondents · Your rating. **Two** drafts. **No** "Last cycle" column, **no** trend chip. |
| `s6_evalteeprep.png` | 6 · Evaluatee Preparation | Employee-facing review and goal-setting. Holds. |
| `s7_discussion.png` | 7 · Feedback Discussion | Cycle on hold for an off-system conversation. **No** transcript capture of any kind. |
| `s8_devplanning.png` | 8 · Development Planning | Goals sourced from the evaluator's write-up. **Not** from a transcript. |
| `s9_track.png` | 9 · Track Progress | Mobile progress tracking against the plan. Holds. |
| `s10_roadmap.png` | 10 · What comes next | Optional — can be drawn natively. |

## 7. Also changing

- **Title card** — "7 KEY INTERACTION SCENARIOS" becomes 9.
- **Progress rail** — seven dots become nine, in every scene. Labels take the
  agreed stage names.
- **Runtime** — currently 3:19. Two new scenes add roughly 40-50s of narration;
  scene 7 gets shorter. Expect ~3:45 unless the script is tightened.
- **Encode quality** — 342 kb/s at 1080p is too low for real UI screenshots; move
  to a CRF-based encode (~CRF 18-20).

## 8. Open questions

1. **"Two drafts anchored to this cycle only" (stage 5)** — two AI-generated
   alternatives the evaluator picks between, or v1/v2 revisions of a single draft?
   The screen differs substantially: a side-by-side choice versus a version history.
2. **Product name** — the build plan says **ARC360** and this repo is
   `ExecArc-360`, but the video's wordmark and every on-screen reference say
   **ARC**. Which is correct for the client-facing cut?
