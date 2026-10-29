# Waterfall and the V-Model

**Covers:** Waterfall, V-Model

## Doing it in order {#overview}
The earliest and most intuitive way to organize a software project is to do it in order: first find out what is needed, then design, then build, then test, then release. Each step finishes before the next begins. It is the way most buildings and bridges are made, and it was the way software was first managed. Two well-known models follow this idea, the second being an improvement on the first.

## Waterfall {#waterfall}
Waterfall is a model in which a project moves through its phases in strict order, with each phase finished completely before the next begins, like water flowing down steps. The phases are usually requirements, design, implementation, testing and maintenance.

Its strengths are clarity and control. Everyone knows what phase the project is in, there is a document at the end of each phase and the plan is easy to track. It suits projects whose requirements are well understood and unlikely to change, such as building software for a regulated device.

Its weakness is that changes are costly. If testing in month ten reveals that a requirement was misunderstood in month one, a lot of work must be redone. Users see the product only at the end.

Many people trace the model to a 1970 paper by Winston Royce. Interestingly, he presented the strict sequence as a risky approach and suggested going back between phases.

## V-Model {#v-model}
The V-Model extends Waterfall by pairing every development phase with a matching test phase. When drawn, the phases go down the left side of a V as the system is defined in more detail, and up the right side as it is tested at growing scale.

The pairs are:

| Development phase (down) | Matching test (up) |
|---|---|
| Business requirements | Acceptance testing |
| System design | System testing |
| Architecture design | Integration testing |
| Module design | Unit testing |

The point is to plan the tests at the same time as each design phase, so that each requirement has a test written for it before any code exists. It improves quality and traceability. It shares Waterfall's weakness: changes late in the project remain expensive.

## A worked example {#example}
A company builds the software for a medical pump, where the requirements are fixed by regulation. They choose the V-Model. See how a single requirement travels through it:

1. Requirement: "The pump must stop within 1 second of a blocked-tube alarm."
2. At the same moment, an acceptance test is planned: "Block the tube and time the stop."
3. System design splits the job into sensor, controller and motor. A system test is planned for the combination.
4. Architecture design defines the messages between them. An integration test is planned for the sensor-to-controller link.
5. Module design defines the function that reads the sensor. Unit tests are planned for it.
6. The code is written. Unit tests run first, then integration, system and acceptance tests, from the bottom of the V's right side to the top.

Suppose a mistake in step 4 is found at step 6 during integration testing. The team goes back two levels, which costs a few weeks, but nothing reaches the patient.

## A common mistake {#mistake}
Choosing a sequential model because it feels organized, even when the requirements are still unclear. For a new product whose users have not been asked, strict order means learning the truth too late. Another mistake is thinking Waterfall forbids any looping back. Real projects often allow small steps back, but each one is a cost.

## Key points {#key-points}
- Waterfall moves through phases in strict order, and each one finishes before the next begins.
- It suits stable, well-understood requirements and is expensive when requirements change.
- The V-Model pairs each development phase with a test phase and plans tests early.
- Both models make late changes costly.
