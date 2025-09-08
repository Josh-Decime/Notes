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