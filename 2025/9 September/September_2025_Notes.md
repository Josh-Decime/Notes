# End of Month Recap
In September 2025 I primarily continued to work on Geist-Agent. I wrapped up Ward functionality, reorganized the project files, started & nearly finished Seance. I also deployed the Quail-Kingdom-Market & Geist-Chatbot. That was all done in spite of how busy my personal & work life was through the month. Unfortunately I think next month is going to be even busier. But I’m still determined to keep coding every day with whatever time I can spare. 

(Expand upon monthly recap when I have more time)

---

# 9/30/2025
Seance is an important functionality for this project & is something I want to function well. For the most part it does. By default it can answer a wide array of questions. But there are certain types of questions it struggles with, which is why I made –deep & –wide. But at this point I have spent so much time on it that I need to move on soon. 

# 9/29/2025
I didn’t have a lot of time so I added the query logging back in because that was useful & had been lost when I was trying to get –deep & –wide to work better.

# 9/28/2025
Seance’s –deep & now –wide responses just keep getting worse when I try to develop them further. I’ve had to revert several times & am considering doing it again because it just keeps breaking. I am beyond my current depth of understanding so AI is really leading this one right now & I can't guide it or critique it like I usually do. This is my first project in python & I don’t find it as natural to read as other languages. This project is also very far from the websites, webgames & VR projects of my past in terms of what it does & how it functions. 

It would be so nice to have an actual expert to talk to, ask questions & learn from. AI can kind of explain things but when things get complicated it gives incorrect answers a concerning amount of the time. I’m used to self directed learning at this point, I learned how to digital sculpt, 3D print & metal cast largely on my own. But I could learn so much faster with assistance. I crave being in an environment with other professionals that are more knowledgeable than me, who I can learn from by solving hard problems together. For now I just have to keep marching on. I feel like a moth flying against glass, looking for an open window. 

# 9/27/2025
The wedding went well. It was a welcomed change of pace from my usual daily routine. I’m also really happy for one of my best friends! It was a lovely ceremony! 

I got my coding in before I went so I didn't have to worry about it. I just made a simple change, to be able to exclude non-code documents from what is fed to the AI when asking a question, something I probably should have implemented a long time ago. 

# 9/26/2025
On top of everything else I had a rehearsal dinner to go to. Even though I am a groomsman I had to turn down going to the bachelor party to have time to code. The bachelor party wasn't anything crazy, they were just watching a movie together. AI can reduce the burden of coding significantly to the point where it isn't a huge deal to commit code every day, but it does still take a commitment.

# 9/25/2025
I decided that I need to add a new –wide flag to search more files. –deep was trying to search too much & it couldn't handle that. So now –deep looks up more within each file, while –wide only takes the top most part of any file & searches much more files. I also added –env so that I can update the .env file mid chat & see the changes without restarting the conversation. Since giving too much context to the LLM breaks it, this is vital in figuring out where the optimal settings are. It's crazy how much clearer I was thinking today because I was able to take a nap. I've really been running myself to exhaustion lately. I still don’t even have enough time to do everything I have to do either. 

# 9/24/2025
Keeping things going, I just reverted back to the best version & did some more testing.

# 9/23/2024
Testing out making –deep scan a wider range of files. Initial tests were alright but by the end of the night answers were coming back as “not found” so it all broke. I did more aggressive editing than I have been thus far so I'm not terribly surprised that happened. I want to be able to give it more context without losing the question & the LLM just providing unrelated gibberish as an answer. 

# 9/22/2025
Today was one of the most crazy days! Wow! Three huge situations simultaneously went my way today! But it took up the entire day, the day started at 6am & I didn't even get home till after 9:30pm. It was a pretty intense day, super stressful for most of it. I couldn't even eat until 8pm because there was no time. All I wanted to do was go to sleep when I got home but I still had a lot of obligations. To keep the code streak alive I got rid of a small pet peeve in seance top of file comments. I also did some more testing of seance responses. While that does not generate code it is still very important to the overall development of poltergeist. 

# 9/21/2025
I did what I said I was going to do today & reverted to the better –deep flag & added –verbose support to mid conversation. 

