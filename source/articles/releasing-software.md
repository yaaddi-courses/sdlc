# Releasing software safely

**Covers:** deployment, blue-green deployment, continuous integration, continuous delivery, continuous deployment, release management

## Getting changes to users without drama {#overview}
Writing the code is only half of the job. It must also reach users, and every release is a risk: a mistake can affect everyone at once. Teams therefore build habits and tools that make releases small, frequent and boring. This article starts with the act of releasing and then looks at the practices that make it safe.

## deployment {#deployment}
A deployment is the act of releasing a version of the software so that it runs where real users can reach it, for example by putting a new build onto the servers behind a live website. Writing code and deploying it are different steps: code that is not deployed helps nobody.

A deployment can fail in ways the tests did not predict, because the live environment has real data, real traffic and real settings. That is why strategies exist to limit the damage.

## blue-green deployment {#blue-green-deployment}
Blue-green deployment keeps two full copies of the live environment, called blue and green. Users are on one of them, say blue. You install the new version on the idle one, green, and test it there with no users watching. When you are satisfied, you switch all the traffic from blue to green at once.

The big advantage is a fast way back: if something goes wrong, switch the traffic back to blue within seconds. The cost is running two environments, which is more expensive. Changes to the database need care, because both versions must work with the same data during the switch.

## continuous integration {#continuous-integration}
Continuous integration, often written CI, is the practice of merging code changes into the shared codebase frequently, at least daily, and running the automated tests on every change. Instead of saving up a huge merge that breaks in many places, the team finds problems when the change is small and fresh in the author's mind.

A CI server watches the code. Each time someone pushes a change, it builds the software and runs the tests, and reports a pass or a fail. A failing build is fixed straight away.

## continuous delivery {#continuous-delivery}
Continuous delivery goes one step further. Every change that passes the tests is prepared so that it could be released at any moment, and a person decides when to press the button. The software is always in a releasable state, but the final release stays a human choice, often for business reasons such as timing a launch.

## continuous deployment {#continuous-deployment}
Continuous deployment removes that last human step. Every change that passes all the automated checks goes live automatically, with no manual approval. It needs strong tests, good alerts and a quick way to roll back, because nobody reviews the final step.

The difference between the last two is a single decision. In delivery, a person releases. In deployment, the pipeline does.

## release management {#release-management}
Release management is the work of deciding and coordinating exactly what ships and when: which changes go into version 2.3, what the release notes say, who approves it, and what happens if it fails. It reduces surprises for users and for the teams that depend on the release.

Useful tools are a release calendar, version numbers that signal the size of a change, release notes in plain language and a checklist for the day.

## A worked example {#example}
A team releases a change using a pipeline:

1. A developer merges a small change, and CI builds it and runs 800 tests in 6 minutes. All pass.
2. The change is packaged and sent to a test environment. This is the end of delivery: it is ready.
3. Under continuous delivery, the product owner presses Release on Tuesday morning. Under continuous deployment, the pipeline would have done it already.
4. With blue-green deployment, the new build goes to green. Smoke tests pass, so traffic switches at 10:00.
5. At 10:04 the error rate doubles. The team switches traffic back to blue by 10:05. Users were affected for about five minutes.
6. The release manager records the event in the release notes and plans the fix for the next release.

Compare with a release done by hand once a quarter, with 200 changes together: when something breaks, nobody knows which of the 200 changes caused it.

## A common mistake {#mistake}
Treating continuous delivery and continuous deployment as the same thing. The first keeps a person in charge of the release. The second does not. A related mistake is deploying without a rollback plan. Decide how to go back before you go forward.

## Key points {#key-points}
- A deployment puts a version where users can reach it. Plan for failure.
- Blue-green deployment keeps two environments and switches traffic, so rollback is fast.
- CI merges and tests small changes often. Continuous delivery keeps software ready to release, and continuous deployment releases automatically.
- Release management coordinates what ships and when.
