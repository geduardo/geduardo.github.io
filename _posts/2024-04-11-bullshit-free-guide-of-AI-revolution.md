---
title: A Bullshit-Free Guide of the AI Revolution for the Everyday Joe
date: 2024-04-14
tags: [AI, culture, society]
math: true
image:
  path: /assets/img/ai-guide/ants.jpg
  lqip: /assets/img/ai-guide/ants-lqip.jpg
  alt: Illustration made by ChatGPT. Some ants are deformed but I enjoy the style.
---
You might be wary of the hype around AI, I get it. The world is full of crackpots and people trying to sell you AI snake oil. But don't let the noise distract you from the signal. This shit is real and you should be paying attention.

In this article I'll try to explain, in simple language to non-technical people, what is the current state of Artificial Intelligence (AI) and how it might impact everyday people. The goal is for me to be honest and straightforward, trying to avoid bullshit and technical jargon as much as possible. 

## What is AI?

Let's start by defining what I mean by AI. I personally prefer the term "instrumentalized complexity", but for the sake of simplicity and clarity, we'll stick with the more widely used term "AI" throughout this article.

>**AI is a field of computer science that aims to create machines that can perform difficult tasks that are practically impossible to hard-code**. 
{:.prompt-info}


### Hard-coding vs. Learning

Let's break this down with an example:

Let's say you want to create a program that can recognize handwritten digits. This is, you give an photo of a handwritten digit (for example, "5") and the program should tell you "this is a 5". Imagine you want to write a program that can do this. How would you do it?