# 9/20/2025 
I tried to make –deep feed top results before branching out but it is still having the same issue. Time has been extremely short lately with my other work & obligations. But tomorrow I am planning to revert to the seance_runner I had on 9/18 because that was much closer. Then I’ll allow it to take –verbose tags mid conversation, like how –deep works, so I have better troubleshooting feedback about how answers are being generated. 

# 9/19/2025
When I try to expand the information provided in –deep it’s answers become unrelated to the question asked.

# 9/18/2025
Late night getting something worth committing. I’m still dialing in –deep, but we got a lot closer today. 

# 9/17/2025
Insane day! Thankfully I had something simple that needed done. It's been hard to keep up with my goals with everything else going on.

# 9/16/2025
Iv got some good testing today for seance. It actually surprises me with how good some of its answers are, as long as it doesn’t have to bring in multiples. For example if you ask “what does seance do?” it gives a fantastic answer, but if you ask “what does each file of seance do?” then it will only summarize one file. –deep is definitely broken, whenever I run it the answer it provides is completely unrelated to the question. It's acting like the question isn't getting asked so it just gets random files & decides what it's going to say about them.

 I got rid of all the reports on here because it was prioritizing those files before anything else so I was getting really weird answers sometimes. It might be a good idea to come up with a good solution to ignore certain files so the user can hide stuff like that from seance while still keeping it in the codebase. I think it might also be a good idea to have a variation of unveil that writes a json file that summarizes the project super in depth so it is easier for seance to answer questions if it references it. I wonder if the normal unveil report would be useful if you only put 1 that was up to date in it, rather than a bunch of reports that are all over the place across time & multiple projects. 

The index was out of date, so now it writes the index every time you run seance, I planned for it to do that initially but it slipped through the cracks until now. 

# 9/15/2025
My energy levels by the time I could work on coding was completely gone! The only reason I did anything at all was to keep my code streak alive. I was dead.

# 9/14/2025
What a busy day! I’m so ready for bed. –deep flag can now be activated mid conversation. It also lists the retrieval context, with the scan type, hits, context & files.

# 9/13/2025
Switched from Jaccard to BM25 for more advanced file retrieval, to feed to the LLM. This should hopefully pull up more relevant files for the AI to find the answer to your question quicker & easier. That should also make smaller models more reliable in answering because they are only receiving files that have been matched with keywords from the question. But, since it is based on word matching it will certainly have some limitations, however. So it uses BM25 by default but adding the –deep flag to it will allow for a wider file scan, which will take longer but hopefully solve issues that it normally gets stuck trying to answer. Adjusting the amount of files/chunks the AI receives changes the effectiveness of the results & the optimal amount will be different depending on the size of the LLM utilizing it, so those variables can now be adjusted in the .env file. 

That's all good in theory but in actuality it is quite messy right now. It is great with some questions but struggles with others. I thought BM25 would be better at pulling up all instances of a function’s name through the codebase, but it is still only sending a few files while neglecting others. I cranked up the amount of files that I could receive with –deep & the answers it was giving were not related to the question I asked, even a little bit. I would ask about generate_filename & it gave me a repeating response about typer. Then when I asked it to “find all functions that call generate_filename” it just spit out the code to doctor.py, which is extra strange because it doesn't even use generate_filename so there is no mention of that anywhere in the file. This is a separate issue, but I need to delete all those reports in my project because they are definitely tripping it up & confusing the AI. 

# 9/12/2025
My client work took up most of my working time today again. I was able to update the terminal while chatting with seance, so now it lists what model is being called & has a little loading indicator instead of just spitting out a ton of background information about how it is functioning. The old log style is still available with the –verbose flag & will be helpful for adjusting the responses. 

I did some testing & was severely disappointed with it's inability to answer simple questions. In yesterday’s testing I noticed that the k chunking made it so it couldn't answer questions that relied on looking at several files. I asked which functions use generate_filename & it could only give me one subcommand at a time & couldn't see all of it. So today I tried a similar question that was located in a single file. I asked what all the subcommands for poltergeist are, the best answer it provided was for me to invoke poltergeist –help. But it was unable to give me the straight answer I was looking for. I’m curious if that is just because of the smaller local model I'm using. I need to add some .env controls for this so I can easily swap out the LLM & test results with stronger models, as well as adding controls for the k chunking. 

