---
title: "Nibble #4"
seoTitle: "Nibble #4 | aashutosh.dev"
seoDescription: "Node 20, TS 5.1 Beta, GPTCache, Null Island and more"
datePublished: Sun Apr 23 2023 14:44:06 GMT+0000 (Coordinated Universal Time)
cuid: clgtisj40000009ms1b6a0ydc
slug: nibble-4
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1681852077078/2515b023-4d74-4c11-8a12-f50ab7f1c614.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1682261000182/ffe4c5e2-6a23-4654-8227-b6db9bdd44bc.png
tags: web-development, reading, oss, gpt-3, openai

---

👋🏻 Hola! Welcome to the #4 edition of Nibble.

### News 🗞️

* ✨ Reddit will begin charging for their scraping APIs - \[[Article](https://techcrunch.com/2023/04/18/reddit-will-begin-charging-for-access-to-its-api/)\]
    
* 🚀 **NodeJS 20.0** is out - \[[Release Notes](https://nodejs.org/en/blog/announcements/v20-release-announce)\] (*this time they call it "Iron", so should be tough to break now, IYKWIM*)
    
* [Google Brain and DeepMind join forces](https://www.deepmind.com/blog/announcing-google-deepmind) to solve the biggest challenges facing humanity. (it \*seems like an alpha-\****bet*** *to beat OpenAI in this race, not sure about the challenges facing humanity, but force sure it can solve the challenges facing existing of Google*)
    
* [Stability AI](https://stability.ai/) launches Language Models [StableLM](https://github.com/Stability-AI/StableLM), and the good news is that you can dig up the repo and deploy your own server. (*You can go ahead and play with* [StableLM-Tuned-Alpha-7b Chat](https://huggingface.co/spaces/stabilityai/stablelm-tuned-alpha-chat) *that they release recently, it's not decent-ish yet, I mean OpenAI has set the bar too high for Chat Models*)
    
* [TypeScript 5.1](https://devblogs.microsoft.com/typescript/announcing-typescript-5-1-beta/) Beta is out (\*they have loosened up some rules, and optimized it as always so that you have RAM left for VS Code and Chrome & breaking changes are "\***ES2020 and Node.js 14.17**" *are minimum requirements*)
    
* Kent Beck, OG behind Agile Manifesto and TDD [worries a little about AI advancements](https://tidyfirst.substack.com/p/90-of-my-skills-are-now-worth-0) and their effect on Software Industry but concludes that you shouldn't worry as it can't replace our stupid human mistakes 😌.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682259160169/d497f6d7-9299-46b2-a1d3-c11b12dccab7.png align="center")
    

### Wild World & Web 🫠

* 🏝️ You have been to this island a ton of times, but it doesn't exist, [Null Island](https://www.atlasobscura.com/articles/null-island-is-one-of-the-most-visited-places-on-earth-too-bad-it-doesnt-exist) (*TLDR; it is a fictional place that is located at the coordinates 0°N, 0°E. Since* `null` *is* `0` *in most programming languages and* `0` *is the placeholder/default location, so all errors or missing locations point to this.*)
    
    ![Welcome to Null Island, where lost data goes to die - Big Think](https://bigthink.com/wp-content/uploads/2022/03/Google-Earth-Ruland-Kolen.png?w=1497 align="left")
    
* [19k new undersea volcanoes were discovered](https://www.science.org/content/article/it-s-just-mind-boggling-more-19-000-undersea-volcanoes-discovered), making it a total of more than ~43k. ()
    
* ♾️ Don't know what to read, but want to scroll through some good content over the web, well [WikiScroll](https://wikiscroll.blankenship.io/), brings infinite scrollable Wikipedia for you. (*if you are going to this site, there is seriously something troubling with you, get yourself checked, thanks!*)
    

### Catch up 🤓

* 😶‍🌫️ [**How to train your own LLM**](https://blog.replit.com/llm-training?ck_subscriber_id=1652259708)**,** a guide by Replit.
    
* Cool folks at [ui.dev](https://ui.dev/) have created a ***visual learning to React*** guide and bought a really expensive domain [react.gg](https://react.gg/)
    
* Codeium says out loud that "[Copilot spits out GPL code](https://codeium.com/blog/copilot-trains-on-gpl-codeium-does-not)", while Codeium doesn't. (*Basically, folks at Codeium say that we don't train over non-permissive code, hence we don't generate that code.*)
    

### TILs 🤯

* [Collective effervescence](https://en.wikipedia.org/wiki/Collective_effervescence) is an eye-catching name for the magic of shared experience and moving in unison.
    
    ![Collective effervescence illustration: two people hold their phones up as lights with 1000s of others in a stadium concert at night](https://ci5.googleusercontent.com/proxy/5wznL7UvC7-hkYS_kFTaj0-vzjk8DTI4qqSjKttupK7z0qrbaXLWEQmwLNaNed09sWtjNPqxXo_qNwbx2S0p-Bt-Psg3qmtSXBGFoYTLkAmZaiJVYD4OhrAbpamRc3er9vgMOcSmq9mhO7i8b4oA4NQHsUQ583apIe7vY2zFO509aseDsyyIAnvBv9VMcmAqECXSkIgsgnYsJBOT92ZhIxmPhibJLJnogcrITgHGWblcm6c=s0-d-e1-ft#https://images.prismic.io/sketchplanations/00f79e4c-a5e6-4c54-b785-456c330f299e_SP+818+-+Collective+effervescence.png?auto=compress%2Cformat&fit=max&w=992&q=50 align="left")
    
* 📧 You can **email yourself from Google Sheets** \[[Post](https://blog.bettersheets.co/simply-email-yourself-from-a-google-sheet/)\] (*we have had long chats on the internet about how half the software is just replacing the spreadsheets, but with LLMs and Plugins, the things that spreadsheets can't do is also reducing every day. Beware YC Startups!*)
    

### New in town 👀

* **🎤** [**Murf.ai**](https://murf.ai/) - Go from text to speech with a versatile AI voice generator
    
* **🧑‍🍳** [**littlecook**](https://littlecook.io/) **\-** Turn unused ingredients into delicious new dishes (*I feel a little sad on this one, wanted to hack something like this last weekend, but now happy, as I can now use this and save some time*)
    
* 🪟 [WindowAI](https://windowai.io/) - Use your own AI models on the web
    
* 🥹 [Multi-ON](https://www.multion.ai/) - A ChatGPT Plugin that can browse the web for you
    
* 🧙🏻‍♂️ [Mage](https://www.mage.space/) - An easy-to-use platform with Text2Img, Img2Img, and Text2Gif with 50+ models to choose from, Stable Diffusion being free.
    
* "Sitting is the new smoking," they say, and a few other philosophy razors in a Twitter [thread](https://twitter.com/george__mack/status/1649835213982408704?t=D90fYvYWhFvuCJCQC4xFmw&s=19) 🧵
    

### Playgrounds 🛝

* [AI Playground by Vercel](https://play.vercel.ai/) - A single place to test a lot of LLMs at once with a single prompt.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682253841330/b0d1baee-c356-4ddf-bc64-731841b2cc18.png align="center")
    
* [integer.exposed](https://integer.exposed/#0x002a) - a playground by [b0rk](https://twitter.com/b0rk), that lets you play around with different operations that you can perform on an integer like signed/unsigned left/right shift, byte order swap, and not.
    

### Recommendations 💫

* 🔎 [Magic Copy](https://github.com/kevmo314/magic-copy) - Remember how we talked about [SAM](https://segment-anything.com/) by Meta in the last two newsletters, well, this brings the power of SAM to your browser using a Chrome Extension. (*I tried to demo it, and it works like a charm and with very good precision, attaching a small video of the same*)
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682107739610/516cef03-f930-4ef2-a41f-799faebaf4db.gif align="center")
    
* [Centered](https://www.centered.app/download) - an app that helps you achieve a flow state and get the task done. It has coaches and spaces, where you will be pinged in the voice of the Space manager (*in my case* [*cassidoo*](https://cassidoo.co/))
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682257955211/0f53705e-d4d6-49ce-999a-ff074233e344.png align="center")
    

### Cool OSS Projects 🤌🏻

* [onionshare](https://github.com/onionshare/onionshare) - a tool that lets you securely and anonymously share files, host websites, and chat with friends using the Tor network.
    
* [GPTCache](https://github.com/zilliztech/GPTCache) - a library for creating a semantic cache to store responses from LLM queries. (*In easy words, it tries to group the queries that are similar in the same bucket and cache the response for it, saving us the response time and money*)
    
* [ocr-space-api-wrapper](https://www.npmjs.com/package/ocr-space-api-wrapper) - a quick way to extract text from an image or PDF, use OCR Space API wrapper with a free API key from [OCR Space](http://ocr.space/OCRAPI) (*No Stable Diffusion, pure OCR, yes a tech from the late 1900s*)
    

### Shoutout

* [Pixxel](https://www.pixxel.space/) - In the world where software is eating the world, these guys are launching hyperspectral small satellites to capture beautiful pictures of Mother Earth. They are basically building a health monitoring tool for the planet. (*these folks are building this cool stuff, right here, in Indiranagar, namma BLR*)
    
* [Julia Evans](https://jvns.ca/) (aka [@b0rk](https://twitter.com/b0rk)) - a software developer, who deeply understands the CS concepts and reflects them in her zines. You can check the awesome content (playgrounds, zines, and blogs) she creates [here](https://jvns.ca/)
    

### Meme of the week

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682259920642/4035b4a5-d97f-49ac-9b82-6dfd5b48903f.png align="center")

### Ponder worthy words

> **Atreus**: Who would reject the flood of fortune's gift?  
> **Thyesters**: Anyone who has experienced how easily they flow back.  
> ~ Seneca, Thysestes, 536

### Things I have been up to

* Went to an amazing event hosted by [**Bangalore Chess Club**](https://twitter.com/Blr_ChessClub)**,** and lost to some 8-year-old prodigies. 🥹
    
* Reading
    
    * [The Daily Stoic](https://www.goodreads.com/en/book/show/29093292) as a Daily Driver. (*yes, a self-help book* 😭)
        
    * [Sapiens](https://www.ynharari.com/book/sapiens-2/) - consuming slowly.
        

### **Where do we stand in the year**?

▓▓▓▓▓▓▓▓░░░░░░░░░░░ 31%

### **Note 👋🏻**

You can reach out to me using any of the links on the [website](https://aashutosh.dev/).  
*If you find any mistakes in this edition, blame the* [*reviewer*](https://www.thepushkarp.com/)*, he was busy moving out today.*

👋🏻 See you at the next one!