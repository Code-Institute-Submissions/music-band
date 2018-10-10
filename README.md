# Music Band - HTML & CSS Project

---

*For this first milestone project:*

I decided to continue with the suggested theme of a music band and have chosen the band "Queens of the Stone Age".

I decided early on how I wanted my project to look, which technologies I was going to use and what should be included in a website of this category type. I have created this project with no JavaScript or other libraries, which while proving a challenge at times, enabled me to think outside the box when implementing certain features and showcases my understanding of the relationships between elements. 

Ultimately, my overall goal was to create a functional, modern and user friendly site, which loads quickly, is responsive on devices on all sizes and provides a good user experience which is both easy to navigate and informative.

--- 
 
## UX

---
 
### Who this site is for and how it can help them

This site is intended for fans of the band. It's theme is based on aspect of promoting the bands tour and new album release.

When deciding upon a ux layout I wanted to put myself in the position of the end-user and ask the essential questions such as:

- *Why* am I going to this website and what reason would I have to go there?
- *What* information should I expect to find?
- *When* I first load the website, how likely am I to stay, does the initial first paint grab my attention?
- *Can* I get to where I want to go easily and at a glance figure out how to get there?
- *Does* the website contain common features I'd expect to find on any other music bands website?
- *Did* the website fulfil my expectations and needs?

To answer these questions I first browsed a number of high profile music band websites to look for common patterns and features and how they applied to different screen sizes. I also browsed on awwwards.com to get an understanding of the kind of layouts that were common in a music category. I also had to take into consideration that not using any JavaScipt would affect how content could be presented and find solutions to issues such as mobile navigation.  

I decided on the number of pages and amount of content I would have, created basic wireframe ideas and set upon creating an empty project skeleton to build on. When deciding on the content type, I set myself the below user stories as a base line to work from.

#### User Stories:
- As a user, I can immediately understand who the website is about and it's purpose.
- As a user, I can easily understand the navigation and layout structure to find my way around the website.
- As a user, I expect the website to load quickly, while still remaining modern.
- As a user, I can expect to find the information most associated with a music bands website.
- As a user, I can see the bands latest news and find links to follow them on their social media.
- As a user, I can find links to buy their music and merchandise, see tour dates and subscribe to a fan newsletter.
- As a user, I can see images and videos relating to the band.
- As a user, I can hear a preview of the bands music.


