---
layout: post
title:  "Velocity EU Conference 2014 – Day 2"
date:   2014-11-18 13:43:17
tags: oreilly velocity conference 2014
---
Disclaimer - 2 of my friends that I work with at the Government Digital Service (GDS) gave talks.

## Microservices – What an ops team needs to now

This was a talk by [Michael Brunton-Spall](https://twitter.com/bruntonspall) from GDS. He covered:

- why you might use a microservices architecture
- how to make it easier to allow experimentation
- Theory of Constraints and how it applies to microservices and teams. This was quite short and is probably worth a talk in its own right
- the services that should be provided by operations to ease the transition to microservices
- the importance of developers operating services they build
- why tools like Spanner and Zipkin are needed for the distributed systems that microservices create
- having different teams at different maturity phases for a service; eg active development versus handing over to an SRE team, and when it might be handed back
- the difference between deep and shallow healthchecks, and why you probably need both

[My notes on Michael's talk](https://flic.kr/p/pPuwiS).

## Performance is a People Problem

[Ben Evans](https://twitter.com/kittylyst) gave a talk inspired by Gerry Weinberg's quote – "it's always a people problem". He stressed the importance of a scientific, measurement-driven approach:

1. Have a hypothesis
1. Measure
1. Make a single change
1. Measure again

Not enough people do step 3 properly, and instead make more than 1 change at a time.

### Goals

We tend to have one or more of the following goals when changing a system:

1. Reduce risk of future change
1. Improve reliability
1. Increase maintainability
1. Quantifiable impact (sell more, make cheaper etc)

### Anti-patterns

- UAT is the developer machine aka it works on my machine
- Production-like data is hard to play with outside of production (so benchmarks often aren't applicable)
- Playing with switches (rather than doing meaningful work)
- Configuration by Fairy Tales – we always set the bifur-fibrillator to 111
- Performance Tips have a shelf-life (JVM GC tends to get better with each release, making GC tuning settings obsolete / counter-productive)
- Blame Donkey (it's always the IO / network for that sub-system)
- Microanalysis – getting bogged down in detail
- Throw it over the wall – silos are bad, m'kay?

### Solutions

1. Collect data
1. Analyse data
1. Publish data
1. Change things

[My notes on Ben's talk](https://flic.kr/p/pPwPdt).

## Collaboration Beyond the Tech Silo

[James Stewart](https://twitter.com/jystewart) of GDS. I'm pretty familiar with this topic, so my notes are a bit lacking.

The unit of delivery is the team. Big organisations don't happen overnight, they grow over time and accrete aural history. This can lead to the situation where people don't challenge the established way of doing things, since they can (wrongly) believe that they can't change things.

### Procurement (or buying stuff)

Allies for the changes you want to make are everywhere, you just need to find them. For instance, we wanted to make it possible to work with smaller companies with simpler discrete pieces of work. We found people that were the subject matter experts and removed blockages from their path.

### Attitude to risk

Having sensible conversations with the right people is always useful. Initially in government, we found lots of people that said "you can't do X, because security". Ensure you delve into what the risks are, and what proportionate investments need to be made. Frequently, we could do X.

### Experiments in government

When we first started, it was a lot easier to ask for £100 million to do a big risky thing, rather than asking for £100 thousand to learn whether the big risky thing was even the right thing to be trying to solve. Accepted wisdom was that government worked in a waterfall fashion, with lots of project boards and documentation to get to the point where a project could begin.

We questioned this, and worked with the people for whom all this process and documentation was supposedly for. It transpired that they also wished for a better way of doing things, so we worked with them to design the process they wanted. It's now government policy to start small, do a short, quick discovery process and change direction early, rather than taking 3 years to deliver a thing.

### Roadmaps (or marrying agile with heavyweight process)

Our colleague [Jamie Arnold](https://twitter.com/itsallgonewrong) wrote about how he and [Richard Pope](https://twitter.com/memespring) use roadmaps to help bridge the gap between agile and GANT worlds.

[My notes on James's talk](https://flic.kr/p/pa8yNC).

## Using Promise Theory to Improve Digital Service Quality

[Jeff Sussna](https://twitter.com/jeffsusna) 

Intention + Expression = Benefit

BUT the benefit may or may not come to pass

A service is:

- an experience
- a relationship
- co-creation

AirBnB talk about 'the product is the trip' --- not a place to stay.

We deal with trust a lot in relationships. Trust is not a fixed quantity, it varies over time:

- Auto-scaling
- Circuit breakers around 3rd party services
- Continuous integration to check the build is green
- Designing for failure and resilience

Promise Theory helps span different boundaries, while giving a common language?

It may be possible to use promise theory to write stories / acceptance criteria.

### References
- Mark Burgess — [In Search of Certainty](http://www.amazon.co.uk/In-Search-Certainty-Information-Infrastructure-ebook/dp/B00ENEEWYO)
- Mark Burgess / Jan Bergstra — [Promise Theory](http://www.amazon.co.uk/Promise-Theory-Principles-Applications-1/dp/1495437779/ref=asap_B001IXTSLU?ie=UTF8)
- Fernando Flores / Terry Winograd — [Understanding Computers and Cognitition](http://www.amazon.co.uk/Understanding-Computers-Cognition-Foundation-Design/dp/0201112973)

[My notes on Jeff's talk](https://flic.kr/p/pabBdS).

## How BBC Sport Scales Engineering

Here, [Keith Mitchell](https://twitter.com/specialized) talked about how BBC Sport works behind the scenes. He covered 4 main topics.

### People and Process
* Pick a process
* Continuously improve that
* Don't have a dev team, have a multi-disciplinary delivery team
 
### Engineering Excellence
* Meaningful code reviews
* Devs are accountable for Non-functional requirements
* Continuous Integration
* Automated Tests
 
### Build and Release
* Release Manager app
* Hack days and innovation time (bleurgh)
** let people scratch their own itch and make it better
 
### Tooling
* Using Docker in AWS to create test environments
* https://github.com/bbc-sport/viewportertool
* Going to add performance budget tool to deployment pipeline — if a change blows the performance, then it shouldn't be deployed
 
https://github.com/bbc-sport contains more of their code.

[My notes on Keith's talk](https://flic.kr/p/pPyX9M).
