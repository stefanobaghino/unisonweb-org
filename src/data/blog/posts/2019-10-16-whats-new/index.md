---
title: Here's what's been happening with Unison
description: Since our last update official update here, we started alpha testing a first release of Unison, gave a talk at Strange Loop, and have been working towards an M2 release with lots of new features, bugfixes, and polish.
date: 2019-10-16
authors: ["paul-chiusano"]
categories: ["news"]
featuredImage: /media/thing9.svg
---

Since our last update official update here, we started alpha testing a first release of Unison, gave [a talk on Unison at Strange Loop](https://www.youtube.com/watch?v=gCWtkvDQ2ZI), and have been working towards an M2 release with lots of new features, bugfixes, and polish. Our goal with M2 is to have the core language and tooling be "feature complete and totally usable". We have often used the metric of: "can write Unison libraries without hitting major gaps or bugs that cause you to want.

## Strange Loop was great!

<iframe width="580" height="436" src="https://www.youtube.com/embed/gCWtkvDQ2ZI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

The Strange Loop talk approached explaining Unison by just talking about how the core idea of content-addressed code (explained in the talk) leads to all these nice benefits, almost for free:

* No builds, easy renames, test caching, and just an overall nicer story for codebase management
* No depdendency conflicts
* Typed durable storage
* A nicer story for distributed execution and transparent code deployment
* ... and I could have kept going!! My favorite benefit that I didn't cover is having a codebase which is always runnable, never broken, and having structured refactoring sessions rather than long lists of compile errors. 

Content-addressed code is just one of those nice simple ideas that feels like it ought to become ubiquitous in languages of the future. But even though it feels like the right thing, it's also a fundamental change that affects just about everything about the developer experience. When Unison started as a research project based on this core idea, there were so many questions, like [if you can't ever modify a definition, only introduce new ones, how do you refactor or update a codebase?](https://twitter.com/unisonweb/status/1173942969726054401). What has been surprising and cool is that all the questions of "how do you do this in the Unison worldview" continued to have answers, answers that actually made a lot of sense (often MORE sense than what we do now) and we could uncover these answers just by actually thinking a little and keeping an open mind. That's been a lot of fun!

## Working towards our next release

In the months leading up to Strange Loop and since the conference, we've been really been focused on filling in some gaps in the developer experience. Some things we've added :

* You can view the history of your codebase (the `history` command)
* You can move around in that history.
* You can run `IO` programs without needing to add definitions to the codebase first.
* Literate Unison transcripts, for producing tutorial style documentation, for instance much of [the docs site](/docs) could be moved over to be generated via the transcript runner, and we're also using these transcripts internally for integration testing of 

Things we plan on getting done for our next major release:

* API documentation support
* Workflow for pull requests and code reviews
* Workflow for publishing and using Unison libraries
* A much better algorithm for refactoring types, which avoids manual propagation of edits
* Bugfixes and general polish - thank you to alpha testers for uncovering and reporting issues, we will be cranking through these

At this point the developer experience of using Unison will be pretty darn good and without major gaps.

## In progress: an ecosystem-wide code viewer with click-through to definition 

There's a cool project in the works that I wanted to mention here.

One downside of the Unison codebase not just being a collection of text files is we don't get to use dumb text based tools to view that code. I prefer to see this as a feature, though, in that it creates a bit of a vacuum which can be filled by something that is way _better_ than the text based tool.

Mitchell Rosen, Elliot Wu and friends have started on a [codebase browser for Unison](https://github.com/unisonweb/elm-browser) which we are planning on hosting here at unisonweb.org/browse when it's a little further along. The idea is that you can hyperlink to any Unison definition, in any Git repo, and have that definition be rendered with nice hyperlinks to all its dependencies. And rather than this being a build artifact that every library author must maintain and keep up to date, it is instead something that Just Works for all publicly hosted Unison code, without any action needed by library authors! It works by reading the underlying codebase format which has all the semantic information needed for this to be possible.

I am very excited for this to come online and kudos to the team for putting this together.

## Wrapping up

We will try to post updates more regularly than once every 6 months. 😀 In addition to this blog, feel free to come by the [Unison Slack](/community), which is a friendly spot to ask questions if you are trying out Unison. Besides GitHub, the #contrib channel is a good spot to follow along with Unison's development.

One more thing: Arya and I will be at [Scale By the Bay](https://sched.co/RoSk) in a month, giving a talk on Unison. 

That's all for now. 🌻