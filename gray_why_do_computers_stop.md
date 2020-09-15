# Why do computers stop and what can be done about it? Jim Gray

## Context of reading the paper

This is one of the early papers references in Joe Armstrong's PhD
thesis. I wanted to see what were the papers he studied and found
inspiring to writing Erlang/OTP. This paper is written in 1985 and is
still very relevant!

## Conclusions

Nothing is really new, to be honest. Modularity, Idempotency, fault
tolerance principles etc. It's already been solved at one layer. Event
Sourcing is just another layer for what Borg speaks of in A "Message
System Supporting Fault Tolerance".

Fail fast modules/processes, is essentially the whole approach to
supervisors in Erlang. Crash it, reset to a known state and resume
traffic (i.e retry operation).


## Notes
"parts of the system may fail but the rest of the system must tolerate failures and continue delivering service"

MTBF = Mean Time Between Failures
MTTR = Mean Time To Repair

Availability = MTBF / (MTBF + MTTR)

Page 4 about Von Neumann was fun to read in regards to modularity: "In
his model, a redundancy 20,000 was needed to get a system MTBF of 100
years." ... "Still, it's not very obvious why von Neumann's machines
required a redundancy factor of 20,000 while current electronic
systems use a factor of 2 to achieve very high availability. The key
difference is that Von Neumann's model lacked modularity, a failure in
any bundle of wires, anywhere, implied a total system failure."

It also touches on where Joe got the inspiration with regards to "Fail
Fast -- the module either functions properly or stops" - Fail-Stop
Processors, an Approach to Designing Fault-Tolerant computing systems,
Schlichting.

Even the design principles mentioned of fault tolerant hardware can be used for designing software (page 5):

- Hierarchically decompose the system into modules
- Design the modules to have MTBF in excess of a year.
- Make each module fail-fast -- either it does the right thing or stops.
- Detect module faults promptly by having the module signal failure
  or by requiring it to periodically send an I AM ALIVE message or
  reset a watchdog timer.
- Configure extra modules which can pick up the load of failed
  modules. Takeover time, including the detection of module failure,
  should be seconds. This gives an apparent module MTBF measured in
  millennia.

Erlang GenServers with supervisors is essentially capturing this
thinking very well. Crash the gen-server with polluted state. Even
though it's focused on hardware and does not address 'state' it's
quite interesting inspiration.

### An Analysis of Failures of a Fault-Tolerant System

Really admiring the way Tandem Computers kept reports/information to
be analysed in terms of why it failed, for what reason etc. Being able
to draw conclusions from this set of information is tremendously
important.

I would say this is equivalent of what most companies today do with
Post-Mortens and writing up reports in regards of incidents.

### Human errors

Page 12, pointing out software upgrade/releases is one of the main
reasons of failures is of course funny to read given how accurate
description this is.  "The top priority for improving system
availability is to reduce administrative mistakes by making
self-configured systems with minimal maintenance and minimal operator
interaction."

In essence they're talking about automation and less configuration!

### Fault tolerant execution

Here we can see the ideas behind the hardware design being adapted to software design:

- Software modularity through processes and messages.
- Fault containment through fail-fast software modules.
- Process-pairs to tolerate hardware and transient software faults
- Transaction mechanism to provide data and message integrity.
- Transaction mechanism combined with process-pairs to ease exception
  handling and tolerate software faults.

Sounds familiar?

"The process achieves fault containment by sharing no state with other
processes; rather, its only contact with other processes is via
messages carried by a kernel message system."

Bohrbug/Heisenbug hypothesis

"If the program state is reinitialised and the failed operations
retried, the operation will usually not fail the second time."


The different process-pair approaches for fault-tolerant execution.

Lockstep - active standby - doesn't really do much for corrupt memory states.
State checkpointing - basically as the name says

page 21 - Automatic checkpointing

Paper A Message System Supporting Fault Tolerance  - Borg

"automatically manages the checkpointing... all messages to and from a
process are saved by the message kernel for the backup process. At
takeover, these messages are replayed to the backup to roll it forward
to the primary process' state" - basically Event Sourcing is being
described.

Transactions - ACID terms etc, we all know them. Haeder - Principals
of Transaction-Oriented Database Recovery

"so we can simply abort all uncommitted transactions associated with a
failed persistent process and then restart these transactions from
their input messages. This cleans up the database and system states,
resetting them to the point where the transaction began."

Borr - "Transaction monitoring in ENCOMPASS" --^

All about being able to continue from a failure, without manual
intervention, cleaning.

Fail fast, crash, set the state, and retry.

Session sequence numbers mentioning idempotency between
request/replies was lovely to see.

Gray - Distributed Database Systems -- Four Case Studies

### Follow up papers to read
- Schlichting - an Approach to Designing Fault-Tolerant computing systems
- borg - A Message System Supporting Fault Tolerance
- Borr - Transaction monitoring in ENCOMPASS
- Gray - Distributed Database Systems -- Four Case Studies
