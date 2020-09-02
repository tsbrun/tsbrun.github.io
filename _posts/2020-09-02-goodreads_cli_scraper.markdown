---
layout: post
title:      "Goodreads CLI Scraper "
date:       2020-09-02 20:44:06 +0000
permalink:  goodreads_cli_scraper
---


I just completed my first Flatiron project—the CLI Data Gem Project. The main requirement is to build a command line application that scrapes a website. It also needs to accept user input and use it to go at least one level deep into the scraped info and return something useful to the user. Seems simple enough, right?

![](https://media.giphy.com/media/3o7bu4G19uhzAf1DYQ/giphy.gif)

My first idea was to build a CLI that scrapes the website [remotewoman.com](remotewoman.com). Initially, it seemed like a great idea. The structure of the website was fairly simple, and so was my scraper. The first major problem, though, was that it took *far* too long to load. In fact, if I loaded more than 10 results, the program would stall indefinitely. It was too much data for my little program to handle. 

Second, there was not really any way to “go a level deep.” I wanted to implement some kind of search function using a gem, but that proved to be beyond my current scope of ability. In the end, I decided that my first idea was not the best way to demonstrate my understanding of the material. Thus, that project was scrapped and I went back to the drawing board.

My goal for the project was to create something that I want to use. Finally, I settled on what would eventually become the [Goodreads CLI Scraper](https://github.com/tsbrun/goodreads-cli-scraper). I'm always looking for something new to read, so why not build a tool that collects new books from Goodreads? 

Armed with my vision for the project, I began the planning phase. I had created the flow diagram and planned out the logic of my program—including nearly all of the classes and functions I would need—within an hour. The experience from my first failed project idea definitely sped up the process. Excited to start building off of my blueprint, I started to inspect the structure of the Goodreads website... and promptly ran into my first major obstacle. 

You see, I was so excited to get started that I planned out the project, drew the flow diagram, and built out the skeleton of my classes *before* inspecting the website to get a feel for its organization. It was not at all as straightforward as [remotewoman.com](remotewoman.com) or the website used for the labs on Learn.co. And I had already submitted my checklist, so there was no going back... 

![](https://media.giphy.com/media/TJawtKM6OCKkvwCIqX/giphy.gif)

After getting over a mini *"I'm in over my head"* crisis, I sat down and got to work. Logically, I started with the #get_page method and used Nokogiri to open the page containing a catalogue of genres. First, I had to have some way to access the url of a specific genre. I did so by giving #get_books an argument of ‘url’, which would take the ‘url’ class variable from the user’s genre of choice. 

The Goodreads website is organized such that—on a specific genre's page—there are images of books linked to that book's url on Goodreads. In order to glean information about those books, I would have to open each url and scrape the necessary data. I used #get_books to open the genre’s page, instantiate instances of the Book class for each url, and assign each instance’s @url and @genre variables. Then, I used #make_books to go through Book.all, open each book’s url, and scrape those webpages.

While wrapping my head around the actual logic of the functions was a challenge, the most difficult obstacle proved to be scraping the correct text from Goodreads. I spent a few hours puzzling over Nokogiri documentation, browsing Stack Overflow, and going through a lot of trial and error. 

Even though the project didn’t go exactly as I expected it to, I still learned so much.

“Write the code you wish you had” was one of the most important suggestions I applied, and it guided the planning phase of the project. In order write the code I wished would work, I need to know exactly what I wanted my program to do. Once I knew that, all I had to do was code those methods. It was akin to writing tests with RSpec, in a way.

Throughout the coding process, documentation was critical. For example, I tried to use #select to assign a Book instance’s genre. Little did I know, #select always returns an array. Thus, in instances when I was expecting a single instance of an object and wrote my code accordingly, I would get an error to the effect of "you can't perform this operation on an array." When expecting a single return value, it's better to use the #find method. I didn’t realize these distinctions until I looked up the documentation on apidock.com.

As I was building my classes, I tried to adhere to the principles of [Don’t Repeat Yourself](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) and [‘single-responsibility’](https://en.wikipedia.org/wiki/Single-responsibility_principle). In the Scraper class, initially the code in #make_books was part of the #get_books method. However, this looked a bit messy, not to mention that two jobs were crammed into a single function. Hence, I separated them and simply called #make_books within #get_books. 

For my next project, I will take advantage of RSpec to make testing my program easier. And I want to improve my commit messages to GitHub and make them more descriptive and adhere to a consistent format. 

**Key Takeaways**

* Write the code you wish you had. 
* Read documentation, paying attention to each method’s return values. 
* Sometimes, the best way to find a solution is to stop looking for one (i.e., [the Eureka effect](https://en.wikipedia.org/wiki/Eureka_effect#:~:text=The%20eureka%20effect%20(also%20known,Some%20research%20describes%20the%20Aha!)).
* Google the same question in different ways until you get the answer. More often than not, someone has already asked the same thing using different words.






