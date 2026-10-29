# Keeping software healthy after release

**Covers:** preventive maintenance, OS, monitoring, incident, root-cause analysis, RCA, deprecation

## Release day is the start {#overview}
It is tempting to think the work ends when the software ships. In fact most of a program's life comes after that day. Systems break, the world around them changes, and users want more. A healthy team spends its effort on four jobs: fixing and improving the system, watching it, responding calmly when it fails, and retiring parts that are no longer worth keeping.

## preventive maintenance {#preventive-maintenance}
Preventive maintenance means changing software after launch to head off a problem before it happens. Nothing is broken yet, but you can see that it will be. Examples include rewriting a fragile section of code, upgrading a library before its support ends, or adding a limit that prevents a disk from filling.

It sits next to three other kinds: corrective maintenance fixes bugs, adaptive maintenance adjusts the software to a changing environment, and perfective maintenance adds improvements. Preventive work is the easiest to postpone, because nobody complains about a problem that has not happened.

## OS {#os}
Your program does not run alone. It runs on top of an OS, or operating system, such as Windows, macOS, Linux, Android or iOS. The OS looks after the screen, memory, files and network for every program, and each program asks it for what it needs. This matters for maintenance because the ground moves under your program. A new OS version may change how permissions or notifications work, so an app that ran fine last year may break. Updating the software to suit a new OS is a typical case of adaptive maintenance.

## monitoring {#monitoring}
How do you find out that something is wrong before your users tell you? You watch the live system continuously. That is monitoring. It collects measurements such as response time, error rate and free memory, plus logs of what the system is doing, and raises an alert when a value goes out of range.

A widely used checklist from Google's site reliability engineers is the four golden signals: latency (how long requests take), traffic (how much demand there is), errors (how many requests fail) and saturation (how full the system is). Good alerts are few and actionable. If people get too many, they stop looking at them.

## incident {#incident}
An incident is an unplanned problem or outage in a live system that is serious enough to need an active response, such as a payment page that suddenly fails for everyone. The first goal is to restore service, not to find who or what caused it.

A common routine has five steps: detect the problem, assign a lead, reduce the harm with the quickest safe fix (such as rolling back the latest change), communicate to users and colleagues, and confirm that service is back to normal. Calm, clear roles matter more than heroics.

## root-cause analysis {#root-cause-analysis}
Once service is restored, the real question starts: why did it happen? Root-cause analysis is the deeper investigation into that question. Stopping at the first answer ("a server ran out of space") fixes only the symptom. Asking why repeatedly leads to causes like "no alert for low disk space, and no clean-up job".

A good analysis is blameless. It looks at how the system and the process allowed the failure, not at who made a mistake. It ends with specific actions that have owners and dates.

## RCA {#rca}
RCA is the short form of root-cause analysis. In team chat and in reports you will see "the RCA", meaning the written document that describes what happened, why, and what will change.

## deprecation {#deprecation}
Eventually some features stop being worth keeping. Deprecation is the planned retirement of a feature, with warning, a timeline and a replacement, instead of letting it decay without notice. Typical steps are to announce the plan, mark the feature as deprecated, offer a migration path, keep it running for an agreed period and finally remove it.

Doing this respectfully protects the users who depend on the old feature and lets the team stop paying to maintain it.

## A worked example {#example}
A shop's checkout stops working at 14:00. Let's follow the clock.

| Time | What happens |
|---|---|
| 14:00 | Monitoring raises an alert: errors on the payment page rose from 1 percent to 60 percent |
| 14:02 | An incident is declared, and Sam is named lead |
| 14:05 | The team sees that a release went out at 13:55, and rolls it back |
| 14:08 | Errors drop to 1 percent. Service is restored after 8 minutes |
| Next day | The RCA finds that a setting was missing on the new servers, and no test checked it |
| Follow-up | Add a test for the setting (owner: Mia, due Friday), and add the setting to the release checklist |
| Later | Preventive maintenance: the team schedules a clean-up of other fragile settings |

The incident cost 8 minutes, from 14:00 to 14:08. The review made sure the same problem would not return.

## A common mistake {#mistake}
A common slip is ending the story when service returns. Without an RCA, the same failure comes back.

A second slip is blaming a person. People then hide problems, and the team learns less. Keep the review about the system.

## Key points {#key-points}
- Preventive maintenance fixes weaknesses before they cause failures.
- Updates to the OS and other surroundings force changes in your software.
- Monitoring finds problems early. Track latency, traffic, errors and saturation.
- In an incident, restore service first, then run a blameless RCA with follow-up actions.
- Deprecation retires features with notice and a path forward.
