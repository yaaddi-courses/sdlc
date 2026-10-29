# Iterative, Spiral and Agile models, and DevOps

**Covers:** Iterative model, Spiral model, Agile, DevOps

## Learning by building in loops {#overview}
The problem with doing everything in order is that you only learn whether you built the right thing at the very end. The models in this article respond by working in loops: build a little, get feedback, improve, repeat. They differ in what each loop focuses on. One just repeats, one adds risk checks, one adds frequent contact with users, and the last joins building with running.

## Iterative model {#iterative-model}
The iterative model builds a system through repeated cycles. The first cycle produces a small working version. Each later cycle adds features and improves what exists, based on what was learned.

Because users see something early, misunderstandings surface in weeks, not months. The risk is drifting without an end, so each cycle needs a clear goal and an agreed outcome.

## Spiral model {#spiral-model}
The spiral model, proposed by Barry Boehm in 1986, combines repeated cycles with a risk analysis at the start of each one. Every loop goes through four steps: set the objectives, identify and reduce the biggest risks, build and test, and plan the next loop.

The drawing is a spiral that grows outward as the system grows. It suits large, expensive or uncertain projects where a wrong turn would be costly, such as a new aircraft control system. Its weakness is overhead. Careful risk work makes little sense for a small, familiar project.

## Agile {#agile}
Agile is an approach that delivers working software in short, frequent cycles, usually one to four weeks, and keeps adjusting the plan as real feedback arrives. It comes from the Agile Manifesto of 2001, written by seventeen practitioners, which values individuals and interactions, working software, customer collaboration and responding to change, while still valuing the items on the other side of each pair.

Popular frameworks are Scrum, with fixed-length sprints and regular reviews, and Kanban, with a continuous flow limited by how much work is in progress. Agile works best when requirements change and users can give regular feedback. It needs discipline: without planning and testing, "agile" can turn into disorder.

## DevOps {#devops}
DevOps is a way of working that joins development and operations in one shared responsibility, so the same team builds the software and keeps it running. Before this idea, one group wrote the code and threw it over a wall to another that ran it, and each blamed the other when problems occurred.

DevOps relies on automation: continuous integration, automated releases, monitoring and reproducible environments. The saying "you build it, you run it" captures the spirit. Teams measure themselves with four numbers: how often they deploy, how long a change takes to reach users, how often a change causes a failure and how fast they recover.

## A worked example {#example}
A start-up builds a recipe app. Compare how each model would handle the same 12 weeks.

| Model | What happens | Strength | Weakness |
|---|---|---|---|
| Iterative | Three 4-week cycles; each releases an improved version | Early user feedback | Needs a clear goal for each cycle |
| Spiral | Before each cycle, the team analyzes risk (for instance, "will the photo upload scale?") | Avoids costly surprises | Extra effort for a small project |
| Agile | Six 2-week sprints with a demo to users each time; the backlog is reordered after each | Adapts quickly | Needs steady discipline |
| DevOps | Same sprints, but the team also runs the app and sees live errors | Faster, more reliable releases | Needs automation and a broad skill set |

For a small team with unclear requirements, Agile with DevOps habits fits well. For a project with one huge risk, such as a new payment technology, a spiral-style risk step at the start is worth the cost.

Numbers: with 12 weeks and 2-week sprints, the team has 6 chances to learn from users. With a single release at the end, it has 1.

## A common mistake {#mistake}
Using "agile" to mean "no plan". Agile teams plan constantly, in short horizons. Another mistake is adopting DevOps by renaming the operations team. The change is about shared ownership and automation, not the label on a door.

## Key points {#key-points}
- The iterative model improves a working system through repeated cycles.
- The spiral model adds an explicit risk analysis to every cycle, and suits large uncertain projects.
- Agile delivers in short cycles and adjusts to feedback.
- DevOps joins building and running into one responsibility, backed by automation.
