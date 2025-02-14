---
title: Programmers, Will AI Work For You, With You, or Without You?
description: A thought experiment on the roles AI can play in software development.
tags: [ai, programming]
authors: yiming
date: 2024-10-14
image: ./cover.png
---

# Programmers, Will AI Work For You, With You, or Without You?

![Cover Image](cover.png)
> **"Programming is dead."**

A friend said so when he heard I was working on dev tools. It was right after LLM’s coding abilities shocked the world. He felt it pointless to continue building tools for human programmers anymore when AI is taking over this profession. You'll never be wrong by predicting without attaching a time frame. Dead when? At least for the time being, the emergence of generative AI has introduced more work for programmers, some more difficult than before.

Whether AI will replace human developers is too big a topic to tackle. However, we can keep an open mind and explore different roles that AI can play in software development. Let's conduct thought experiments to imagine what each means to us.
<!--truncate-->

## Coding Copilot

We all love GitHub Copilot. There’s absolutely zero learning curve. Your IDE suddenly gets 10x smarter and generates code snippet completions as you type. It’s fast. It’s context-aware. It keeps you in the flow by letting you stay inside the IDE. 

The quality is pretty good. Far from perfect, but the tolerance in this scenario is also pretty high. Who doesn’t enjoy some free code written for? Even if it’s not 100% correct, it can still be a good starting point. Otherwise, you’ll go to StackOverflow and grab something there anyway, won’t you?

A Copilot works **FOR** developers. It’s a tool, but a very smart one. It’s fully at your disposal, and its entire goal is to make you more productive. You, the human programmer, are the pilot. This brings several implications:

1. All prior wisdom generated by humans for humans continues to be valid and important — writing readable code, using design patterns to combat complexity, planning for the future, etc. Eventually, they are used to overcome humans' limited capacity for comprehension, memory, and consistency.
   
2. Languages, frameworks, and libraries will continue to be created and evolve as they are today. Made by humans for humans, these tools are the actualization of wisdom mentioned in #1. Contrary to what laymen may expect, the top priority of these tools is not generating powerful and performant applications but lowering programmers' mental load. DX will continue to be one of the most essential topics in the industry.
   
3. Following #1 and #2, such AI Copilot must adapt well to whatever tools the human programmer has chosen to use. It must serve him by creating code that not only works but is also "good" by human standards. Preferably, the code should have a consistent style as those manually written.

Copilots like GitHub Copilot, Codeium, and Cursor have proven very useful. However, they are certainly not the kind of disruptive innovation the crowd anticipates.

What's next?

## Buddy Developer

Although routines are the primary unit developers organize and work on their code, they usually think at a higher granularity — feature. Features have business meanings, making them a good fit for planning, communication, and delivery. They’re also the ideal unit for breaking work down and distributing it among team members.

Naturally, AI's more ambitious goal is to tackle feature development directly.

You play a product manager or team leader role in such a setup. The AI works **WITH** you. It takes requirements from you, employs its own thoughts to generate an implementation strategy, and eventually comes up with code that contains the feature and integrates seamlessly into the project's code base. Instead of prompting with code or comments, as when you use Copilot, you prompt your AI buddy with requirements in natural language, optionally complemented by other high-level artifacts like a flow chart.

This poses some very tough challenges. One obvious problem is that humans are terribly incapable of describing things precisely.

> Wife: buy a watermelon on your way home. If you see tomatoes, buy two.
>
> Q: how many watermelons should the husband buy if he sees tomatoes?
> 

Humans are even worse at precisely understanding other people’s thoughts. So when we work with our AI buddy, we can have these desperate struggles:

- Have I explained enough of my needs to the AI?
- Does the execution plan generated by the AI (most AIs take a "plan-then-write" approach) show that it’ll actually cover everything I need?

Of course, the ultimate guarantee is to review every line of code the AI writes thoroughly, but our expectations should be higher than that. When humans see ambiguity, we resort to common sense. If a pair of communicators share a "common" common sense, they’re likely to be on the same page. That's why a team gets more efficient after working together for an extended period of time. LLMs are already amazingly good at capturing common sense (albeit with a brute-force approach). As they get even better in the future, we can probably have enough confidence that we’re actually talking to a reasonable person.