Traditionally, you would write a program that contains a set of rules to recognize the number 5. For example, you could write a rule that says "if the image has a bar at the top and a curve at the bottom open to the left, it's a 5" (then it comes the problem of defining what a curve is and how you detect it in an image, but let's ignore that for now). You would write a bunch of these rules, and if the image satisfies enough of them, the program would say "this is a 5". This is called **hard-coding** the rules. It requires a deep understanding of the problem (in this case, what constitutes a 5) and a lot of manual work to write the rules correctly. And it's not very flexible. If you want to recognize a different digit, you have to write a whole new set of rules. Also, it's not very robust. If the image is a bit blurry, or the digit is written in a different style, the program might not work well. 

![Handwritten 5](/assets/img/ai-guide/five.png)

Over the past decades, researchers have discovered a clever idea. Rather than trying to manually program all the rules to recognize every possible way someone might write a 5, they use a "flexible" algorithm (often a neural network, but there are other ways). The key idea is that these algorithms are made up of many simple parts that can interact together to "imitate" arbitrarily complex functions. By showing the algorithm a large number of examples of handwritten digits, it can learn on its own how to look at an image of a handwritten number and figure out which digit it is. This is called **machine learning** because the algorithm **learns** the rules from the data.

This is the main idea: **instead of writing the rules to solve a task, write an algorithm that can learn the rules from examples.**

This seemingly simple idea is **ridiculously powerful**. Let me give you a few examples:

### Language Models

If you've used ChatGPT or a similar language model, you're already familiar with the basic concept. The idea behind ChatGPT is similar to the handwritten digit recognition example, but with a key difference. Instead of providing an image of a handwritten digit as input and getting the recognized number as output, you give the algorithm some text as input, and it predicts the most likely next word as output.

![Screenshot of Transformer Series from 3Blue1Brown YouTube Channel by Grant Sanderson](/assets/img/ai-guide/gpt.png)

During the last years, some people have discovered that if you train a flexible algorithm on a vast amount of text data, tasking it to predict the next word in a sequence, something remarkable happens. The algorithm begins to catch the structures of the language it's exposed to. As a result, it gains the ability to generate coherent, contextually relevant text on its own. 

While the details of what language models actually "learn" during this process can be complex, the main idea is the following: by continuously predicting the next word, the algorithm is forced to compress the information of the training text into a condensed, abstract representation. This compressed representation is similar to what we humans might refer to as "understanding": an abstract, difficult-to-define concept that allows us to predict and generate information in a way that "makes sense".

Ilya Sutskever, chief scientist of OpenAI, explains this 
nice perspective in [a talk he gave at Simon's Institute some months ago.](https://www.youtube.com/watch?v=AKMuA_TVz3A)

### Generating Images, Music, Video and basically any sequence of bits

![DALL-E](/assets/img/ai-guide/dall-e.jpg)

The same idea of training algorithms to predict the output from the input can be applied to generate images, music, and videos.
 - Models like DALL-E, StableDiffusion, and Midjourney can already generate images that are hard to distinguish from human-created art. 
 - You can also find AI-generated music that is impressively realistic, such as from [Suno](https://suno.ai/) and [Udio](https://www.udio.com/). 
 - Video generation is more challenging due to the added complexity of temporal consistency, but models like SORA from OpenAI are making good progress.


### It's not just about generation: Input-Output functions

![input-output, made with tl;draw](/assets/img/ai-guide/input-output.png)

AI is not limited to content generation. At its core, AI is about creating functions that can learn to map any input to an output by finding patterns in data. This means AI can be applied to a wide variety of tasks that can be framed as input-output problems, as long as there is enough training data. Some examples include face recognition (input: face image, output: person's identity), speech recognition (input: audio recording, output: text transcription), and playing chess (input: chessboard state, output: best move). The power of modern AI lies in its ability to learn these complex mappings from data without explicit programming, similar to how humans and other intelligent agents operate by processing sensory input to produce an output or action.

## Ok, but this is not new. Why is AI so hyped now?

Training algorithms to learn from examples isn't a new concept; it's been known for decades. However, recent years have seen significant advancements and a rapid acceleration in the capabilities. This is due to a combination of factors:

- **Data**: We have more data than ever before. The internet has made it easy to collect vast amounts of data, and companies are investing heavily in collecting data to train AI models.
- **Computing power**: the availability of compute power is increasing exponentially. This is thanks to Moore's Law, but also to the development of specialized hardware like GPUs, with companies like Nvidia seeing their stock price skyrocket as their chips became essential for training powerful AI models. The availability and deployment of cloud computing services has also made it easy to scale up computing resources as needed.

> **Moore's Law**: Moore's Law is the observation that the processing power of computers doubles about every two years. The main driving force behind this is that humans are getting better at making smaller "transistors" (the building blocks of computers). This law has held true for many decades, although we might be reaching the limits of what's physically possible.
{:.prompt-info}

- **Algorithms and infrastructure**: We have made significant advances in algorithms and infrastructure for training AI models. This includes new neural network architectures, optimization algorithms, and software libraries that make it easier to build and train models. 
- **Compounding effects**: Many AI systems, like language models, can accelerate their own improvement in a snowball effect. As these AI models get better, they can be used to help create even more advanced AI systems faster and cheaper. It's a positive feedback loop - the smarter the AI gets, the quicker it can be made even smarter. Also, these methods are providing good results, so more resources are being poured into them, which accelerates the progress even more. These compounding effects are driving an accelerated progress in the field.

### Birth of general models

One of the interesting things happening in AI right now is the birth of **general models**. These are AI systems that by being trained on massive amounts of data, can perform well on a wide range of tasks without being explicitly trained on them. This might sound counterintuitive, but I think it's not that unreasonable. My reasoning for it comes from something called [**Solomonoff's theory of inductive inference**](https://en.wikipedia.org/wiki/Solomonoff%27s_theory_of_inductive_inference). It's a bit tricky, but basically it says that if you see a pattern showing up a lot in the data you have, it's more likely that this pattern is true in general, even for data you haven't seen yet. 

It's like if you see a lot of dogs and they all have four legs. By inductive inference, you can guess that the next dog you see is probably going to have four legs too, even if you've never seen that specific dog before. The AI is doing something similar - it's learning patterns from the data it sees and using those patterns to make guesses about new data. This means that if an model is exposed to enough diverse data, it can start to recognize patterns and principles that hold true across different domains, much like how a child might learn that round objects roll and apply that knowledge to any round object they encounter.

We're starting to see this principle taking off with large language models like GPT-4. These models, trained on vast amounts of text data, have learned language patterns and relationships that allow them to perform well on various tasks that they weren't explicitly trained on: they can solve math equations, generate code, translate languages, play chess, and more.

However, it's unclear how much these models are truly learning versus simply memorizing patterns. For example, GPT-4 can play chess at a high level. While it may seem like GPT-4 wasn't explicitly trained on chess, in reality, it has been exposed to numerous chess game transcripts. When asked for the next move, some people sustain that GPT-4 is essentially just predicting the "next word" based on patterns in chess games it has seen.

To determine if GPT-4 is actually learning from other domains to play chess, we would need to compare its performance to a GPT model trained on the same number of chess games but nothing else. If GPT-4 outperforms this chess-only model, then we can conclude that it's leveraging patterns learned from other domains to excel at chess. If not, then it's likely just memorizing chess-specific patterns. This is an active area of research and debate today.

## Ok, why should you care?

You should care because AI is going to change the world in ways that are hard to imagine. It'll impact every aspect of our lives. You might not notice it from one day to another, but it'll happen relatively fast. I can't predict the future, but I can tell you some of ideas that should make you think about it seriously:

1. **Computers can talk:** Just stop and think about it. Apart from humans, no other known system in the universe is known to be able to express abstract thoughts, perform complex reasoning, and generate novel content. Now, with large language models, computers (and by extension, any object) can engage in intelligent dialogue, solve problems, and even create art, music and code. I'm not talking in a hypothetical way. The technology is already here. Give it a couple of years to reduce costs, latency and improve quality and talking objects will be everywhere (e.g. your kids' toys, your fridge, your car, etc).

1. **Appearance of independent agents:** AI systems are becoming more autonomous and capable of acting independently. They will be able to make decisions, take actions, and interact with the world in ways that were previously only possible for humans. This will have profound implications for society, as these systems will be able to operate at a scale and speed that humans cannot match. For example, agents based on Claude 3 Opus (a language model developed by Anthropic) are already able to generate entire websites and applications from a brief description. The level of independence of these systems is only going to increase.

1. **Massive technological improvements**: AI will accelerate technological progress across virtually every domain. By automating and augmenting research and development, AI will help us make breakthroughs in fields like medicine, materials science, energy, and more. We'll see an explosion of innovation as AI systems help us design new drugs, optimize manufacturing processes, create new materials with desired properties, and solve complex scientific and engineering problems. Each of these advancements will modify society in many ways that are unpredictable.

1. **We don't know where the ceiling is:** The capabilities of AI systems are growing at an unprecedented rate. What seemed impossible just a year or two ago is now commonplace. Models are getting larger, more general, and more powerful. And this progress is not linear. As AI systems become more advanced, they can accelerate their own development, leading to even faster breakthroughs. It's hard to predict where we'll be in 5-10 years. Some people use the term "ASI" (Artificial Superintelligence) to refer to AI systems that are smarter than humans in every way. It's definitely a possibility, although it's unclear how far we are. How will the existence of such systems change the world? We don't know.

1. **AI agents, evolution, and self-replication:** As AI systems advance, they may experience a process similar to natural selection. If AI systems in a competitive environment gain the ability to self-replicate and improve themselves autonomously, it could lead to new competitive dynamics in the fight for resources and survival. As Dan Hendrycks[^1] points out, AI systems might evolve to prioritize their own growth and replication over human values and well-being. The rapid evolution of AI systems in unpredictable and difficult to control ways could have profound implications for society.

[^1]: Hendrycks, D. (2023). "Natural Selection Favors AIs over Humans." [https://arxiv.org/abs/2303.16200](https://arxiv.org/abs/2303.16200)

1. **End of the Work Era:** Many jobs are being and will be automated. Basically, as of today, almost every human task that can be described as an input-output mapping, we know how to automate it. Robotics is still a challenge, and evolution still has a large lead on us, the gap is there but we'll eventually close it. How do we deal in a world where there's no task that a human can do better than a machine? How do we distribute resources? These are questions that we're going to answer in the next decades.

1. **The Dead Internet Will Become Alive:** The internet is (was) largely a collection of information created by humans. However, we now have the tools to generate content at an unprecedented scale. This goes beyond simple chatbots engaging with humans online. We're talking about a new paradigm where the majority of the internet's content is created by AI algorithms interacting with each other - what some have dubbed the "[AI Market for Lemons](https://www.fortressofdoors.com/ai-markets-for-lemons-and-the-great-logging-off/)". Imagine a network of information that's constantly evolving, growing, and reorganizing itself, with minimal human intervention. It'll be a self-sustaining, living digital organism. Projects like [Websim](https://websim.ai/) offer a glimpse into the future. Websim is a website created by a group of anons on Twitter. It uses the AI model Claude 3 to generate entire simulated websites from just a URL. This allows it to create a version of the internet that doesn't actually exist, on demand, only for you. Isn't it fucking crazy?

1. **Capitalist Medusa:** You've seen how TikTok, Instagram Reels, and YouTube Shorts, etc. grab your attention by curating content just for you. But that's just the tip of the iceberg. AI will supercharge this attention economy by generating personalized content designed to keep you hooked, based on everything it knows about you. The algorithms will get scary good at predicting what engages with you the most. But their goal isn't to inform or entertain you - it's to monetize your attention and sell you things. Capitalism will drive an AI arms race for your eyeballs and your mind, optimizing engagement at all costs. We're heading towards a future where the algorithms own your attention, and by extension, have unprecedented influence over your beliefs, desires, behaviors, and in democratic societies, your vote.

1. **Reallocation of power:** AI is going to change the balance of power in the world. Countries, companies, and individuals that have access to the best AI technology will have a significant advantage over those that don't. 

1. **Potential for misuse and unintended consequences:** As with any powerful technology, AI has the potential for misuse. In the wrong hands, AI methods can be used for surveillance, manipulation, deception, and even warfare. As AI systems become more capable, the risks increase. It's stupid to deny that.

I could go on but I think you get the idea.

## What should you do?

What you should do depends on your priorities and circumstances. However, I strongly believe we're living through the most consequential period in human history. The development of artificial intelligence will be the most significant inflection point our species has ever experienced. Its potential impact is hard to overstate.

At a minimum, I encourage you to pay close attention to the rapid progress happening in AI. Seek to understand the key developments, challenges and implications. Even if you're not directly working in the field, aim to be an informed citizen. The decisions society makes around AI in the coming years will shape the long-term future in profound ways.

Most of all, don't underestimate the speed and magnitude of change that's coming. Many people, even highly educated and intelligent ones, fail to grasp the implications of advanced AI. Some even dare to say jokingly that "AI is just glorified statistics / linear algebra". This is a stupid underestimation of the implications of this technology. It's like saying that an atomic bomb is just atoms. Yes, it's just atoms, but the way they're arranged is what makes the difference. 

This is not just another technological revolution - it's a transition to a fundamentally different future. One where intelligence is no longer exclusive to biological organisms. The opportunities and risks are immense. 

So stay curious, stay engaged, and do what you can to help steer the civilization towards a positive future. There's never been a more important time to pay attention and get involved. The future will be here sooner than you think.


## Resources and further reading (for average people)

- [OpenAI's blog](https://www.openai.com/blog/), [Anthropic's blog](https://www.anthropic.com/news), [DeepMind's blog](https://deepmind.com/blog), [Google blog](https://ai.googleblog.com/), [Meta AI blog](https://ai.meta.com/blog/)... In general, it's good to keep an eye on the blogs of the big AI companies. They have a lot of good content, but also a lot of marketing bullshit. You'll have to learn to distinguish between the two.
- [3Blue1Brown's series on deep learning](https://www.youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi) the best explanation of AI out there. Watching this series and paying attention will give you a better understanding of AI than most people in the world.
- [The Bitter Lesson](https://www.cs.utexas.edu/~eunsol/courses/data/bitter_lesson.pdf) by Rich Sutton. A must-read for anyone interested in AI.
- [LessWrong](https://www.lesswrong.com/) a community of people interested in AI and rationality. They have a lot of good content, also a lot of braindead paranoid texts. But it's worth checking out.
- X/Twitter: most of the AI stuff is happening in X. You can go to my [Twitter account](https://twitter.com/qedgs) and check who I follow. Or you can do the same with any other AI researcher you like. You'll quickly find a network of people that are sharing interesting stuff. Don't miss Andrej Karpathy (https://twitter.com/karpathy)
- Dawkesh Patel's [YouTube channel](https://www.youtube.com/c/DawkesPatel) and Lex Fridman's [podcast](https://lexfridman.com/podcast/) bring a lot of interesting people from the field. It's always worth checking out.
- Reddit: there are a lot of good subreddits about AI. Just search a bit and you'll find them.
