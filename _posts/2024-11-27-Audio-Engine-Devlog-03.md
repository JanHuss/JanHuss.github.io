---
title: Honours Feasibility Demo [Devlog 03]
description: Working on the actual engine, structure and experiencing burnout
author: Jan
date: 2024-11-27
categories: [01. Audio Programming, Audio Engine Devlog]
tags: [game development, audio engine, honours, abertay, devlog, dsp, memory management]
---
# Repository link to project
---
[Audio Engine](https://github.com/JanHuss/maginEngineAudio)

# Overview
---
Hello hello! Welcome to Devlog 3! This is most likely the final blog of 2024. So much has happened and while reading you’ll understand why I need a well deserved break ^^
This post is about the so-called Feasibility Demo, a deadline to prove to my supervisor that I can complete my project in time by showcasing what I already have completed. 

# Feasibility Demo
---
The feasibility demo was the next step to submit after the Project Proposal. For this, we had 1 ½ months to provide “artefacts” of our project's progress. Some were mandatory artefacts and the others were supporting artefacts. 

## Mandatory artefacts
Mandatory artefacts included: 
- A Gantt chart of the timeline until April 28th displaying the tasks needing to be completed
  ![Gantt Chart](/assets/img/UMLs/Gantt.png){: width="200" .w-5 .left }<br>
- The research question of the project
- Any changes made to the project in terms of scope 
- A risk analysis form
- A risk assessment form (I know, you’d think they’d call one of them completely different)

## Supporting Artefacts
Supporting artefacts were slightly different. These were anything that would show progress to the project itself. Mine were:
- The repository of the project itself 
- A running application of the project in its current state
- A structure diagram of the project I would like to build
  ![Structure Diagram](/assets/img/UMLs/HonourStructureDiagramOld.png){: width="200" .w-5 .left }<br>
- A UML diagram showcasing that the structure diagram is not just pure insanity but actually thought through
  ![UML Diagram](/assets/img/UMLs/HonourUMLOld.png){: width="200" .w-5 .left }<br>

# The projects development
---
While developing, many things happened at the same time which ultimately led me to a full blown burnout that I could not get out of. More on that later. 
To develop the audio engine, I set up a repository on Github. That way I could work on any device on campus as well. I thought it would be wise to include a GUI for testing the application. In hindsight that was probably a waste of my time. I used the PortAudio library for loading audio and miniAud.io for playback, which also changed to removing PortAudio entirely. There were multiple reasons here. One, why not just use one playback and load header to understand how one thing works? Two, to avoid confusion. Three, the PortAudio .lib file was causing havoc on my repository, needing to be set up every time I pulled the repo onto a new device. The third point just drained my entire motivation every time I had to do that.
Removing PortAudio, really helped me boost my productivity and motivated me to go back on campus.

# Burnout
---
I think this is important to mention in its own section, not only because many developers or students can end up feeling this way, but I also need to explain how it happened and how I managed to pull through, in hope that others might benefit from this.

## How burnout happened
At the beginning of the term I was knee deep in Studio Catloaf related topics. Here, I already had to cut back on the programming side in order for me to work as both a producer and audio developer. You can already see that I was doing 3 jobs. Doing 2 jobs is already far too much but we’re a small company and one must work on multiple areas for the company to thrive. 
In year 3, I took on the responsibility as the student rep for my class and was asked at the beginning of the year if I wanted to continue this. It usually only involves introducing yourself as a rep to the class, taking notes of complaints or appraisals and then presenting these in a semi-annual meeting. That’s it. So I said yes. Of course, this had to be the year in which the Competitive Games Lab wanted to run a competition amongst courses and it had to be led by the reps. That still didn’t phase me at the time but it became a lingering thought. 
I was also offered a position as a laboratory assistant in the Audio Programming module I was going to study that year too. The reason for this was that I have a degree in Music Production and so know how digital audio and audio as a whole works. I was so excited about this that I said yes as well. I thought it to be a great opportunity to force myself to learn ahead of my peers, then explain it to them to ensure that I understood the topic myself. There was a whole thought there. Anyway…

So I was a student rep, a lab assistant, a student in his final year and a company director who is expected to work whenever possible. Just writing that makes me think: “Who takes on so much?”. For the first 4 weeks of term, I worked 7 days each week. Everything was going incredibly well. No hiccups at all. And in week 5, I struggled playing back audio in the audio programming lab, which threw everything off. I couldn’t explain to students how it worked and ended up in analysis paralysis for weeks. 

## How I dealt with it
Having had burnout before, I quickly pulled out of the student rep and lab assistant roles and told my colleagues that I need to reduce my workload. Everyone was incredibly supportive and I took the rest of the week off, fully aware that the burnout will not subside that easily.

In fact, I had to endure it for another 10 weeks until the final deadline was over. I couldn’t find focus which made me underperform in all areas of that term. It was a real shame as I only came to Dundee for that Audio Programming course in the first place and I couldn’t get the most out of it. 
There were many times that I considered deferring the course or even just graduating early seeing that I already have an honours degree. But I see every morning as a new opportunity to figure things out and so I sat down and just kept on going. That’s probably the best way to do it. I’m so close to the finish line, that it would be silly not to just keep on going! I talked to many lecturers who have been incredibly supportive, as have my peers. One lecturer said to me: “I know this might be difficult, but take a week off”. I already had taken that week off at the time so I couldn’t afford any more time away from my work but I know they meant it well.

## After submission
The evening of the final submission was very strange, I didn’t calm down for another 2 days actually. But when I did, my body wouldn’t even move. I was feeling it after leaving burnout untreated for so long. But it felt great! I took a good 2 weeks off at which point I started wanting to work on something so I did the occasional Leetcode problem.

# Conclusion
---
This post ended up being more about the burnout I experienced than the progression of my project. But my point here is that people need to look after themselves. Pushing yourself beyond limits is fine and needed at times but to do this consistently is incredibly unhealthy.
If you notice that someone might be struggling then ask them if they are alright. If you are the one struggling, then talk to people. It will lower the bar of expectations.

To finish off on a lighter note: The project is still ongoing. I am full of energy and am happy that I’m only one more term away before I can start working again! 

I wish you all a Merry Christmas and a Happy New year!

All the best,

Jan
