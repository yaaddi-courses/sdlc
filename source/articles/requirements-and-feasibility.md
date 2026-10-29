# Requirements, user stories and feasibility

**Covers:** requirements gathering, functional requirements, non-functional requirements, user story, acceptance criteria, feasibility analysis, ROI

## Know what to build before you build it {#overview}
The most expensive mistakes in software happen early and are found late: building the wrong thing, or a thing that is not worth building. The first phases exist to prevent that. You find out what people need, write it in a form the team can test, and check that the project is worth the cost. Let's take those steps one at a time.

## requirements gathering {#requirements-gathering}
Before anything is built, you talk to the people who will use or pay for the system, to find out what it needs to do. This early work is requirements gathering. It feeds both the project plan and the design.

Common methods are interviews, surveys, watching people do their work, workshops with several stakeholders and reviewing the current system. Two rules help. Ask about the problem, not only the solution, because users often ask for a feature when the real need is different. And write down what you learn so that everyone works from the same list.

## functional requirements {#functional-requirements}
Functional requirements describe what the system must do: its features and behavior. An example is "a user can reset a forgotten password by email." Each one names an action or a result that you can demonstrate.

## non-functional requirements {#non-functional-requirements}
Non-functional requirements describe how well the system must do its job: speed, security, reliability, ease of use and capacity. An example is "the reset email arrives within 10 seconds, even with 10,000 users online."

These are often forgotten until late and then cause painful changes. A system that does the right things slowly or insecurely has not met its requirements.

## user story {#user-story}
A user story describes a feature from the point of view of the person who needs it, in the form "As a (kind of user), I want (goal) so that (reason)." For example: "As a shopper, I want to save items for later so that I can buy them on payday."

The "so that" part matters. It explains the purpose, so the team can suggest better ways to meet it. Stories are deliberately small and leave details to conversation.

## acceptance criteria {#acceptance-criteria}
How do you know a story is done? Acceptance criteria are the specific, checkable conditions that answer this. They remove arguments about whether the work is finished. A popular format is "Given a situation, when something happens, then this result follows."

For the shopper story: "Given I am signed in, when I tap Save, then the item appears in my saved list, and it is still there after I log out and in again."

## feasibility analysis {#feasibility-analysis}
Before real money or time is spent, ask whether the project is realistic and worth doing. That early check is a feasibility analysis. It looks at four questions: can we build it with our technology and skills, is it affordable, will the organization be able to run it, and is it legal and safe?

The answer may be "no", and that is a good result. Stopping a bad project in week one costs far less than stopping it in month eight.

## ROI {#roi}
ROI stands for return on investment. It compares what a project earns with what it cost. A plain form is (gain minus cost) divided by cost, shown as a percentage. Say a tool costs 50,000 and saves 80,000. The ROI is (80,000 minus 50,000) divided by 50,000, which is 30,000 divided by 50,000, or 60 percent.

## A worked example {#example}
A shop wants a "save for later" feature. Let's see how a vague wish becomes something concrete.

| Item | Result |
|---|---|
| User story | As a shopper, I want to save items for later so that I can buy them on payday |
| Functional requirement | A signed-in user can save and remove items |
| Non-functional requirement | The saved list loads in under 2 seconds with 1,000 items |
| Acceptance criteria | Given I am signed in, when I tap Save, then the item is listed and stays after I sign out and in |
| Feasibility | Technically easy; 3 weeks of work; legally no issue |
| ROI | Cost 12,000; expected extra sales 30,000 a year; ROI = (30,000 - 12,000) / 12,000 = 150 percent in the first year |

Check the last row: 30,000 minus 12,000 is 18,000, and 18,000 divided by 12,000 is 1.5, or 150 percent. The table shows how a vague wish becomes something that can be built, tested and justified.

## A common mistake {#mistake}
A common slip is writing requirements as solutions: "add a drop-down menu" instead of "users must choose one of five options quickly". The first locks in a design before anyone knows whether it is best.

A second slip is skipping non-functional requirements because they are harder to write. Add at least a number for speed and for the expected number of users.

## Key points {#key-points}
- Requirements gathering finds out what the system needs to do, by talking to real users.
- Functional requirements say what it does, and non-functional ones say how well.
- A user story names a need, and acceptance criteria say how to tell it is met.
- Feasibility analysis and ROI check that the project is worth doing before you spend the money.
