# End of Month Recap
This month was a real challenge to my commitment. I got the most sick I have been in over 6 years, & it lasted essentially the entire month. I’ll spare the details but I had to go to the doctor a couple times & ended up needing antibiotics, which didn't agree well with me. On top of that I had a lot of work as well. This month was a miserable slog & I barely got to have any festive fun. 

There was a lot of going back & forth attempting to get better results with seance –deep & –wide. But I did have some success with several aspects of the project. I was able to add the verbose logs into the transcript for easier debugging & understanding of how seance reaches its answers. I also added a token debugger so it's possible to see what tokens are found for a keyword. Doctor now creates a .env file in the .geist folder so new users can run it to get the .env controls that are built in for commands. There was also some minor file restructuring. The readme was also updated.

Now that I am recovering finally I am hoping next month will be much more productive. 

---

# 10/31/2025 
HAPPY HALLOWEEN! 👻

# 10/6/2025
With how little time I have to devote to this, it is becoming increasingly difficult to add any real meaningful progress to the project. I want to keep working on it every day, but I have been considering putting it on hold until I have more time again. Because I don’t have enough time & am just trying to make some progress to keep committing code every day I am allowing the progress to be sloppy. Prioritizing speed, to get code committed each day, over everything is also causing me to learn less. If I could slow down to review everything & seek to understand it all better I would learn far more. A good middleground might be to still keep looking at the project & thinking about it every day but instead of committing code I could prioritize my notes, so I can think things through & still progress even when code isn't written. 

# 10/5/2025
Since the last 2 days worth of attempts to add –verbose to the logs didn't work I reverted to before I tried. To clean up the non-working code.

# 10/4/2025
I kept trying but still wasn't able to get –verbose to print to the transcripts.

# 10/3/2025
I want the –verbose information to go into the transcripts so it is easier to compare how changes affect what data goes into the LLM. Unfortunately I wasn't able to get it to work in the time I had available.

# 10/2/2025
After going back & testing –deep it is still giving sub par results. So the issue I am facing is something other than senace_runner. So I need to review changes since it was last working well & find the true cause of the issue.

# 10/1/2025
I reverted back to the best working version of –deep. The changes that have been made are providing worse results & that has not improved, so at this point it is better to revert & just re-add the useful additions that have been made in the last several days. I have so much more to say about my thoughts on this & what it has taught me. In particular about the strengths, weaknesses, & limitations of coding with AI. Unfortunately I need to commit this ASAP or it won't be committed until tomorrow. 