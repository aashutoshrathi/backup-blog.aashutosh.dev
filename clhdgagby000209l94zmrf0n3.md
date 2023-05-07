---
title: "Nibble #6"
datePublished: Sun May 07 2023 13:29:27 GMT+0000 (Coordinated Universal Time)
cuid: clhdgagby000209l94zmrf0n3
slug: nibble-6
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1682755116423/035418a1-0129-48af-9909-8fad2c80dd6a.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1682755136351/46a75e97-58c5-4d1f-bdba-c8d001b8cc07.png
tags: ai, microservices, javascript, data-science, databases

---

🙏🏻 Namaste!  
Welcome to the #6 edition of Nibble.

We tweaked the banner a bit to make `1001` it more visible and also, and the `0`s were not nerdy enough, so now they are. 🥂

In our defense, this was a busy and lazy weekend, plus had the content of two Nibbles ready, so might publish the next earlier than expected.

Don't let your Monday blues get in the way of reading this completely. (*remember "pain is inevitable, but* ***suffering is optional***")

### News 🗞️

* Microsoft announced [**Clarity for Mobile apps**](https://learn.microsoft.com/en-us/clarity/mobile-sdk/) (*It's like LogRocket but for Mobile apps, if you think about it carefully, MS might capture your development stack soon*)
    
* [**Vercel announced Storages**](https://vercel.com/blog/vercel-storage)**,** they are offering serverless Redis, Postgres, and blob storage (S3-like) (*honestly, what a time to play this masterstroke, when Server Components are the center of buzz and Vercel leading the market of SSR, the only thing one needed was a hosted DB from somewhere else)*
    
    And guess what, they also have templates to use their DB for some use cases, for example, if you want to use Vercel PG as Vector DB, you can just one click deploy it using this template [**postgres-pgvector**](https://vercel.com/templates/next.js/postgres-pgvector)**.**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682959515697/b155790d-8fb9-4899-84e3-d9912c6f3442.png align="center")
    
* **😳** [**Geoffery Hinton**](https://en.wikipedia.org/wiki/Geoffrey_Hinton), the Godfather of AI, left Google after a decade & spoke out about the risks that advancements in AI bring in. \[[**Article**](https://www.reuters.com/technology/ai-pioneer-says-its-threat-world-may-be-more-urgent-than-climate-change-2023-05-05/)\] (*the news was all over the place all week, and people are now really afraid as one of the smartest people who made Neural Networks possible is afraid.*)
    
* 💔 Google said they won't share the advancements in AI with the public anymore. \[[**Full Article**](https://archive.ph/rUQxM)\] (*uf! Someone got hurt with the ChatGPT going live, but Google was the reason behind the genesis of Transformers, so overall bad for us.)*
    
* 📉 Oh! On that note, [Chegg](https://www.chegg.com/) got hurt badly with the rise of ChatGPT, but they have been trying to recover, by making the biggest enemy their friend. They announced [**CheggMate**](https://www.analyticsinsight.net/chegg-launches-its-gpt-4-compatible-cheggmate-learning-service/), GPT-4 powered solution so to help you cheat on homework.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1683461064530/197ea52d-f51a-4471-8151-1b87a14d8434.png align="center")
    
* Amazon Prime Video published [**a blog post**](https://www.primevideotech.com/video-streaming/scaling-up-the-prime-video-audio-video-monitoring-service-and-reducing-costs-by-90)**,** telling the world how they reduced the costs by 90% by moving from "microservices" to "monolith" architecture. As soon as the post dropped, everyone had a take on it, here are a few of the good ones.  
    \- [**Even Amazon can't make sense of Microservices**](https://world.hey.com/dhh/even-amazon-can-t-make-sense-of-serverless-or-microservices-59625580) by DHH  
    \- [**Serverless is a lie**](https://www.youtube.com/watch?v=qQk94CjRvIs) by Fireship  
    (*this could have been another "*[**tab vs spaces**](https://www.youtube.com/watch?v=SsoOG6ZeyUI)*" war, but this involves real money, so the only thing left to see is if organizations force their engineers to take out some bandwidth to move out of Microservices architecture if they can*)
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1683465304196/ebd888b3-2a58-4cf7-af71-fbf68a4894bb.png align="center")
    
* [**Modular announced Mojo**](https://www.modular.com/mojo)**,** a programming language that looks like Python and feels like C (*yes, blazing-fuckin-ly fast*). It is specifically built for developing more performant AI models. (*I got the early playground access, but haven't played yet. Reminds me of the Gym membership I got last year* 🫠)
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1683463405039/cba6afcf-869b-448b-8f5d-651ca2bff311.png align="center")
    
* Some insider from Google leaked a document stating "[**We don't have a MOAT, neither does OpenAI**](https://simonwillison.net/2023/May/4/no-moat/)" (*it's been 4 days full of MOAT meme posting, if you are unaware about this, go click on the article link, also the GIGA chads in the industry met the POTUS*)
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1683463663358/85ff1ed8-3f9b-4a07-a892-29703d06302a.png align="center")
    

### Wild World & Web 🫠

* You might know "लक्ष्मण रेखा", but have you ever heard of the "Wallace Line"?  
    \=&gt; There is a **32 km stretch of water** between Bali and Lombok Islands, which is indeed keeping the "worlds apart". The line is called [**Wallace Line**](https://education.nationalgeographic.org/resource/dividing-species-wallace-line-map/)**.** It is an imaginary line, on either side of which there is no similarity in bio-diversity and it is like an invisible barrier for animals and no one has ever crossed the line (*except for humans ofc)* \[[**Full Video by PBS Eon**](https://education.nationalgeographic.org/resource/dividing-species-wallace-line-map/)\]
    
* [**Mark Zuckerberg Wins Gold And Silver Medals In His First Jiu-Jitsu Tournament**](https://www.ndtv.com/feature/mark-zuckerberg-wins-gold-and-silver-medals-in-his-first-jiu-jitsu-tournament-see-pics-4012857) (*yes, the same guy, who testified like an LLM in front of Congress. For some reason, it's been a thing now, Tech Bros are going deep into fitness to name a few* [***Sam Altman,*** *reportedly deadlifts*](https://twitter.com/levelsio/status/1654455407916756992?s=20)*, Zuck is winning medals in Jiu-Jitsu, Bezos has been buffed up for a long time now &* [***Divyesh Puri***](https://divye.sh/) *has been a health and fitness enthusiast too*)
    

### Catch up 🤓

* 🙀 AutoGPT UI is coming - \[[**Join Waitlist**](https://news.agpt.co/)\] (*as long as you have enough money in savings, feel free to connect your OpenAI account to it*)
    
* 🔥 Move your servers to the "Edge" using [**Hono**](https://hono.dev/)**,** an ultrafast web framework for the Edge.
    
* You knew [**Whisper by OpenAI**](https://openai.com/research/whisper) now meet [**Whisper JAX**](https://huggingface.co/spaces/sanchit-gandhi/whisper-jax), the fastest Whipser model out there, 70x faster than the others. (*this brings me to the point, is there someone who has already built the Movie Audio to SRT file thing?*)
    
* Inflection AI release its own Chatbot called [**Pi**](https://heypi.com/talk)**.** They say that it's smart & supportive and you can talk out personal stuff with it.  
    (*The team behind Inflection has the industry’s top AI experts who previously worked at DeepMind, Google, OpenAI, and Meta. I tried to use the product, personally, it's doing good for early access*)
    
    ![Image](https://media.discordapp.net/attachments/1101550496726139042/1103789252883525755/image.png?width=1870&height=760 align="left")
    

### TILs 🤯

* You might have used the "*sweating guy*" meme, but do you know where it originated? \[[Key & Peele Clip](https://www.youtube.com/watch?v=cDdv7q4jtiY&t=6s)\]
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682879477285/7aba7904-5d59-40b0-a0fa-bf1d85ff96c1.gif align="center")
    
* 🗺️ Have you ever come across maps that have some places that don't exist?  
    Well, the detailed maps of the cities have such places and they make up some *random places or random names* so that they can later **check if someone plagiarised** their maps.  
    You can watch the detailed [**video**](https://www.youtube.com/watch?v=DeiATy-FfjI).
    
* WhatsApp Web has this cool option to blur the part of images, which you paste into it. (*it's been there for a while, but I never noticed it seems, and the answer to the msg in the screenshot is "****NO****" ofc.*)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1683460800895/0bcfc3ef-a12e-44d8-9478-4e04fcc0b886.png align="center")

### New in town 👀

* [**Query Kitty**](https://www.querykitty.com/) **\-** ChatGPT for the Impatient ones (*press the* **Ctrl+Right Arrow key** *anywhere and use the text prefixing it as prompt*)
    
* [**Hackercast**](https://camrobjones.com/hackercast/) **\-** An AI-generated podcast summary of Hacker News (*because why let folks like me read it from there and give you fine-grained content, instead go listen to 1-hour bot-generated podcasts*)
    
* [**Unitary**](https://www.unitary.ai/) **\-** AI-powered video content moderation
    
* [**Landing AI**](https://landing-ai.com/) - Now make kinda beautiful landing pages with just a prompt. (*RIP* 🪦 *Bootstrap template sellers*)
    

### Recommendations 💫

* [**Reflect**](https://reflect.app/) - An alternative to [**Obsidian**](https://obsidian.md/) with appealing UX (*at least on the landing page, from the first looks it feels like* Linux:MacOS :: Obsidian:Reflect, *but don't take my word for it, yet, go try it.*)
    
* Communication is hard, and it has become harder with the ever-evolving and remote job world. Here is one of many rules that I follow, it's "[Don't ask to ask, just ask](https://dontasktoask.com/)" (*also, always remember over-communicating professionally is okay, then under-communicating*)
    
* [**RegexGPT**](https://regexgpt.app/) - yet another tool for building out Regexes from plain text. (*I personally think we get it, LLMs can write better Regex than humans, and let's not make more such tools please?*)
    
* [**JamGPT**](https://jam.dev/?invite=631d06f3-d58a-4200-2705-26e158294736) - the Chrome Extension that allowed you to easily report bugs, now announced AI-powered bug solver (*screaming intensifies as I feel attacked with this one personally.*)
    

### Cool OSS Projects 🤌🏻

* [**alright-react-app**](https://github.com/DoneDeal0/alright-react-app) **\-** Tired of setting up React apps all by yourselves?  
    This CLI tool bootstraps the app with an exposed, unopinionated, high-perf config. w/ Jest, SWC, Storybook, TS5 & Webpack 5
    
* [**Internet in a box**](https://github.com/iiab/iiab) - It is a self-contained, offline version of the internet, with a lot of selected data in it, and it comes packed in a Raspberry Pi, which can be used as a hotspot to share access to these resources (*if you remember* [***Microsoft Encarta***](https://archive.org/details/microsoftencartapremiumedition2009) **🥹**, this is like 2023 version of that, with more data and better ways to share that and yes, FREE!)
    
* [**jsnes**](https://github.com/bfirsh/jsnes) - A NES Games emulator is written in JS. (*Atwood's Law in action*)
    
* [**shape-e**](https://github.com/openai/shap-e) **\-** Generate 3D objects conditioned on text or images (*It's like Dall-E but for 3D figures, and from the same org OpenAI*)
    
* [**AutoPR**](https://github.com/irgolic/AutoPR) **\-** a GitHub Action that autonomously writes a pull request in response to an issue! (*yes, it's time to pack bags and learn to farm!*)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682944532231/0978b373-4d8f-4ef2-be2c-b0e016b6d34c.gif align="center")

### Meme of the week

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682749844757/988028e4-bda8-411c-888d-17d802d165f3.png align="center")

### Ponder worthy words

> "Analysts are poorer forecasters than dart-throwing monkeys."  
> ~ Prof. **Philip Tetlock** (*he has legit research backing this statement*)

#### **Where do we stand in the year**?

▓▓▓▓▓▓▓▓░░░░░░░░░░ 33%

You can reach out to me using any of the links on the [website](https://aashutosh.dev/)  
👋🏻 See you at the next one!