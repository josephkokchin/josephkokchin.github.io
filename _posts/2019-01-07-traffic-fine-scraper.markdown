---
title: "Building a traffic fine scraper with Python"
layout: post
date: 2019-01-07 03:20
published: true
image: ../assets/posts/joystick_diagram.png
headerImage: false
tag:
- Python
- Web Scraping
- Automation
- Bots
- Selenium
category: blog
author: rodferro
description: Building a traffic fine scraper with Python and Selenium
---

<h2><span class="evidence">Motivation</span></h2>

The other day I was remembering that during my visit to Mexico City back in June '17 (for my participation on the first edition of the [PythonDay México](https://rodolfoferro.xyz/pythondaymx/)), a [friend of mine](https://twitter.com/JMireles_) recieved me at his home for my stay. The thing is that during my stay we were talking about building something that could be useful, so we decided to scrape a website in which people with car plates from Mexico City would be able to verify their traffic fines.

The website is the following: [http://www.multasdetransito.com.mx/infracciones/df-distrito-federal](http://www.multasdetransito.com.mx/infracciones/df-distrito-federal)

As you may have noticed if you opened the site, it contains an input to write down the car plate from which you want to search the traffic fines and the site returns them (if the plate has any).

What my friend told me was that an issue for citizens in Mexico City is that just a small bunch of them are the ones who know about that site, so it might result useful to create something in which they can consult this info in an easier way.

After this, I was like: *"Dude, today I held a workshop on how to build a TwitterBot in 30 minutes for the PythonDay, what if we build a TwitterBot that inputs the plate in the site and then scrapes the info from it automatically?"*. He said yes. With this, we built [MultaBot](https://twitter.com/MultaBot/with_replies) a TwitterBot that used to read a car plate and scrape for its traffic fines.

We started with this project as a private project, but the other day I was invited by the *[Division of Law, Politics and Government](http://www.ddpg.ugto.mx/)* of my university to give a tech talk about how automation can be useful for future jobs not for only people tech related, but also for politicians and lawyers. When I remembered about this, I thought that it would be a nice example, so I wanted to give it an improvement on its base and ended with this example script that now I want to share with you.

<h2><span class="evidence">Experimentation</span></h2>

I'll explain the whole code, so you'll understand what's happening all the time. To begin, I'll import [Selenium](https://selenium-python.readthedocs.io/) and the Python [data pretty printer](https://docs.python.org/3/library/pprint.html):

<code data-gist-id="5cd80b39fa4b2d6ae44ddb61f9a2d59e" data-gist-hide-footer="true" data-gist-line="1-2"></code>

Selenium will allow us to automate the control of a web browser, so the idea will be to use it to automatically open the website, input the car plate and after loading the traffic fines extract and parse them for the `pprint` output.

After this, I created a function to launch the browser and scrape the info of the car plate. If `verbose` is set to `True`, the function will print details of each traffic fine:

<code data-gist-id="5cd80b39fa4b2d6ae44ddb61f9a2d59e" data-gist-hide-footer="true" data-gist-line="5-19"></code>

Inside the function I've set the url to be scraped, then called to a function named `busca_placa_df` (which means *search_plate_df*, *df* stands for Federal District in Spanish) and then I close and quit the opened browser for this search.

Then, I built the main function that inputs data and then scrapes the traffic fines:

<code data-gist-id="5cd80b39fa4b2d6ae44ddb61f9a2d59e" data-gist-hide-footer="true" data-gist-line="22-69"></code>

As you see, in lines `24-26` I clear the data in the input field with `id=plate` from the HTML source, then input the car plate that I want to look for, and after this look for the button by its XPath and click it (lines `28-29`).

I now want to know the results for the search, for this look for the element with `id=secciones` in the HTML of the response (lines `31-32`) and first verify if it has any debts by looking if the resulting text is only `"INFRACCIONES"`, if so I returned a message saying t has no debts (lines `33-34`). In the other case, in lines `35-36` I save the result with its contained text (which specifies the number of traffic fines for the plate).

If the flag `verbose` is turned on, then the scraper will get all the info of each traffic fine (lines `38-40`). For this, it will look for the element with `id=tablaDatos` in the HTML, which contains all the info of each traffic fine and if it is not empty (line `41`) it will iterate for each traffic fine and then extract all the info them (lines `42-50`). I now build a dict with the response to serve it in a nice way using `pprint` (lines `52-67`) and return the result (line `69`).

To test the script I just called the function `launch_browser` with a demo car plate (that coincidently has 2 traffic fines) and print the results (lines `72-74`):

<code data-gist-id="5cd80b39fa4b2d6ae44ddb61f9a2d59e" data-gist-hide-footer="true" data-gist-line="72-74"></code>

If you run this in a script, you'd get an output like this one (note that it prints the 2 traffic fines I mentioned 😝):

<center>
  <img alt="plate_scraper.py" src="../assets/posts/plate_scraper.png">
</center>

<h2><span class="evidence">Conclusion</span></h2>

At the begining, what we thought would be a project just for fun to work together that night *–like a mini hackathon–* ended with a useful project that could be helpful for citizens in Mexico City.

As you have seen, Python has tools that help to automate some things in very cool ways. I mean, if you run the script as it is provided, you should see a browser window to open automatically, then the text gets written alone in the input field and the results are shown by their own. **Isn't this really awesome?**

Please let me know what you build with Selenium and Python in the comments! 💻🐍🤙🏼

<!-- JS Imports for gist-embed: http://blairvanderhoof.com/gist-embed/ -->
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/gist-embed/2.7.1/gist-embed.min.js"></script>
