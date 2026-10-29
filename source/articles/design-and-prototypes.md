# Designing before you build

**Covers:** high-level design, low-level design, design document, prototype

## Plans are cheaper than code {#overview}
Changing a drawing costs minutes, while changing finished code can cost days. Design is the phase that uses that fact: you work out the shape of the system on paper, agree it with the team, and test risky ideas cheaply before committing. This article covers the two levels of design, the document that records it, and the quick experiments that test an idea.

## high-level design {#high-level-design}
High-level design is the first pass at the system's overall shape, without working out every inner detail. It answers questions like: what are the main parts, what does each one do, how do they talk to each other, and where does the data live?

A typical output is a simple diagram with a few boxes, such as a mobile app, a web server, a database and an email service, with arrows between them. At this level you also make the big choices, such as which technology to use. Mistakes here are the most expensive, so it deserves the most discussion.

## low-level design {#low-level-design}
Low-level design comes next and works out the exact internals of each part: the data structures, the tables and fields, the functions and how they call each other, and the handling of errors.

Think of it as the difference between a map of a country and a map of a street. The high-level design shows where the highways go. The low-level design shows each turn. A developer should be able to start writing code from it without guessing.

## design document {#design-document}
A design document is a written record, made before the code, of the planned structure and approach, so that the team can discuss and agree on it. It need not be long. A useful one has:

- the problem and the goals, and also what is not a goal,
- the proposed design, with a diagram,
- alternatives considered and why they were rejected,
- risks and open questions.

Writing it forces you to find gaps. It also helps people who join later understand why something was built a certain way.

## prototype {#prototype}
A prototype is a deliberately rough, throwaway version of a product or feature, built quickly and cheaply to test whether an idea works. It could be a clickable mockup with no real code behind it, or a small program that tries one risky technique.

The purpose is to learn. Show it to users, find out what confuses them, and change the plan. Because it is cheap, throwing it away is not a loss. The danger is the opposite: a prototype that quietly becomes the real product, carrying shortcuts that were never meant to last.

## A worked example {#example}
A team designs a photo-sharing feature.

| Step | Output |
|---|---|
| High-level design | Four boxes: phone app, upload service, storage, notification service |
| Low-level design | Table `photos` with columns `id`, `owner`, `file_path`, `created_at`; the upload function checks size and file type before storing |
| Design document | Two pages with the diagram, the goal "upload in under 5 seconds", the rejected option "store photos in the database", and a risk "large files on slow networks" |
| Prototype | A clickable mockup shown to five users; three of them did not find the upload button |

The prototype cost two days. It revealed a problem in the screen layout that would have cost weeks if found after the code was written. The team moved the button, tested again with five more people, and then started building.

## A common mistake {#mistake}
Making the design so detailed that it becomes code on paper, or so thin that it says nothing. Match the detail to the risk: be careful about the parts that are hard to change later, and relaxed about the rest. The second mistake is shipping the prototype. Decide at the start that it will be discarded, and write the real thing properly.

## Key points {#key-points}
- High-level design sets the overall structure, and low-level design fills in the internals.
- A design document records the plan, the alternatives and the risks so the team can agree.
- A prototype is a cheap experiment. Learn from it, then throw it away.
- Spend design effort on decisions that are expensive to change.
