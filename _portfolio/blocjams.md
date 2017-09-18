---
layout: post
title: BlocJams
thumbnail-path: "img/blocjams.png"
short-description: BlocJams is your source for on-line music streaming, similar to spotify.
---
{:.center}
![]({{ site.baseurl }}/img/blocjams.png)

## Summary
BlocJams is a music streaming website. Similar to Spotify, BlocJams is an interactive website that allows you to select from a variety of albums and makes discovering and playing music an easy experience.

## Explanation
BlocJams is the first project I was assigned during my web-devolopment course at Bloc.io. I was given a basic outline on how BlocJams was supposed to look and function. I then had to create javascript and jQuery functions to make the site interactive and functional.

## Problem
* Improve overall aesthetics
* Create a dynamic collections page
* Make the songs on the albums page react to the user scroll and click, adding     play/pause buttons
* Improve user experience by making a player-bar
* Make the seek-bar and volume-bar functional

## Solution
### Phase 1
BlocJams didn't respond to changes in screen-size nor did it respond well to scrolling. We used transitions and transition-delays to make the homescreen react to the users scoll. Then @media declarations were used to account to changes in the viewers screen-size.  
### Phase 2
At first, the collections page would only display the two albums we had entered, as static elements. To make the page react to changes in the amount of albums we used the following code
'''jQuery
$(window).load(function() {
    var $collectionContainer = $('.album-covers');
    $collectionContainer.empty();
  for (var i = 0; i < 12; i++) {
      var $newThumbnail = buildCollectionItemTemplate();
      $collectionContainer.append($newThumbnail);
  }
});
'''
Now, in order to update the amount of albums shown on the collections page you only have to change one small part of the code.
### Phase 3
The albums page only had the names of the songs listed, as you can see in this screenshot of the old webpage. ![Old BlocJams](img/oldbloc.png). To make this page functional we had to make a clickHandler function along with onHover and offHover functions that would update the song number to a play or pause button. Once done with these implementations the albums page looked like this ![New album page](img/newalbum.png).
### Phase 4
To make the overall experience more user friendly the website needed a player-bar, where the user could easily pause songs, skip songs, control volume, and even skip to a certain point in the song. I will discuss this process more later but for now here is a look at the completed albums page. ![Final Albums page](img/finalalbum.png).

## Results
For the most part all the solutions implemented throughout this project worked just fine. However, I did run into few problems. The first, and probably most time-consuming was a problem with the styling of the play and pause buttons in the albums webpage. The play and pause buttons were appearing in the upper left portion of the circle instead of in the center. After a lot of reviewing I discovered the issue wasn't in a typo. And after more searching it was apparent the issue was in having multiple CSS rules for the same selector. I had contradicting rules causing the buttons to be off-center.
To make the player-bar we had to create a class for it, along with everything that would be displayed (play/pause button, seek-bar, volume-bar). A very difficult part of this was getting the seek-bar and volume-bar to react to the song. For this we had to get the exact length and position of the seek-bar and the button in the seek-bar, then turn the length of the song into a percentage.

## Conclusion
Going into the project I was very confident in my ability to create a webpage using html and CSS, but I wasn't so sure of my javascript skills. But as the project progressed and we got deeper into javascript and its different functions I felt like I got comfortable with it. Surprisingly most of the problems I ran into had to do with typos in my HTML or CSS. From that I learned I need to slow down even if I think it's something I feel very confident doing. I learned it's very easy to make mistakes. 
