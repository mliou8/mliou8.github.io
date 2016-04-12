---
layout: post
title: Emoji Player
---

![Image of Yaktocat](https://octodex.github.com/images/yaktocat.png)


I just recently deployed a side project! I'm tentatively calling it 'The Best Emoji Music Player in the World'.  
Check it out here: [Emoji Player](www.emojiplayer.com)  




It's amazing that the domain name was basically untaken. I think it's because no domain name bots have picked up on emoji as a real word yet.
The idea was originally for a NYC Spotify hackathon about music visualization. What are different ways that we visualize music?

We were told that there have been two main ways of visualizing music. One way is "eye candy", which is basically finding cool and 'wow factor' 
ways to represent the different audio components of a song, like the base line, vocals etc. The other is codifying components of music.
A cool demo we saw is where the maker filmed very easy to associate actions like "stomping your foot" and instead of playing the sound, only played 
the clip of someone stomping their foot. In that way, and layering different visuals around that image, you can "listen" to the song only using your eyes.

I'm using a lot of air quotes.



<!--break-->

Anyway, to wrap it up, I was interested in how emojis are becoming digital shorthand for expressing certain sentiments. 
Basically similar to Instagram's engineering team, and their deep dive into how emojis are being used on their platform. [link here] (http://instagram-engineering.tumblr.com/post/117889701472/emojineering-part-1-machine-learning-for-emoji)
I thought that since
they've already been codified to have a certain meaning, but also that this meaning can vary from person to person ("What did you mean with that face?")

It would be interesting to see if the song that gets generated matches up to the emojis that you used.
Basically, I'm super interested watching people use the app in person, watching how they drag them, their little comments of "oh I like this one. Why'd you add this one?"
And then "Hey that's exactly what I expected!". or not.

In the future I'll probably be adding the following features:
  - Upvotes or downvotes, or some way of getting input from the user on whether the song matched their expectations. 
  And then feed that information back into the database.
  - Sentiment mapper to show what qualities you're getting closer to.
  - More? Suggestions? 

Heroku Note: If you're deploying on heroku using node.js and you have both node and bower dependencies, you'll need to
do the following:

1) Add bower as a dependency in your package.json
2) Add "postinstall": "bower install" into your scripts object. This will install bower after the initial script is done.
3) Make sure that you have a bower.json file as well, and that it has all the dependencies that you will be using.

I was struggling with this for a while, because I forgot to --save my bower installed dependencies and while it was installing
all of the npm modules just fine, it didn't know which bower packages it needed to install.

A way to test if all your scripts are correct, and will run properly on your production environment, is to -rm rf all of your 
node_modules, and bower_components, and then reinstall both. If your app runs correctly still then you should be good to go.
This is essentially the process that heroku will run too, if youfollowed the previous steps correctly.



