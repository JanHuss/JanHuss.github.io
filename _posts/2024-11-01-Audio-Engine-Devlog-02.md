---
title: Honours Project Proposal [Devlog 02]
description: Researching and writing up my ambitions for the honours project
author: Jan
date: 2024-10-16
categories: [01. Audio Programming, Audio Engine Devlog]
tags: [game development, audio engine, honours, abertay, devlog, dsp, memory management]
---
# Repository link to project
---
[Audio Engine](https://github.com/JanHuss/maginEngineAudio)


# Overview
---
So much for the “I’ll try and get a blog post done every Month” statement, haha. It’s only been 2 weeks and I have stuff to report! The project proposal was a total blur at times. Given only 2 weeks to complete this proposal document, I was incredibly focused and did not realise my surroundings that much.

# Project proposal
---
Straight after submitting the Project Idea, I was tasked to create a 2500 word document containing a proposal for my project's idea. This paper had to cover topics such as, what the idea was, why it should be researched and how I would go about researching it. 
I am not going to bother you with the intricacies of the paper but in short, I gave the following reasons:

## What: 
Build an audio engine that focuses on memory and CPU management to stay within a given budget.

## Why: 
I have heard the term “Budget” in different presentations and read about them in different articles and I find optimisation a fascinating problem solving topic. I am also working with FMOD for our Book of Abominations game and I would love it if we could use our own  personalised audio engine within the game. But even if we didn’t, I would find it really cool to be able to make use of my personal game projects. Lastly, I find that there is not a lot of information out there for people who are interested in audio programming, to get started. Therefore I would like to be one of these information sources once I get the hang of things.

## How: 
To get a broad understanding of the topic, I have watched many videos on audio engine structures such as this one here: 

{% include embed/youtube.html id='L4GuM15QOFE' %}

Seriously, if you haven’t seen this video, it’s amazing. 

I’ve also read and watched many books and videos from Guy Somberg, which is a great way to get the basics down. His books “Game audio programming” are fantastic for diving into a topic broadly and to help you find the right terminologies to further your research.

Here are links to his books:<br>
[Vol 1](https://www.amazon.co.uk/Game-Audio-Programming-Principles-Practices/dp/0367658348)<br>
[Vol 2](https://www.amazon.co.uk/dp/1032401796/ref=sspa_dk_hqp_detail_aax_0?psc=1&sp_csd=d2lkZ2V0TmFtZT1zcF9ocXBfc2hhcmVk)<br>
[Vol 3](https://www.amazon.co.uk/Game-Audio-Programming-Principles-Practices/dp/0367348047/ref=pd_sbs_strm_eu_t2_strm_cts_d_sccl_2_2/260-9523374-0217730?pd_rd_r=11962c49-7433-461a-a4e3-bd70a5ca7551&pd_rd_wg=0MXYY&pd_rd_w=q7ZD7&pd_rd_i=0367348047&psc=1)<br>
[Vol 4](https://www.amazon.co.uk/Game-Audio-Programming-Principles-Practices/dp/1032361077/ref=pd_sbs_strm_eu_t2_strm_cts_d_sccl_3_3/260-9523374-0217730?pd_rd_r=fe579c76-e5b8-4f53-ac77-459eb87a0bcb&pd_rd_wg=0gOmq&pd_rd_w=tCgQT&pd_rd_i=1032361077&psc=1)<br>

I have read parts of the books “[From Beep to Boom](https://www.amazon.co.uk/Beep-Boom-Development-Advanced-Engineering-ebook/dp/B07NF84K28/ref=sr_1_1?crid=2RH531J5NB28L&dib=eyJ2IjoiMSJ9.R_QyHA8ZT0Zxi12u-pS_5HK-GVWuf3lbEFl8shctJcNcnLY_M010E8ZZE935i8M0_ACtoyokf9k3ZvFHqlGO1e8QWG5YT_d1jAVrvBFf4WpD_cgLg1oHOIo4_IduHnk-.3cRVSvMv350n9BSKAUHxXisCMg3he5gvSk3L_NsEpgw&dib_tag=se&keywords=beep+to+boom&nsdOptOutParam=true&qid=1735999261&s=books&sprefix=beep+to+boom%2Cstripbooks%2C96&sr=1-1)” by Simon Goodwin and “[Game Engine Architecture](https://www.amazon.co.uk/Engine-Architecture-Third-Jason-Gregory/dp/1138035459/ref=sr_1_1?crid=1F1ENILRGTA72&dib=eyJ2IjoiMSJ9.Xttm-8wZxYABmWa4B3VZ33FeuYj3_-UyGDNcrMglq38bWueLrUc1OcIHtq7cUN3eAkeq61N03p8-ebjceYs3_o2xiJxhVVRITW4ziE8CtbTtfkbF0bP9_e3yEEFs6lXpTFqUJmevsG4SsecIgrjBklnY592gfFUkh_LIhnNM9Nx7q5xPGcPxyiJK1BmA0O_sti7jX50wcjDR6P9IYB3fzxKgtXYzOifru8x9hr1GaVo.SaOP7nV_bMo7c4PLIIRKGLXyTCkot2hVJSTR2oXir9w&dib_tag=se&keywords=game+engine+architecture&nsdOptOutParam=true&qid=1735999340&sprefix=game+engine+ar%2Caps%2C87&sr=8-1)” by Jason Gregory which have also been relevant.
All of this just to get a “Yes, you may continue your work” from the supervisor. 

# Conclusion
What I found most noticeable was that there wasn’t much information on how to actually get started in coding audio related projects. Of course I came across “[The Audio Programmer](https://www.theaudioprogrammer.com/)” and joined their discord but they are very “[Juce](https://juce.com/)” framework heavy which is too high level for my honours work. I will however go back to making use of Juce when the university year is complete. Otherwise, I found [PortAudio](https://www.portaudio.com/), a library good for loading data but not directly friendly for audio playback. So I looked for something that could playback audio as well and I found [miniaud.io](https://miniaud.io/) (<-- clever), a one header file that could playback multiple formats. 

And so my journey began… See you in the next blog! 
