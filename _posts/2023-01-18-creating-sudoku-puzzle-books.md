---
layout: post
title:  "Creating Sudoku Puzzle Books"
date:   2023-01-18 10:17:59 -0800
categories: sudoku publishing
tags: sudoku publishing book sudoku-solver
---
{% include scripts.html %}

I recently published my first Sudoku puzzle book, and getting to this point has been a huge personal journey. Read on to learn all about how I got there.

<div style="justify-content:center;text-align:center;">
	<a href="https://www.amazon.com/Large-Print-Sudoku-Eric-Magers/dp/B0BRDC3SYB?crid=3429FI9XUDHG7&keywords=eric+magers&qid=1674176696&sprefix=eric+mager%2Caps%2C143&sr=8-2&linkCode=li2&tag=emagers-20&linkId=fa76e7f91efafa31df51f17af6789721&language=en_US&ref_=as_li_ss_il" target="_blank"><img border="0" src="//ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&ASIN=B0BRDC3SYB&Format=_SL160_&ID=AsinImage&MarketPlace=US&ServiceVersion=20070822&WS=1&tag=emagers-20&language=en_US" ></a><img src="https://ir-na.amazon-adsystem.com/e/ir?t=emagers-20&language=en_US&l=li2&o=1&a=B0BRDC3SYB" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />
</div>
<br />
I became interested in Sudoku in 2019 after discovering the YouTube channel [Cracking the Cryptic](https://www.youtube.com/channel/UCC-UOdK8-mIjxBQm_ot1T-Q?themeRefresh=1). YouTube knows me well and kept pushing their videos into my feed until I finally clicked, and it was a life changer. You would never think you could spend hours watching people scratching their heads and saying things like "and now we're off to the races" in a British accent until you've tried it. This channel made me focus and get interested in the different Sudoku-solving strategies and the logic behind those strategies.

I created a naive Sudoku solver around that time. Once the solver was completed, I thought about how I could use the solver to create an original Sudoku puzzle. While I could generate puzzles using the same solver logic, I then realized there are a lot of complexities to making **_good_** Sudoku puzzles. For instance, an important rule is that a Sudoku puzzle can only have a single solution. Another thing to consider is the difficulty of the puzzle. You wouldn't want to give a Sudoku to a beginner that isn't solvable by a human in the first place (or is too difficult to intuit a solution).

At this point, I got distracted by wanting to learn [Blazor](https://dotnet.microsoft.com/en-us/apps/aspnet/web-apps/blazor), so I dropped that project in favor of a Blazor Sudoku web game. I don't remember where I left off with it, but I had it mostly playable. However, I faced the challenge of not being able to provide realistically solvable puzzles (this was an extension of the solver/puzzle generator problem). I also wanted to extend it to play other Sudoku variants, and this is where the project also went to the back burner. My interest shifted to [Rust](https://www.rust-lang.org/), and other projects came and went.

Fast-forward to 2022, I revisited the original idea of creating a Sudoku solver. This time, though, I decided to implement Sudoku-solving strategies rather than take a naive approach. The naive approach, called backtracking, will give you a solution and can even tell you if there's only one solution. Still, it has no way to grade the difficulty of the puzzle. With the approach of using logical strategies, you have the benefit of having a way to determine the puzzle difficulty (based on the number of times techniques were used and the difficulty of those techniques). The strategy approach also gives the bonus of not having to deal with recursion.

Implementing the solving strategies also let me take a more iterative approach to build the solver, which helped keep me interested. For example, I could set a goal for a day or week to "implement X-Wing" as an example. This gave me the benefit of having the endorphin rush of pushing the change, seeing the tests pass, and closing the issue in GitHub for each strategy I implemented. I didn't have to delay that gratification until the entire solver was complete.

As I went through the development, I also realized the same as back in 2019. Any Sudoku solver would be easy to convert into a Sudoku puzzle generator. That became the next part of my project, which I wrapped up pretty quickly. I could now create any number of Sudoku puzzles that I wanted with an associated grade (I'm still fine-tuning the grading algorithm).

But what do you do with hundreds of thousands of Sudoku puzzles? Well, you make a game or app people can play, or you make a book. I didn't want to do any game or web development at the time, so I decided to make a book.

Creating the book took more work than implementing the Sudoku solver or generator. This first challenge was to figure out how to programmatically make PDFs, which was a manageable issue. There are handy tools out there to convert HTML into PDFs using Chromium. The big problem was creating the HTML template, which would be converted into the PDF, which actually looked good after the conversion. After many pixel-pushing hours, I came up with something decent and then had to write some logic that took the template and input all the puzzles.

To end this journey, I signed up for and created a new book in KDP, which was pretty straightforward. I used a free KDP ISBN, uploaded my book as a PDF, and created a cover using their cover builder. If I ever make another book, I will create the cover outside their tool since what you can do with it is very limited. Then I just had to wait for what seemed like forever for the book to be approved and listed for sale. So far, I have lost $3.27 on the book since I ordered an author's copy and have yet to make a sale, but that's perfectly fine. I never was in it for the money. I enjoyed the process and did something I never thought I would (publish a puzzle book). Of course, best of all, I am now a published author (let's ignore who did the publishing and what kind of book it is).

Stay tuned for more posts about Sudoku strategies and how I implemented them in my solver. Every step of this journey was a lot, and too much for a single post, but I'll be sure to document it all in future posts for any that are interested. Be sure to check out and share the book with anyone you know who either likes, or you think might like, Sudoku!

<div style="justify-content:center;text-align:center;">
	<a href="https://www.amazon.com/Large-Print-Sudoku-Eric-Magers/dp/B0BRDC3SYB?crid=3429FI9XUDHG7&keywords=eric+magers&qid=1674176696&sprefix=eric+mager%2Caps%2C143&sr=8-2&linkCode=li2&tag=emagers-20&linkId=fa76e7f91efafa31df51f17af6789721&language=en_US&ref_=as_li_ss_il" target="_blank"><img border="0" src="//ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&ASIN=B0BRDC3SYB&Format=_SL160_&ID=AsinImage&MarketPlace=US&ServiceVersion=20070822&WS=1&tag=emagers-20&language=en_US" ></a><img src="https://ir-na.amazon-adsystem.com/e/ir?t=emagers-20&language=en_US&l=li2&o=1&a=B0BRDC3SYB" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />
</div>