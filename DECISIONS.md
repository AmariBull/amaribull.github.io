# Decision log

Your methods section. About one page total.

Answer these as you go, not the night before it is due.
Specifics beat polish - a short honest answer is worth more than a long vague one.

Delete these instructions when you are done, or leave them. It does not matter.

---

## 1. What did you set out to build, and what changed?

What you wanted at the start, and what is actually live now.
Name one thing you dropped or added along the way, and why.

At the start of this project I was set on building a site that displayed information about me in a blog style focusing on nontechnical aspects I want to highlight. My goal was to brainstorm ideas about what specific things I could add that did not focus the attention on the school work I complete every week. Given that the plan that was cooked up between me and Claude was a soft styled blog detailing my interests of food, media, sports, and crafting. One thing what was added was and about me section seperate from the homepage so that I could still talk about my studies and work but not make that the focal point of the website.

---

## 2. A fork in the road

Name one real choice where you could have gone two ways.
Plain HTML or a framework. One page or several. Your own CSS or someone's template.
What goes on the front page and what does not.

Say which you picked, what the alternative was, and what you gave up by not taking it.

"There was no alternative" is not an answer. Find the fork.

A choice that could have gone multiple ways was the media use on the site itself. Claude presented multiple options of how I could add visuals to the site including colored blocks, stock photos from online, and personal photos that I had access to. With each of these options there were pros and cons but ultimately I decided on going with the personal photos so I could ensure the true to me. I believe this also makes the site more personable and easier to connect with for those who happen to scroll on it as well.

---

## 3. Where you overruled the agent

One time Claude suggested, wrote, or claimed something and you did not take it.

What did it do? How did you notice? What did you do instead?

If it genuinely never happened, say so plainly, and then say what you would have had to
check in order to notice. Being honest here costs you far less than a story you cannot
defend when you record your video.

Honestly, Claude cooked. Understandibly, I can attribute much of its understanding to the planning that was done before even touching the code but even still it was as if Claude was in my head. All the suggestions that it would give and the explanations behind the changes it made coincided with a lot of this things I was thinking myself. It took very little redirection for Claude to understand my point and apply changes seamlessly which was very nice to see. I am not sure if what I was making here was just that basic and obvious but it made this process very smooth and fun to do.

---

## 4. How you know it works

What check did you run, and what did it tell you?

Then the real question: **what would have made this check fail?**
A check that could not have failed is not a check.

Link to your `verification/` folder.

I fetched the live URL directly instead of just trusting that the deploy worked, both right after each push and again a few minutes later. Comparing the fetched content against my local files line by line confirmed the live site actually matched what I'd committed, not just that GitHub said the push succeeded. After I reorganized the file tree into src/ and ui/, the first fetch came back 404 on the moved pages, which turned out to be normal GitHub Pages deploy lag and resolved itself a few minutes later. 

If I'd only checked that the push succeeded and the site returned a 200, I would have missed the football photo being served under the wrong casing entirely, since locally it looked completely fine.  This check would have failed, and shown me it failed, if the live fetch had come back with a 404 or served old content instead of what I'd just pushed.

Link to your verification/ folder: verification/

---

## 5. What is still wrong

One thing on your own site that is not right, not finished, or that you do not
fully understand.

What would you do next, and how would you find out?

The formatting of my images are still not completely correct. For the time being I guess it is not as large of an issue for the requirements of this project but it is something that is apparent to me when I look over the site. I believe it can be fixed with a prompt to Claude about rotating and resizing the images but I think it adds a bit of character to the site itself.
