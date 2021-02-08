# Purpose

Start documenting the papers I read so that I can find them later for
references if they were interesting.

# Comp Sci Papers

| Title                                                                           | Link                                                 | Status                  | Notes                                                                                                                                                                                |
|---------------------------------------------------------------------------------|------------------------------------------------------|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Communicating Sequential Processes                                              | [Link](csp.pdf)                                      | skimmed before, re-read | Golang channels essentially..                                                                                                                                                        |
| Making reliable distributed systems in the presence of software errors          | [Link](armstrong_thesis_2003.pdf)                    | Unread                  |                                                                                                                                                                                      |
| Why Do Computers Stop and What Can Be Done About It?                            | [Link](tandem_computers_why_computers_stop_85.7.pdf) | Read                    | referenced from Joe Armstrong's PhD, quite interesting, [My notes](notes/gray_why_do_computers_stop.md)                                                                              |
| A contention adapting approach to concurrent ordered sets                       | [Link](ordered_sets.pdf.pdf)                         | Unread                  | [Erlang blog post](https://blog.erlang.org/the-new-scalable-ets-ordered_set/)                                                                                                        |
| A Message System Supporting Fault Tolerance                                     | [Link](borg-1983.pdf)                                | Unread                  | referenced in *Why do computers stop*, precursor to Event Sourcing systems?                                                                                                          |
| Distributed Computer Systems - Four Case Studies                                | [Link](TR-85.5.pdf)                                  | Unread                  | referenced in *Why do computers stop*                                                                                                                                                |
| Fail-Stop Processors: An Approach to Designing Fault-Tolerant Computing Systems | [Link](357369.357371.pdf)                            | Unread                  | referenced in *Why do computers stop*, the "fail fast module", perhaps where Joe got the inspiration about let it crash?                                                             |
| Towards an API for the Real Numbers                                             | [Link](3385412.3386037.pdf)                          | Unread                  | [From The morning paper](https://blog.acolyer.org/2020/10/02/toward-an-api-for-the-real-numbers/), reminds me of a erlang system using external system for calculating real numbers. |

# Practices
| Title             | Link                   | Status | Notes                                     |
|-------------------|------------------------|--------|-------------------------------------------|
| Chaos Engineering | [Link](1702.05843.pdf) | Unread | I should read this to improve fire drills |

# References
## Documentation of Architecture
* [Rust analyzer example](https://github.com/rust-analyzer/rust-analyzer/blob/d7c99931d05e3723d878bea5dc26766791fa4e69/docs/dev/architecture.md)
  * [Nygard's ADR](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions) is a good way of tracking _change_ however, rust-analyzer architecture document is a good example of maintaing a architecture _view_ of a system
