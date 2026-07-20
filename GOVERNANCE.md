# CompoSeq Governance

## 1. What is CompoSeq?

CompoSeq is an umbrella organization of independently maintained open-source projects that share a common set of standards for representing and operating on genomic information based on composable interfaces and declarative query primitives.

CompoSeq governs several interfaces:

- the **Arrow schema specifications** for genomic data types;
- the **kernel semantics** that define what a genomic spatial operation must compute to be correct;
- the **GIQL specification** grammar, semantics, and conformance suite;
- the **RFC process** by which all of these change.

Member projects retain full autonomy over their own code, release schedules, internal roadmaps, technical direction, and day-to-day maintenance. The organizing principle is subsidiarity: a decision is brought to CompoSeq if it cannot be made within a single project without breaking a shared interface.

## 2. Member projects

A project becomes a member project if (a) it implements at least one CompoSeq specification and passes its conformance suite and (b) its maintainers agree to this document and the Code of Conduct. Membership does not require a repository transfer. 

A project may leave at any time by notifying the Steering Council.

The Steering Council may by unanimous vote remove a member project that is unmaintained for 12 months or persistently violates the Code of Conduct.

## 3. Roles and Steering Council


Maintainers are contributors who hold merge rights on a specific member project repository and additionally set direction for a member project, including triage, releases, and roadmap.

The Steering Council (SC) is the decision-making body for the organization. At founding, the SC consists of one maintainer per member group. A member group may consist of an academic lab, research group, or company that maintains one or more member projects. A member group's other maintainers may attend SC discussions, participate in discussions, and propose RFCs, but do not vote. The SC may elect by unanimous vote additional maintainers to become SC members as it sees fit. 

SC members that have not contributed to the project for 12 months will be asked if they want to become Emeritus members and recant their rights until they become active again. The list of SC members, active and emeritus is public in [STEERING.md](STEERING.md). Each January the SC reviews its members and confirms or updates the roadmap ownership.

## 4. Decision making

We use a "consensus seeking" process for making decisions. The group tries to find a resolution that has no open objections among maintainers. Maintainers are expected to distinguish between fundamental objections to a proposal and minor perceived flaws that they can live with, and not hold up the decision-making process for the latter. If no option can be found without objections, the decision is escalated to the SC, which will itself use consensus seeking to come to a resolution. In the unlikely event that there is still a deadlock, the proposal will be adopted if it has the support of a simple majority of the SC.

## 5. The RFC process

A good RFC states the problem before the solution, considers alternatives seriously (including doing nothing), specifies the migration path for existing data and code, and says what would make this a mistake. An RFC is not required for implementation details, performance work, bug fixes, docs, or anything internal to one project, even if it is large. An RFC is needed when a change would make two projects disagree about what the same query, schema, or operation means.

```
Proposal → Draft → Review → Accepted → Implemented
                                     ↘ Rejected / Postponed
```

- Proposal: an informal statement that someone would like to lead an effort to change a specification.
- Draft: PR to `composeq/rfcs` using the template.
- Review: open discussion. Anyone may comment.
- Discussions: comments and feedback are collected and changes are made.
- Accepted: merged with a number and a decision record. Acceptance means the design is agreed, not that anyone has committed to build it.
- Implemented: at least one member project ships it and passes the conformance suite. A specification is not final until something implements it.

## 6. Amending this document

Amendments require unanimity of the SC. The current version and its full history are public in git.
