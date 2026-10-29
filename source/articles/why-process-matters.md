# Why software needs a process

**Covers:** SDLC, ad-hoc

## From idea to retirement {#overview}
Every piece of software has a life. Someone has an idea, the team works out what it should do, builds it, tests it, releases it, keeps it running, and one day switches it off. Teams that manage this journey on purpose tend to ship better software, with fewer surprises, than teams that make it up as they go. In this article we will name the journey and see what goes wrong without a plan.

## SDLC {#sdlc}
SDLC stands for software development lifecycle. It is the sequence of phases that a piece of software passes through, from the first idea to its retirement. The usual phases are:

1. **Planning:** decide whether and why to build it.
2. **Requirements:** find out what it must do.
3. **Design:** decide how it will be built.
4. **Building:** write the code.
5. **Testing:** check that it works.
6. **Release:** put it in front of users.
7. **Maintenance:** fix, improve and monitor it.
8. **Retirement:** shut it down in an orderly way.

Different teams arrange and repeat these phases differently. Some go through them once in order, and others loop through them every few weeks. But the activities themselves appear in almost every project, even when nobody names them.

An SDLC is not paperwork for its own sake. Think of it as a shared map that tells everyone what is happening now, what comes next and who decides.

## ad-hoc {#ad-hoc}
Now imagine the opposite. Ad-hoc means done on the spot, without a planned and repeatable method. An ad-hoc approach to software is to start coding as soon as an idea appears, make decisions as problems arise and test whatever seems risky.

For a small experiment or a personal script, this is fine and fast. The trouble starts when the work grows. Results depend on who happens to do the job. Nobody can say when it will finish. Requirements are discovered late, so work is thrown away. Knowledge sits in one person's head, so when they leave, the project stalls. And the same mistakes repeat, because nothing was written down about how they happened.

## A worked example {#example}
Two teams each build a small booking tool, and each takes 10 weeks. Let's compare how they spend their time.

| | Ad-hoc team | Process team |
|---|---|---|
| Weeks 1 to 2 | Start coding at once | Agree on what the tool must do and how success is measured |
| Weeks 3 to 6 | Build features as ideas come | Build in planned pieces, testing each |
| Week 7 | Find out a key user group was ignored; rework 3 weeks | Review with real users and adjust |
| Weeks 8 to 10 | Rushed testing, bugs reach users | Final testing and release with a checklist |
| Rework | About 3 weeks | About 1 week |

The ad-hoc team started building two weeks sooner, but spent three weeks on rework, which is 3 out of 10, or 30 percent of the total. The process team spent two weeks planning and one on rework, about 10 percent. The numbers are illustrations, not measurements, but the pattern appears in many real projects: time saved at the start is often paid back with interest later.

## A common mistake {#mistake}
A common slip is believing that process means bureaucracy. A good process is as small as the project allows. For a weekend script, it might be one sentence of goal and a quick test. For software that handles money, it is much more. The mistake is to choose the amount by habit instead of by risk.

The opposite slip is to copy a heavy process from a large company into a tiny team.

## Key points {#key-points}
- The SDLC is the sequence of phases from idea to retirement, and every project has one, named or not.
- An ad-hoc approach works for small experiments but breaks down as work grows.
- Process is a shared map. Make it as small as the risk allows.
