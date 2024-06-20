+++
title = '#7 Let us try Clojure'
date = 2024-06-20T06:27:32+05:30
draft = false
+++

# Summary
Not spending enough time these days due to other things I'm involved in. Going for Functional programming/Clojure for Zuperb.

# What's happening?

It's been a couple of days since I last sat down for Zuperb. Pop and Mom are in town. They staying with my sister, but I'm visiting them in the evenings after work.
There's also a workation coming up - to Munnar on Friday. So I'll be away from Zuperb for a couple more days. In the future, I want Zuperb to be available if I need in these kind of days as well. Something like God? Invisible, but everywhere 😛

# What's happening with Zuperb?

I've been going through various programming languages. In the last post, I said I want to try Flask vs. Express vs. Elixir. I continued to read about stuff from that point, and looks like I've found one that I may finally start building Zuperb in!

Listened to some videos on programming paradigms, evolution of languages, functional programming, etc. A few things/opinions I learned about:
- The original idea Small talk creator meant by 'Object oriented programming' is something like the Actor model: there are actors/processes/objects that can do stuff, and they talk to each other through messages.
- And things like OO people themselves suggest to use composition instead of inheritance, etc.
- Programming in functional style can reduce the chances of code rot, give peace of mind. This talk - [Functional Programming in 40 Minutes • Russ Olsen](https://www.youtube.com/watch?v=0if71HOyVjY&t=1730s) - is a recommended watch. I loved the picture he is painting with words about the functional world. I'm sold on it.

You can see I was already biased towards functional style. When [Pramode](https://pramode.net/) first introduced me to functional programming, I thought that's great. LISP was weird and cool. I must say, there is also some attraction due to the reputation that LISP, and functional languages have: 
- it is like mathematical functions
- very expressive
- maintainable in the long-run
- prove-able
- can reason about code better

All FP advocates seem to be saying if you want peace of mind, sanity, go for FP. That's the strongest temptation for me, I think. 

I've even felt other languages are not my taste. Maybe I'm comparing with the experience from LISP, haskell, etc. But those were small hello world programs. Let's see if I'll still like it after writing a fair amount in it.

Among functional languages, some time was spent on comparing Clojure and Elixir. I'm leaning towards Clojure. I also saw Clojure comes in the top of lists like 'most loved language', 'most paid', etc. 😉


# Hello Clojure

Clojure is a LISP, got paranthesis.
Duh, that's all I know.

Let me learn a little bit.

# Hello Pedestal
The guy in the video linked above, Russ,  works at Pedestal.

I can use that to develop web applications in Clojure.
http://pedestal.io/pedestal/0.7/index.html

One other blogpost I read also had this on the top of the list of 'frameworks' in clojure.

Oh, and by the way, I'm coming across (and bookmarking mostly) more and more interesting videos like this one - [Simple made Easy](https://www.youtube.com/watch?v=SxdOUGdseq4) by Rich Hickey(author of Clojure)





# Baby steps in Clojure

Pure functions don't change anything, have no side-effects. They just relate one set with another set, like a mathematical function. They connect some input with some output. If I give this input, I always get that output, guarantee. It doesn't also change something somewhere else, like the value of some variable.

But if my accounting software doesn't 'change' the account balance when I take money from it, how can I use the software?

So we'll have to make changes, have side-effects to have a tool that works.


Every functional language deals with states, side effects in a different way, I had learnt from Russ.

Skimming through the getting started section of Clojure, I'm starting to learn how Clojure deals with states, mutating states, etc. - Identity.

# Identity
Identity is "a stable logical entity associated with a series of different values over time".

Wow, I heard a similar thing from Alan Watts. Something like - we are like a whirlpool, like a knot moving across a rope - a identifiable pattern(stable, logical entity) that's always changing(a series of different values over time). It's not a cat on the mat. It's a catting on the matting!

Even when I thought I'll go ahead with Clojure, I wasn't fully sure if the language would have ideas at its core that I can connect with. Not saying, I'm awesome. But that I tend to like ideas that connect with the ideas around reality, nature of reality, nature of 'I', etc. 

"Identities are mental tools we use to superimpose continuity on a world which is constantly, functionally, creating new values of itself."

Wow. That's exactly how I these days perceive reality - how I, others, and other things exist out there.

Great start!

Will stop skimming and dive into this, but on another day.

# Wrapping up
That's it for today. I'm guessing I'll learn and build in Clojure little by little going forward.

Thanks for watching, uhm I mean, reading. 

Great day! 😊