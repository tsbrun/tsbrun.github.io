---
layout: post
title:      "Sinatra Project: Plot Manager"
date:       2020-11-19 19:44:02 +0000
permalink:  sinatra_project_plot_manager
---


Another project completed. I built plot manager where a user can login and perform CRUD actions on plots and characters. 

Development ran smoothly up until I got to routes. I was trying to interpolate Ruby code into my routes, so that—for example—a user could be redirected to their specific show page after successfully logging in. The thing is, I was using single quotes, which are not compatible with interpolation. It took a while before I figured it out, but that was one of the main difficulties of building out my controllers. On a related note, I found out that the href attribute of a link tag (`<a>`) should point to the resource's route (as defined in a controller)—not the path of the file you want to display.  

Something I learned from watching video reviews and recorded study groups is to constantly test the code you just wrote. Make sure that it works, or that it hasn't broken some other code that used to work. I had to keep reloading my web page, making sure the logic I had written in the controller worked (the `shotgun` gem is a lifesaver, btw). A potentially easier way to practice TDD is to write tests with rspec and/or Capybara. An hour of practice writing tests could shave off a few hours of writing / testing / debugging code. I mostly say this to convince myself to sit down and learn how to write tests so I can endure fewer hours of torture when it's time to build my next project.

I logged 104 commits during this process. I'm still not as proficient as I would like with git, and I definitely could have split up a few commits into smaller pieces. In the process of trying to make my commits more compact, I discovered the `git reset HEAD~` command, which allows you to split the most recent commit. Also, I used git branches during the development process. Instead of being afraid of messing up my code when adding new features, I can create a new branch. If I code myself into a hole, then I just delete it. And if whatever feature I wanted to add works out, I can merge it with the main branch.

Here's a quick list of some other lessons I learned during this project build:

* The devil is in the details, especially when it comes to documentation. All that technical jargon and example code looks really overwhelming, but you need to read it carefully and try to understand it. Otherwise, you may miss the answer you're looking for.
* Make it work, then refactor later. It's ok for your code to look messy or not be the most efficient the first time you write it. Focus on the foundation, then improve / beautify it once your MVP features are green (i.e., passing tests).
* Know when surface-level understanding is good enough. I tend to go down a Google rabbit-hole when looking for answers to programming questions. It feels productive because I'm learning new, interesting information. But it prevents me from actually coding and it drags out the time I take on a project. Sometimes I just need to fix the problem and move on.

Overall, I think the most important important lesson I've learned from this project is:

![](https://media.giphy.com/media/2rIDTzizHRQv6/giphy.gif)
