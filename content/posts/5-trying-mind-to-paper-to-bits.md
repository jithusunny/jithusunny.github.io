+++
title = '#5 Mindstream -> Paper -> Bits'
date = 2024-06-16T20:21:28+05:30
draft = false
+++

## Summary
- Streamed thoughts about how to proceed with the project onto paper - 5 sheets.
- Transcribed them (converted to text) with the help of ChatGPT.
- Edited a little bit, fixed a few errors, added headings, etc.
- **Too long; maybe don't read!**


## Okay, my mind says:

I will start off writing what I thought last: **"keep moving."**

Because my father and mother are both teachers... Wait a minute, not because they are teachers, maybe because of their teaching style... Hmm, now when I think about it, it's not just in teaching, it's a general psychological thing - "Pointing out mistakes, imperfections, flaws, etc."

So, mostly because of my upbringing, analyzing thoroughly and spotting mistakes is an easy thing for me to do. As a side note, I must also be the biggest victim of this hyper-analytic, scrutinizing, spell-checking, grammar-checking mindset/pattern.

This is not a completely sad picture if you felt I meant that. I have also benefited from this pattern a lot. In the end, it's not good/bad. These thoughts remind me of the Chinese Farmer's story I heard from Alan Watts. 🧘‍♂️

All these words took a lot of time to be transferred from my mind onto this paper. There are many (thought) directions I simply refuse to go, or I would take forever. What I was trying to say is: **"If we analyze/think too much, we'll get stuck. Keep moving."**

If you play a wrong note, make a grammatical mistake, or say something that didn't come out like how you imagined - It's okay. Acknowledge it if you want in a graceful, funny way. And just keep going. Making mistakes is a sign of movement. It's good.

OMG, too much preaching. These are thoughts from my mind; I'm just reporting them. Not really advice for the reader! 😊

## Come back to Zuperb

Now, coming to the thing I wanted to explore today in Zuperb.

Zuperb is alive. Its heart beats, it breathes, it may even have offspring 😛 Currently, Zuperb is just a couple of HTML pages on a computer with a name - zuperb.in. That is not so much fun. But let's start where we are.

Another side note, the above reminded me of my friend's blog post: [The Beginning by Arjun Sreedharan](https://arjunsreedharan.org/post/45904009462/the-beginning)

Let me explore what I mean by Zuperb is alive. The fact that somebody visited Zuperb is noteworthy. Let's take note of it. Zuperb must be conscious of it, maybe acknowledge that somehow.

One thing that comes to my mind is the 'site counter' thing I have on my Blogspot blog. It was for me to know and show how popular my site is getting. Zuperb is also about showing, though my attitude around 'the show' has changed. Now it is more wishy-washy like 'All this is Leela', 'a divine play', etc. That's fine.

Counting and showing some numbers is just a minor first step. It's the beginning of an interesting trail. Zuperb needs to have the ability to understand who he/she/it is with as if it is alive. Not to push some ad, get personal info to sell, etc. Only to serve, show better. Maybe, Zuperb can:

- avoid showing something not useful to the visitor.
- automatically translate content to the visitor's language/local.
- automatically decide and use the verbosity/volume of text/content, etc.

The last line is about an idea I got about writings primarily. Later on, we can adapt it for any kind of content. Something like **'responsiveness for content'**.



## Nice idea, but getting stuck? 🤔

I can go on and on about cool ideas and new systems that we can/will build. But I'm sensing that there's a danger in this. Like many previous times, this may also end up as all talk, no action.

Let's try to now **do something**, enough of talking.

**Show, don't tell** - [Pramode Sir](https://pramode.net/) taught me. Let me see if I can do something and show.

Well, I need to talk. Because my current mode of operation is to write down thoughts and do. This is like my log. It's a record of what I've been through, what was done, motivation, etc.

## We need a webapp 🌐

Zuperb can now speak to the world through posts. Next, we might want to add the ability to know these:

1. How many visits on Zuperb?
2. How - at what times?
3. From where in the world?
4. Through what device?

We'll need some code in the posts that gets this data, sends it to a backend server, and stores it in a database.

This sounds like re-inventing the wheel. But I'm very hesitant to add external dependencies. Let's keep things as simple, efficient, and straightforward as possible. Zuperb is not just another blog. What it will grow into only God knows! 🙏

So, I want to keep things simple, have a lot of control over the data storage, logic, presentation, etc.

In short, the next breadcrumb is **building a webapp**. 


## Okay, proceeding with the webapp 🚀

This is not easy - can't finish it quickly. What I will do is continue writing in Hugo, hosting on GH pages until I build a basic web application. In this webapp, I can put my thoughts like this post, others can read them, etc. Also, we will start building some self-awareness into the system - like how many people visited, read, reacted, commented, what the system is about, its values (!), etc.

What's doable today? 🤔  
It's 9:35 PM. I've a hard stop at 10 PM.

A basic webapp will need:

- A backend
- A database
- A frontend

NestJS is what I use at work to build web app backends. It comes with a file/module structure that we can follow, and things will just work. Flask is another option I considered. Python's readability is great. Which way to go?
Pausing and thinking can also be spontaneous 🧘‍♂️

I need to keep moving. But remember Alan Watts recollecting a moment he had with Suzuki or some great Zen master. Spontaneity is said to be a distinct characteristic of Zen. The masters of Zen are expected to flow, not get stuck. But when thinking is needed - you can sit and think. When asked about something that needed some thinking this particular Zen master took almost a full minute to think, collect his thoughts and start speaking.

I started writing about the importance of not getting stuck and moving. Though it looks like I’m flowing and not getting stuck, I feel I’m moving in circles. I’m stuck on Flask vs. NestJS.

Wait a min, I had this other great(?) idea of building it in both.

- Backend instance #1: Flask
- Backend instance #2: NestJS

Since I can’t make up my mind to pick one, I’ll do it in both. I’ll start with Nest because that is what I recently worked on. So I can move quickly and build things. But I’ll also build a version in Flask. Or FastAPI. More about this line of thinking later.


## Aim 🎯

- Basic UI to add posts in plaintext and view them.
- API to get/insert/edit post.
- DB: table to store the post.

## Time’s Up ⏰

It’s 10:10 PM. I’d love to continue. But sleep’s more important. After all, we’re awake and doing all we do to get a good sleep in the end. __‘Innit?__

So I’ll get this transcribed to digital text by ChatGPT tomorrow & publish.

Good day! 🌙

__[This was June 14 night, but finally got posted at June 16 night]__