# 9/11/2025
I am flying through setting up seance! It now runs by just typing “poltergeist seance”, yesterday you had to name the index & then build it separately before being able to ask questions. The reply was also scanning for an answer instead of utilizing the LLM & it was giving confusing, not human friendly answers. Now it uses the LLM. Results were hit or miss, with it providing the correct answer on simple questions but anything that had multiple spots in the codebase it couldn’t answer correctly. The logs are also overly verbose, showing the structure of what is prompting the AI & what files it has access to for answering. Now I just need to dial it in so it's giving better answers. I’m curious how much that has to do with the LLM attached too, maybe I’ll have to actually use an API key instead of just my local model for some testing. Overall this is coming along extremely quickly & I am super impressed still!

# 9/10/2025
I am shocked & amazed at how far along seance is after just one day! My day was packed & I barely had any time to work on this, but it can already connect & answer questions!!! There are definitely many things to work out to get it all flowing smoothly but it is so much further along than I would have imagined it would be in a single day! Especially when I spent most of the day working on other projects. There is a lot more I want to say about it, but it's already getting late, I need to be off to sleep. 

# 9/9/2025
Since deployment is fresh in my mind from yesterday I deployed Geist-Chatbot. So much easier this time around. Hopefully this sticks in my mind for next time, granted it will probably be a while since I don't have any website projects I’m working on currently. After I finish this AI agent there are some other agent workflows I wanted to try, like LangGraph & MCP servers. I also want to make another VR project! I really enjoyed the last one I did, even though it was a work project. I would like to make a small VR game just for fun! There is just not enough time in the world for everything I want to do! I have so much client work to do right now, I think it's going to slow down my AI Agent project for this month. I’ll keep moving along with whatever time I have available. 

# 9/8/2025
Deploying a Vue project is one of those things I just don't do frequently enough to have it totally down. It doesn't help that I use a different method almost every time too. In the past I used gh-pages, but this time I wanted to try deploying with GitHub Actions. I like Actions better, but I overcomplicated it at first & was in a weird limbo where I was still trying to deploy it as if I was using gh-pages. The Quail Kingdom Market is now deployed! It is great to see it on my phone! It will be nice that other people will be able to access it too, instead of me just having it up in localhost on my laptop on monthly signup days. It has been pretty fun being the Brass Key Collective official merchant. The Quail Kingdom has just expanded so it's no longer just once a month. 

# 9/7/2025
Almost all of my time today went to a pre-wedding party. I’m very glad I had something to do that is quick & easy, to still make progress. Yesterday I decided to go with a verbose file naming convention, so I just swapped ward to that as well. Instead of just ward/runner.py it is now ward/ward_runner.py. 

# 9/6/2025
I wish that imports could auto-update when you change file names or move them. Like if once an import was connected it recognized when the file moved or changed names & just auto swapped them, that would be nice. I ran this in the terminal to auto update the imports & it worked but added an empty line at the bottom of every file it touched.

```powershell
$map = @{
  'from\s+geist_agent\.unveil\.runner\s+import' = 'from geist_agent.unveil.unveil_runner import'
  'from\s+geist_agent\.unveil\.tools\s+import'  = 'from geist_agent.unveil.unveil_tools import'
  'from\s+geist_agent\.unveil\.agent\s+import'  = 'from geist_agent.unveil.unveil_agent import'
  'import\s+geist_agent\.unveil\.runner'        = 'import geist_agent.unveil.unveil_runner'
  'import\s+geist_agent\.unveil\.tools'         = 'import geist_agent.unveil.unveil_tools'
  'import\s+geist_agent\.unveil\.agent'         = 'import geist_agent.unveil.unveil_agent'
}

Get-ChildItem -Path src -Recurse -Include *.py | ForEach-Object {
  $p = $_.FullName
  $txt = Get-Content -LiteralPath $p -Raw -Encoding UTF8
  foreach ($k in $map.Keys) { $txt = [regex]::Replace($txt, $k, $map[$k]) }
  Set-Content -LiteralPath $p -Value $txt -Encoding UTF8
}
```