![index](https://github.com/nazarja/music-band/blob/master/assets/wireframe/index.png)
![store](https://github.com/nazarja/music-band/blob/master/assets/wireframe/store.png)
![media](https://github.com/nazarja/music-band/blob/master/assets/wireframe/media.png)
![tour](https://github.com/nazarja/music-band/blob/master/assets/wireframe/tour.png)
![newsletter](https://github.com/nazarja/music-band/blob/master/assets/wireframe/newsletter.png)
![mobile-menu](https://github.com/nazarja/music-band/blob/master/assets/wireframe/mobile-menu.png)

---

## Technologies Used

---

I choose not to use bootstrap and instead focus on custom pure css, css grid and flexbox. The reasons being that:

- I wanted to set my own breakpoints as to when the content needed it, not based on common screen sizes.
- Bootstrap applies many default styles which I would need to override.
- I wanted to showcase my ability and understanding of css and the box model, grid system, media queries and relationship between elements.
- CSS Grid and flexbox adequately suited my needs with minimal code
- I could create my own classes and rules to be used amongst multiple components/elements. 

---

## Features

---

### Color Scheme

The sites color scheme takes inspiration from the bands new album logo which comprises and blue, black and white. I wanted to implement these colors site wide in a minimal fashion. These colors would be applied to buttons, backgrounds and fonts.

### Navigation

The navigation proved to be tricky. I revisited this feature a number of times to edit and make adjustments. The mobile menu needed a way to open and close. I decided upon the checkbox hack where the checkbox toggle event would trigger a hidden menu to slide in. The checkbox would be hidden offscreen and the label would be clicked to activate the menu. 

In desktop mode, I applied an animation to the menu item for visual purposes. Originally I had a hover menu for the social media links but the html validator didn't approve of a div within an ul although the browser rendered it fine, so these feature was removed. 


#### Index / Main Header

I wanted to to provide some sort of full screen slideshow, without JavaScript this feature was achieved by two images on top of one another. The image on the bottom is always there, the image on top fades in and out of opacity with a css keyframe animation. Another layer was placed on top with a gradient color to make any text more legible.   

#### Index / HTML Audio

Creating the audio feature was also a bit of a challange. firstly as to not infringe on any copyright, I downloaded an official album preview from soundcloud which feature the first 20 secs of each song on the album. Which went perfectly with the websites theme of promoting a new tour / new album. I wanted to implement a custom audio player, but without JavaScript I was limited to the default browser html5 audio element. The challange here was to fit the style of the audio element in with the websites theme. With each browser providing their on style, with a css rule I targeted webkit browsers and set the color of the background div to that of webkits audio element. The default div background color would be set similar to firefox's audio element. With microsoft edge taking a hit on this one. I would assume most users of the bands target age group would be using either chrome, safari, brave (all webkit) or safari browsers. 

#### Index / Creative Section

For this section I took to gimp to isolate an image from the bands previous artwork. This section required multiple breakpoints to grow and shrink with the layout properly. Revisited a few times to cut down on code wile still maintaining a good look. 

### Store Page

This section was quick and easy to implement with the longest part collecting the correct links to each retailer for an album.
I used CSS Grid for the entirety of the content. Only adjusting breakpoints when the content need it. All links are valid and open in a new tab.

An issue I encountered was that I was linking to images on google play which are in webp format, which seems to be only supported by chrome. The solution was to download and convert the images to a more universal format such as jpg or png and serve the images locally instead.

### Media Page

This page implements flexbox with was perfect for resizing images and arranging columns.
I wanted a mosaic look for the photographs and found a good solution of w3 schools to which I could adapt to my section. The Photos are arranged in 4 columns with the images set to 100% width. Breakpoints stack two and all columns on top of each other respectively. Images are directly from qotsa.com. One issue I had was with page load speed, So I decided to download the images instead of lining to them. Then reduce the file size to what would be there maximum width. This reduced the image sizes and load time considerably.

Videos are YouTube embeds, A way of making these responsive comes with the YouTube embed code. Padding = 56.21%. To further add more videos on the same row, this number was halved and quartered. The videos now resize perfectly.

### Tour Page

This page provides information to a user about upcoming live dates and is tickets are available a link to ticketmaster.
The main content is a form with dummy data taken from the nine inch nails website, as queens of the stone age are not currently on tour.

An issue I had to resolve was as the tour dates feature was made with a table, when resizing to mobile width the table was far too wide and required a solution. CSS tricks had a good article which I could adapt to my own table. This involved a desktop first approach and on mobile screens treating the table as block element and applying a `:before` and `td:nth-of-type` selector on the td to insert the heading adjacent to the information. Otherwise it would be unclear what the information was referring to.

### Newsletter Page

The newsletter page is a simple form using semantic form elements and resizing accordingly for different widths. Most form elements have a required attribute for html5 validation although unfortunately as no backend or JavaScript being available the form simply redirects to a thank you page.

---

## Testing

---

Throughout the entire project build I was conscious and constantly testing each new feature after was created to check for consistency across browsers and different screen sizes. I was also concerned with page speed and regularly used google lighthouse to audit performance and page speed.

I have tested the code on the **W3C** website using both the html and css validator. The only real issue I can find is that the css validator is throwing an error on the use of css variables which I understand to be valid css, so I have ignored this as a false error.


My main tool was using chromes dev tools device toolbar to simulate various devices and responsive mode to check for when the content required breakpoints. At the end of each page I uploaded the site to my personal portfolio site and tested and both android and iphone using safari, chrome and firefox browsers. Revisited any code which needed adjustment and tried to find a solution which was acceptable for all browsers. 

I have also asked my family members for they're feedback and how they found the site in general and whether they would change anything or found something difficult to use or confusing.

Overall I'm happy with the final outcome and even though browsers do all render differently, I think I have found a happy medium between them. One such issue is form items and font rendering which both need to be adjusted.

---

## Deployment

---

Throughout the process I have built my project locally using vs code as my editor and chrome as my preferred browser. I also have firefox open to check for consistency. I have regularly tracked my files, made local git commits and pushed to my github repository.

The primary site as requested in the instructions is hosted at [https://nazarja.github.io/music-band/index.html](https://nazarja.github.io/music-band/index.html).

I have also deployed the website to my personal website via file transfer and it is currently viewable at [http:seanmurphy.eu/music-band](http:seanmurphy.eu/music-band).

All code is viewable at my github repository at [https://github.com/nazarja/music-band](https://github.com/nazarja/music-band).

---

## Credits

---

### Content

- Text for the live tour dates form was copied from [http://www.nin.com/live/](http://www.nin.com/live/) as the official queens of the stone age website has no tour data.
- Text on the Index page / Creative section was copied from a Queens of the Stone Age Artwork Cover - which is related to the image opposite the text.
   

### Media

- The photos in this project were obtained from the official Queens of the Stone Age website, and some from a google photos search.
- Album images are from Google Play
- Videos are embedded from YouTube
- Audio is from Soundcloud

### Acknowledgements

- I received inspiration for this project from many online sources, mainly as to different ideas on layout and what would be typical content for a music website.

*Sites included:* 

awwwards.com , pearljam.com, nin.com, qotsa.com

Also a google search for the best music websites!