Another bigger question is whether LLMs are powerful enough to implement features. Today’s LLMs have extremely tight context size limits. Unlike Copilots, which work at the code snippet level, feature-building AIs need a ton of context, often a big portion of the entire code base, and maybe access the code change history to understand why something currently works the way it does. Also, generating large chunks of code is computation-intensive, which can be rather slow and prohibitively expensive.

Of course, we can wait for LLMs to get much stronger or employ techniques like CoT to mitigate the problem, but another parallel solution is probably to adapt our project setup to help AIs do a better job. Use more high-level programming languages (including DSLs), do more declarative coding, make APIs more succinct, and employ more pre-built components so that AIs don’t need to generate from scratch. Basically, just try programming at a higher abstraction level and write less code. Just think about it: how much difference will it make if AI codes against a well-designed ORM API vs. generating SQL directly to access the database? A higher level of abstraction reduces AI’s cognition and generation load, and thus less chance of hallucination. 

The benefits are also mutual. If AI generates higher-level code, you’ll also have a much easier time comprehending it, validating it, and making changes to it as necessary.

Feature-building AI is still in its very early stages. Products like [Cursor Composer](https://youtu.be/V9_RzjqCXP8), [Marblism](https://www.marblism.com/), and [Replit Agent](https://docs.replit.com/replitai/agent) are having a good head start. For such products to succeed, a solid long-term partnership needs to form between humans and AI. It requires finding the right compromise (languages, frameworks, libraries, etc.) that allows both humans and AI to work effectively.

## Fully Autonomous Software Engineer

> We even tried giving Devin real jobs on Upwork and it could do those too!
— [Introducing Devin, Cognition AI](https://www.cognition.ai/blog/introducing-devin#:~:text=We%20even%20tried%20giving%20Devin%20real%20jobs%20on%20Upwork%20and%20it%20could%20do%20those%20too!)
> 

I’m not sure how true the story is, as it mentioned no details about what kind of jobs were done, how many times they were done, the success rate, how satisfied the customers were, etc.

The ultimate form of AI-assisted programming will be fully autonomous programming agents. It requires no supervision from professional software engineers, takes requirements directly from non-technical stakeholders, and delivers systems end to end. From a developer’s perspective, the AI works **WITHOUT** us! Or, in more brutal words, it replaces us. Instead of hiring an IT team, a non-tech-savvy company may purchase AI computation power to build and host the business applications they need. 

It can have some very interesting implications:

1. How the application is built can be a complete black box. This is what happens inside an organization when the IT department delivers an app to a business team. The demanding party doesn’t care and can’t understand how it works internally.
   
2. Given #1, AI can implement the system as straightforwardly as it sees fit. There’s no more restraint on writing code that humans can understand and change. There’s no need to follow best practices designed to mitigate human weakness. Duplicated code? Not a problem as long as it makes sure when a change is needed, all duplicates are consistently updated. SOLID principles? No more relevant. What humans see as shitty code can be perfectly fine for AI.

If we pursue this direction, it'll make sense to design languages and building blocks that maximize LLM's performance. AI programming and human programming would become two distinct worlds. Is it utopia or dystopia? I’m not sure. Fortunately, after a two-year cooling down, we know today’s AI is still extremely limited. A full-scale replacement of human developers is not coming any time soon.

## Final Thoughts

The future is very uncertain. But what’s certain is that software developers are among the first cohort to benefit from AI. We will also be the first group of people who struggle with it. Anyone who seriously integrated LLM into a product knows how frustrating it is to program against it — it’s restricted, unstable, slow, and hallucinating all the time. It's an API that requires us to think very differently. If old-days APIs are like Newtonian physics, LLMs are quantum mechanics — no more determinism, everything is probabilistic.

It’s too early to worry about being replaced by AI programmers. What’s imminent is to learn how to combat its weakness. Regardless of its immaturity, Generative AI is undoubtedly the most promising key to unlocking an exciting future.