# 9/5/2025
Today I took file walking out of unveil_tools.py & moved it to utils like I have been planning for a while now. I also increased the scope of scanned files. But it was more than we need for most scans, so I set the old file scan restrictions to be default & allowed larger scans with the flag –full. I also deleted unused files & codeblocks, to clean up the project. I’ve been focused on refactoring & cleaning things up the last several days, getting that deep cleaning going.

The chat I was using with GPT today was cursed! I used an older chat I started when I was inquiring about what files need to be moved out of unveil_tools. Back then I was thinking of potentially moving more than I needed out just for re-usability sake. But I put that on hold to keep developing functionality. I decided I’ll only move the functions that are being reused, everything else can stay where it is unless I have another workflow that needs to call something from it later. I went back to this chat & asked it to update to my new files & instructions, it said that it did but then it just didn't follow my set instructions & would hallucinate code blocks. This was a great testament for how much instructions actually help! It has been so nice to not repeat myself across other chats for simple formatting & project logic handling. Also, sometimes just starting a new chat & giving it all the information it needs again is less work than continuing with a chat that has more of the information, but isn't giving good results. 

# 9/4/2025
I’m shocked at GPT 5’s ability to refactor code. It only took 2 prompts for it to refactor my file that was 1191 lines of code, into 4 files that added up to 941 lines of code. I spent most of my time today verifying it works & trying to uncover the changes. I haven't yet noticed any issues or major changes in functionality at all. The only real change I see in functionality is that some of my extra terminal logs for testing are gone. I’ve been prompting GPT 5 to explain the difference in code, how it is smaller than the original file, but it really seems to struggle with that kind of task. It couldn't explain how the code shrank by 250+ lines, would be more after repeat imports per file because they increased the total lines in the refactor. It gave some examples of changed code but it only accounted for less than 50 lines of code shrinkage. 

Even though it seems to all be working as intended I worry that some edge case handling code might have been left behind in the refactor & I just haven’t stumbled upon it yet. Working with AI is certainly a double-edged sword. This is why it is so important to have a good file structure from the beginning. I had rushed ahead with this functionality without proper planning for file structure, going forward structure needs to be a higher priority. But it's good to know it can refactor so well, if needed. 

# 9/3/2025
Ward now has better terminal logs for what is happening when OSV runs, if you don't have lockfiles or manifests to scan then it defaults to the API to still complete a report. 

# 9/2/2025
Ward now scans larger projects, it splits up the API calls & then stores them. You can even adjust the settings in the .env file which is a nice addition. I want any variables that you might want to change to be in the .env so there's only 1 file to interact with to finetune the agent. With that I’ll say that ward API calls are good for now. I installed OSV to test out how ward utilizes it. Unfortunately it isn't getting the information it needs to run, so there is more development that will go into getting it working. 

# 9/1/2025
Today I cleaned up some of the code in ward_runner.py. I initially thought to just go back to the previous commit & then reintegrate functionality back, but having AI compare the code & only implement a fix didnt work. It also increased the file quite a bit still so I just cut my losses & went back to the larger file. Then GPT & I looked for some cleanup that we could do within the file. After cleaning a bit we moved forward on making the reports more useful. When you run it with OSV API it now collects the severity of the vulnerabilities. The LLM you have connected also gives a summary. There is also now a monitoring & continuous scans section at the bottom that gives an example of how to use the json scan to continuously monitor your dependencies, by only showing new vulnerabilities. 
The ward_runner file is getting far too large for my liking. I have some serious codebase cleaning to do. Ward_runner needs to be separated into at least 2 different files, some of unveil_tools needs to be moved to utils because ward_runner shouldn't be calling it for anything. Also, ward can't run on larger projects with more dependencies. Atleast, not the API version which I’m testing first, before comparing it to the OSV installed version. There is still a lot to do!