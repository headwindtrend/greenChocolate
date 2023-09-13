# greenChocolate
Drag a youtube thumbnail/link and drop it into the greenChocolate playground which is a temporary "playlist" of your choices.

if you got tens or even hundreds of videos flood into your youtube subscription feed everyday, you probably want to prioritize them a bit so that your limited free time can be spent on those favorites of higher priority (important, longing for, eyecatching, interesting, and whatever else it might be.) greenChocolate is the playground to hold the choices you picked from your subscription feed (or whereever it may be, as far as the thumbnail/link you are about to drag&drop is a youtube video.)

greenChocolate's advantages over an ordinary youtube playlist are:
1. the videos will not start playing automatically one by one (yes, this is indeed an advantage sometimes, if not most of the time);
2. since the videos will not be played one by one automatically, the order doesn't really matter. scroll through the list and just play them in whatever order you like, hence less burden in the picking process nor need to reorder them on the playlist before you can start playing;
3. as soon as you drop the payload, the video is loaded in an embeded form (and it is much faster than loading the whole youtube video page);
4. by the time you finished your picking, all the choosen videos are ready to play, no wasting time in page-loading of each and every video;
5. every video is maximized which utilizes full size of your window.

i've tested it in win10 msedge and android google chrome, both worked fine. (my galaxy device does let me drag&drop accross windows, that's the prerequisite, unfortunately, for android browsers to use greenChocolate.)

change log:
* 2023 Sep 13&nbsp;&nbsp;&nbsp;&nbsp;added two features: (1) autosave, which will make a copy of all the id's of the videos currently on the playground. autosave will take place after a drop video event happened or a remove video action taken. and on every start of a session (load the page/html or refresh the page/html), the autosaved copy will be checked. and if anything exists there, the system will ask if you want to bring it back. and please be aware that since the autosaved copy is kept in `localStorage`, it's domain oriented. essentially, different domains can have different set of autosaved copy. (2) added a click event handler for the green board, so that you can click it away in case of the green board didn't go away automatically somehow.
* 2023 Sep 05&nbsp;&nbsp;&nbsp;&nbsp;added a hidden feature for video removal. now, right click the text (those "white on chocolate" below) can remove the respective video from the webpage. with this hidden feature, even if the green spot is unavailable (as when greenChocolate is loaded from an html file), user still has a way to remove the video. as a drawback of this, if you somehow need to open the context menu of the text (for instance, to copy it), you have to select it and right click on an empty space (for instance, the chocolate area immediately next to the text). because if you right click on the text, this video removal hidden feature will be triggered instead.
* 2023 Aug 27&nbsp;&nbsp;&nbsp;&nbsp;changed the method in regexp matching so that the script (i.e. the html) can be loaded from local storage (for instance, anywhere in c:) even though it will lose the feature "video removal" the green transparent spot, but at least everything else will work.

how to open up greenChocolate playground:
1. open up your youtube subscription feed page (or any of the youtube pages that has video thumbnails/links that you want to pick) in browser;
2. use any method that you know of to open a document out of the youtube webpage and write the javascript for greenChocolate to that new document. for instance, by using this javascript statement `open().document.write()`.
3. if you don't mind the lacking of the video removal feature (or never bothered to remove video), you may simply save the script to a file and load the file in browser.

operation notes:

greenChocolate has a background in chocolate, and upon your drag operation pointer hit destination (entered the window and over chocolate), a green board will appear (which should cover the whole window) therefore you can release your mouse button to drop it onto the playground. the drop process will always put the video to the top of the list. every video has a green transparent spot on its top-right corner for the removal of the respective video from the playground. and the size of the spot is good enough for touchscreen operation. the green board will always appear at the very top of the list, so there is a "jump to the top" transparent icon to help you get back if you scrolled down anywhere. you may want to click/tap the icon everytime before you drag&drop video into the playground.

if your drag operation pointer hit destination but the green board doesn't appear, just move it away your window and move it back in. if you did it a number of times and still hasn't able to trigger the green board to appear, try slow down your movement because sometimes the operating system may miss the event if you move too fast. still not make it? the last resort is, just move it on top of the chocolate edges which works all the times. the edges are relatively thin and not ideal for the operation though. another way is, scroll down a bit until the text on chocolate background is shown, redo the drag&drop, and move your pointer on top of anywhere with chocolate background that the green board will certainly appear (at least i have never experienced a fail so far), this is easier than catching the edges. having mention all these troublesome techniques, but they are really seldom needed.

here below is the documentation written by bing-ai.

## Overview
This script allows users to drag and drop YouTube video links onto a webpage, and it will automatically embed the video into the page. It also provides an option to remove the embedded video.

## Functions

- `drop(event)`: This function is triggered when a drop event occurs. It extracts the YouTube video ID from the dropped data and creates an iframe to embed the video into the webpage. It also removes the drop box after embedding the video.

- `allowDrop(event)`: This function is triggered when a dragover event occurs. It prevents the default handling of the event.

- `rmvifrm()`: This function removes an iframe (and its associated description) from the document when a user clicks on a green circle that appears in the top right corner of the embedded video.

- `createDropBox()`: This function creates a drop box (a green rectangle) that covers the entire webpage when a dragenter event occurs.

- `removeDropBox()`: This function removes the drop box from the webpage.

## Usage
To use this script, simply drag and drop a YouTube link onto any webpage where this script is included. The video will be automatically embedded at the top of the page. To remove an embedded video, click on the green circle in the top right corner of the video.

Please note that this script assumes that YouTube URLs are in one of these formats:
- `https://www.youtube.com/watch?v=<video_id>`
- `https://www.youtube.com/shorts/<video_id>`
