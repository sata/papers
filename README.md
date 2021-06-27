# Purpose

Start documenting the papers I read so that I can find them later for
references if they were interesting.

Check [wiki](https://github.com/sata/papers/wiki) for articles that I haven't stored in the repo.

# Comp Sci Papers

## Reliability/Distributed systems/

| Title                                                                                                                                     | Status             | Notes                                                                                |
|-------------------------------------------------------------------------------------------------------------------------------------------|--------------------|--------------------------------------------------------------------------------------|
| [Communicating Sequential Processes](csp.pdf)                                                                                             | :eyes:             | Golang channels essentially..                                                        |
| [Making reliable distributed systems in the presence of software errors](armstrong_thesis_2003.pdf)                                       | :eyes:             |                                                                                      |
| [Why Do Computers Stop and What Can Be Done About It?](tandem_computers_why_computers_stop_85.7.pdf)                                      | :heavy_check_mark: | referenced from Joe Armstrong's PhD, [My notes](notes/gray_why_do_computers_stop.md) |
| [A contention adapting approach to concurrent ordered sets](ordered_sets.pdf.pdf)                                                         | :eyes:             | [Erlang blog post](https://blog.erlang.org/the-new-scalable-ets-ordered_set/)        |
| [A Message System Supporting Fault Tolerance](borg-1983.pdf)                                                                              | :eyes:             | referenced in *Why do computers stop*, precursor to Event Sourcing systems?          |
| [Distributed Computer Systems - Four Case Studies](TR-85.5.pdf)                                                                           | :eyes:             | referenced in *Why do computers stop*                                                |
| [Fail-Stop Processors: An Approach to Designing Fault-Tolerant Computing Systems](357369.357371.pdf)                                      | :eyes:             | [0]                                                                                  |
| [Towards an API for the Real Numbers](3385412.3386037.pdf)                                                                                | :eyes:             | [1]                                                                                  |


[0] Referenced in [Why do computers stop](tandem_computers_why_computers_stop_85.7.pdf), the "fail fast module", perhaps where Joe got the inspiration about let it crash?
[1] [From The morning paper](https://blog.acolyer.org/2020/10/02/toward-an-api-for-the-real-numbers/), reminds me of a erlang system using external system for calculating real numbers.

## Networks/Architecture

| Title                                                                                                                                     | Status             | Notes                                                                   |
|-------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------------------------------------------------------------------|
| [A Brief Introduction to Named Data Networking](NDN18.pdf)                                                                                | :heavy_check_mark: | Useful intro. to the subject, lots of good references                   |
| [Leveraging Content Connectivity and Location Awareness for Adaptive Forwarding in NDN-based Mobile Ad Hoc Networks](3405656.3418713.pdf) | :heavy_check_mark: | MANETs in NDN, similar aspects to Haggle, just on NDN                   |
| [From Opportunistic Networks to 3GPP Network-Independent Device-to-Device Communication](oppnet23gpp.pdf)                                 | :heavy_check_mark: | The evolution of DTN, OppNets to commercial adoptation in 3GPP'12       |
| [Supporting Delay Tolerant Networking: A Comparative Study of Epidemic Routing and NDN](li2020supporting.pdf)                             | :heavy_check_mark: | Comparison of DTN on IP approaches and how it could be supported in NDN |



# GNU/Linux
| Title                      | Status | Notes |
|----------------------------|--------|-------|
| [Wireguard](wireguard.pdf) | :eyes: |       |

# Practices
| Title                               | Status | Notes                                     |
|-------------------------------------|--------|-------------------------------------------|
| [Chaos Engineering](1702.05843.pdf) | :eyes: | I should read this to improve fire drills |

# Book club notes
* [How to Measure Anything: Finding the Value of Intangibles in Business](./bookclub/howto_measure_anything.md)
