# Lantero

*Warm light on old paper, pointed at any when, any where.*

Lantero is a private, on-device planner for **parent-led family learning**. It helps a parent turn a child's obsessions — pirates, dinosaurs, Lego, space — into short, playful missions that quietly build real skills. The parent is the guide. The child gets an adventure. No dashboards are ever pointed at your kid.

The name means *the one who carries the lantern* — the lamplighter. That's the whole idea: light to see by, not a camera watching.

---

## The problem

Summer comes, school pauses, and parents face the same uneasy choice. Worksheets and drill apps feel like a second school nobody wants — and they tend to teach kids that learning is a chore to be endured. The slick "AI tutor" products go the other way: they put a screen between you and your child, meter learning by the minute, watch the child through the camera to track attention, and sell speed — *"2.6× faster."* Some of the families who've used those report the metrics culture made their kids anxious.

Meanwhile the thing that actually works is sitting in your living room. Children learn faster and more deeply when six conditions are present: autonomy, a real sense of mastery, immediate feedback, meaningful challenge, emotional safety, and a growing identity as a *capable learner*. The best of the high-tech learning systems didn't invent a magic tutor — they got good at **orchestrating those six conditions**. That orchestration doesn't require surveillance, quotas, or a screen babysitter. It needs a motivated guide, a good plan, and a little structure.

Most parents have the motivation. What they lack is the plan and the structure — without it turning into a full-time job.

## What Lantero does

Lantero's unit of work is the **mission**: a 10–30 minute, interest-wrapped, single-skill quest, mostly done with physical materials, run by you.

> *Captain Willie's crew found a bottle. The map inside is written in the old pirate code — and the tide turns at sunset.*

That hook is a phonics lesson. The child experiences a story and a clear goal (decode the map). You know the hidden skill target. Every mission comes with a short parent script — an opening line, a couple of mid-mission prompts, an effort-based praise line, and a graceful fallback for when it isn't landing ("the tide changed — we'll catch it tomorrow," no debt, no guilt).

The app sits with the *parent*, not the child. It helps you:

- **Tune to your child.** A quick, re-runnable onboarding captures who your explorer is — their interests, how they like to learn, where they are now, and which life skills matter most. Re-tune any step as they grow.
- **Build a mission in seconds.** Pick a skill (or let it choose what's due for review), an interest wrapper, how much time and energy you've got, and screen or no-screen. Out comes a ready-to-run mission card you can print. There's also a one-click "copy AI prompt" that packages your child's profile so you can generate richer missions in Claude or ChatGPT — without any of your child's data leaving your machine unreviewed.
- **Keep a gentle ledger.** Log what you actually did across day, week, month, and quarter. A circular heat map shows where the light is falling — which subjects are over-indexed and which need attention — so balance is a glance, not a spreadsheet.
- **Watch the one metric that matters.** Each week Lantero asks the north-star question: *is your child approaching learning willingly and feeling capable?* That outranks everything else. If academics climb while willingness drops, the system is failing on its own terms.
- **Stay compliant, if you homeschool.** Instructional days, minutes, and subject coverage are logged against a superset homeschool standard, with an exportable quarterly report.

What you will **not** find: points, streaks, leaderboards, timers used as pressure, child-visible scores, "ahead of grade level" framing, or anything that works by making your child not want to stop. Those are ruled out by design, not left out by accident.

## Who it's for

Parents of roughly 4–9-year-olds who:

- chose alternative, progressive, or gentle schooling (Montessori, Waldorf, play-based) or homeschool — and want to *protect* those norms, not override them;
- are curious about AI but wary of surveillance and screen-first products;
- dread the summer-slide / worksheet trap and want learning that feels like shared time, not a second job.

They aren't shopping for acceleration. They want a confident, curious kid and good hours together. Lantero is built for that parent-and-child unit — not for the child alone, and never for a metric.

## How it's built

- **Single file, no build step.** The whole app is `docs/index.html` — vanilla JavaScript, no backend, no accounts, no telemetry.
- **Local-first by architecture.** Every bit of data lives in your browser's `localStorage`. Nothing is sent anywhere. Export a JSON backup anytime from **Settings → Data**, and import it on another device.
- **Parent-facing only**, on principle. The child's interfaces are the printed mission card and you.

## Run it

Open `docs/index.html` in any modern browser, or serve the folder as a static site (it's published via GitHub Pages). HTTPS lets you install it to a phone's home screen — a web manifest and icons are included; there's no offline service worker yet.

## A note on what this is

Lantero is an early prototype, shared with friends and family for feedback. It's a real product in the making, but it isn't finished, and it is **not legal advice** for homeschool compliance — verify requirements with HSLDA and your state's education agency.

If you're testing it, start with **[ONBOARDING.md](ONBOARDING.md)** — it walks you through the first run and tells you exactly what feedback is most useful.

To send feedback, use the **Send feedback** button in the app header (it opens an email), and attach your backup JSON if you can.
