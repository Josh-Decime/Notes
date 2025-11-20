# 11/19/2025
I decided I’m going to start another VR project. I installed Unity, it was having some installation issues & I had to retry several times but it's finally installed. I don't have time to start the project today.

# 11/13/2025
Today I just made some minor adjustments to the readme. I’m considering starting another project now that seance is working well. Digging into it is going to be really time consuming & I already got it working well. I would learn a lot going through it but with how little time I have each day I likely wouldn't find any changes within the time I have. I could just do notes explaining what I learn each day & that would be something. But also, I am just ready to move on to something else. This project was fun & a great learning experience but there are many other things I want to build!

# 11/12/2025
After reviewing the verbose logs from running seance –wide I can see that it is getting everything it needs to answer the question correctly. I thought that it was, because it was referencing those files, but I have now confirmed it received everything it needed to answer. So the issue isn’t with BM25 this time, it is my LLM for certain. So anyone using a stronger LLM should get the correct answer since the answer was extracted from the code by BM25. I tried to see if maybe it just answered too soon without going through all the files provided, so I gave explicit instructions to read all of the files provided & that didn't change the result. 

# 11/11/2025
It seemed like my small LLM is getting overwhelmed by the context provided by –wide. So it can't provide the full, correct, answer. I reduced the context to see if that would fix it but unfortunately it is not reaching the correct answer still. 

# 11/10/2025
A little understanding goes a long way! You really can't leave it up to AI to troubleshoot in its current state, but if you know what you're doing it can be so helpful! It now boosts the token value of words with symbols before running BM25 & the answers it was providing to my test questions were so much better! –deep & –wide are now essentially fixed & could just use some minor finetuning. 

# 11/9/2025
Now that I’m finally starting to recover from that horrendous sickness I’m beginning to look more closely at how seance is functioning. While sick & on a time crunch I let AI lead the way on this. I wasn't looking as closely into what it was giving me & was just testing things as we went. I knew that would cause a lot of issues, but it's a personal project so I can get it a little messy if I want. Thankfully, the process of cleaning it up is going to be really great practice & will teach me a lot. 

Today I decided to take a closer look at the block of code I’ve been working with the last several days & realized that it is incapable of solving my issues. It processes the chunks provided by BM25 after it has already chosen them, while AI led me to believe it could fix the issue by changing the token ranking. It did seem to give better results for –wide last time but I think that might have just been because of the non-deterministic aspect of AI. If it did actually help, it's just a bandaid fix rather than solving the core of our issue. Seance_runner is already such a large file, it doesn't need any extra bloat.

# 11/8/2025
I made some minor improvements with –wide but were still not there.

# 11/7/2025
Didn't have a lot of time & just had to do what I could

# 11/6/2025
Since –deep keeps saying it is not receiving relevant context I tried to boost symbol tokens so a name like generate_filename would be at the top of the lists of tokens. It didn't seem to cause any issues but it didn't solve the issue either. I’ve built up so much technical debt, especially while I was sick. My strongest understanding of how things need to function is in videogames or webpages, this project is harder for me to wrap my head around what is happening. If I just had a full day to work on this I could really dig through all this & get a better understanding of where the issues are, but this project has unfortunately fallen down my priority list. 

I had slightly more time than usual today & was able to do more testing. I read through the –verbose –deep log to see what tokens it provided & it isn't even providing the right files to be able to answer the question, it's in the completely wrong spot. I have a debugger to check tokens exist for keywords, but I need more in depth information about how tokens are chosen before being fed to the LLM. It's going to take a huge effort for me to even begin to understand that process from the code itself. Python is one of the languages I’m still rather weak with & this is my first time trying to build anything like this. There is a treasure trove of learning ahead of me, I just need to find the time for a deep dive. Even though AI is pretty flawed in its current state, it should be able to answer my questions well enough for me to get a decent grasp.

# 11/5/2025
Some progress was made, it is now generating answers again but still having the same issues as before, but now with a bit more terminal feedback & some duplicate functionality was removed. 

# 11/4/2025
I’m still not in a place where I have a lot of time &/or energy to devote to this unfortunately. It's going to take a lot more work than I’ve been able to contribute to this, for a while, to keep it going. So far I’m just going back & forth trying to get seance –deep & –wide to both provide answers as they are intended. At this point I have little faith AI is going to be able to solve it & I’m going to have to really dig into this & understand where the root of the issue is & how to fix it. I really need to find a day to make another bigger push forward.

# 11/3/2025
I just looked for some low-hanging fruit to do anything on this. Other things in the day took precedent so thankfully there was something quick & easy to do. I’m running out of simple low-hanging fruit things to do… 

# 11/2/2025
Since I am finally feeling healthy again I mostly spent my day cleaning & running errands. It is so incredibly nice to not be extremely sick! As for coding, I just reverted back to the best version of seance. 

# 11/1/2025
I continued to debug the seance –deep & –wide functionality, to no avail. I am thinking I should revert again & move on to the next commands. I also updated my notes for October.  