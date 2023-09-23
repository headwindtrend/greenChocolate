# greenChocolate
Drag a youtube thumbnail/link and drop it into the greenChocolate playground which is a temporary "playlist" of your choices.

if you got tens or even hundreds of videos flood into your youtube subscription feed everyday, you probably want to prioritize them a bit so that your limited free time can be spent on those favorites of higher priority (important, longing for, eye-catching, interesting, and whatever else it might be.) greenChocolate is the playground to hold the choices you picked from your subscription feed (or wherever it may be, as far as the thumbnail/link you are about to drag&drop is a youtube video.)

greenChocolate's advantages over an ordinary youtube playlist are:
1. the videos will not start playing automatically one by one (yes, this is indeed an advantage sometimes, if not most of the time);
2. since the videos will not be played one by one automatically, the order doesn't really matter. scroll through the list and just play them in whatever order you like, hence less burden in the picking process nor need to reorder them on the playlist before you can start playing;
3. as soon as you drop the payload, the video is loaded in an embedded form (and it is much faster than loading the whole youtube video page);
4. by the time you finished your picking, all the chosen videos are ready to play, no wasting time in page-loading of each and every video;
5. every video is maximized which utilizes full size of your window.

i've tested it in win10 msedge and android google chrome, both worked fine. (my galaxy device does let me drag&drop across windows, that's the prerequisite, unfortunately, for android browsers to use greenChocolate.)

change log:
* 2023 Sep 23&nbsp;&nbsp;&nbsp;&nbsp;a new branch `With the logging sub-system` is created out of `main`.
* 2023 Sep 16&nbsp;&nbsp;&nbsp;&nbsp;added two behaviors: (1) after a drag event has caused the appearance of the green board, the script will see if at least a part of the green board is visible in the viewport. and in case of "none of it is visible", the viewport will be scrolled to the top (to show the green board) automatically. and (2) after a video is inserted due to a drop event, the viewport will be scrolled to the top (to show the newly added video) automatically.
* 2023 Sep 14&nbsp;&nbsp;&nbsp;&nbsp;added a logo for greenChocolate.
* 2023 Sep 13&nbsp;&nbsp;&nbsp;&nbsp;added two features: (1) autosave, which will make a copy of all the id's of the videos currently on the playground. autosave will take place after a drop video event happened or a remove video action taken. and on every start of a session (load the page/html or refresh the page/html), the autosaved copy will be checked. and if anything exists there, the system will ask if you want to bring it back. and please be aware that since the autosaved copy is kept in `localStorage`, it's domain oriented. essentially, different domains can have different set of autosaved copy. (2) added a click event handler for the green board, so that you can click it away in case of the green board didn't go away automatically somehow.
* 2023 Sep 05&nbsp;&nbsp;&nbsp;&nbsp;added a hidden feature for video removal. now, right click the text (those "white on chocolate" below) can remove the respective video from the webpage. with this hidden feature, even if the green spot is unavailable (as when greenChocolate is loaded from an html file), user still has a way to remove the video. as a drawback of this, if you somehow need to open the context menu of the text (for instance, to copy it), you have to select it and right click on an empty space (for instance, the chocolate area immediately next to the text). because if you right click on the text, this video removal hidden feature will be triggered instead.
* 2023 Aug 27&nbsp;&nbsp;&nbsp;&nbsp;changed the method in regexp matching so that the script (i.e. the html) can be loaded from local storage (for instance, anywhere in c:) even though it will lose the feature "video removal" the green transparent spot, but at least everything else will work.

how to open up greenChocolate playground:
1. open up your youtube subscription feed page (or any of the youtube pages that has video thumbnails/links that you want to pick) in browser;
2. use any method that you know of to open a document out of the youtube webpage and write the javascript for greenChocolate to that new document. for instance, by using this javascript statement `open().document.write()`.
3. if you don't mind ~~the lacking of the video removal feature~~to use a relatively inconvenient and counterintuitive way to remove video (or never bothered to remove video), you may simply save the script to a file and load the file in browser.

operation notes:

greenChocolate has a background in chocolate, and upon your drag operation pointer hit destination (entered the window and over chocolate), a green board will appear (which should cover the whole window) therefore you can release your mouse button to drop it onto the playground. the drop process will always put the video to the top of the list. every video has a green transparent spot on its top-right corner for the removal of the respective video from the playground. and the size of the spot is good enough for touchscreen operation. the green board will always appear at the very top of the list, so there is a "jump to the top" transparent icon to help you get back if you scrolled down anywhere. ~~you may want to click/tap the icon everytime before you drag&drop video into the playground.~~

if your drag operation pointer hit destination but the green board doesn't appear, just move it away your window and move it back in. if you did it a number of times and still hasn't able to trigger the green board to appear, try slow down your movement because sometimes the operating system may miss the event if you move too fast. still not make it? the last resort is, just move it on top of the chocolate edges which works all the times. the edges are relatively thin and not ideal for the operation though. another way is, scroll down a bit until the text on chocolate background is shown, redo the drag&drop, and move your pointer on top of anywhere with chocolate background that the green board will certainly appear (at least i have never experienced a fail so far), this is easier than catching the edges. having mention all these troublesome techniques, but they are really seldom needed.

avoid to drag across the handle (the three dots) of the windows splitter in android. because i found it "prevented" the event listener from noticing the `dragenter` event that did happen.

how to put a recommended video onto greenChocolate:

first of all, i found that this requires different techniques for different scenarios.

when the green transparent spot is shown, the drag of the recommended video thumbnail will trigger the appearance of the green board. so, it works on its own. and if it doesn't, just drag the payload away the playground and back in. that does the trick to grab the attention of the event listener.

when the green transparent spot is not shown (it happens when the playground was not created out of a youtube webpage), the drag of the recommended video thumbnail does not trigger the appearance of the green board at all even if i drag the payload away and back in. however, there is a way to get it around, that is, to drop it on the address bar and drag it back into the playground thereafter.

when i mentioned the "recommended video" above, it referred to those videos thumbnails that youtube presents you by its algorithm after you played a video on the greenChocolate playground.

here below is the documentation written by bing-ai.

## Overview
This script allows users to drag and drop YouTube video links onto a webpage, and it will automatically embed the video into the page. It also provides an option to remove the embedded video.

## Advantages of GreenChocolate Over a Traditional YouTube Playlist

GreenChocolate offers several benefits compared to a standard YouTube playlist:

1. **No Auto-play**: Videos won't automatically play one after another. This can be an advantage when you want more control over what plays next.
2. **Flexible Order**: Since videos don't auto-play, the order of videos doesn't matter. You can scroll through the list and play videos in any order you like, reducing the need to carefully curate the playlist order.
3. **Fast Loading**: When you drop a video into the playground, it loads in an embedded form, which is much faster than loading the entire YouTube video page.
4. **Pre-loaded Videos**: By the time you finish selecting your videos, all chosen videos are ready to play, saving you from waiting for each video to load.
5. **Maximized Videos**: Each video is maximized to utilize the full size of your window.

## Operating Instructions for GreenChocolate

GreenChocolate is a tool designed for managing videos. Here’s how you can use it:

1. **Drag and Drop:** To add a video to the playground, simply drag it over the chocolate background. When your cursor enters the window over the chocolate, a green board will appear, covering the entire window. You can then release your mouse button to drop the video onto the playground. The video will be added to the top of the list.

2. **Removing Videos:** Each video has a green transparent spot in its top-right corner. Clicking this spot will remove the respective video from the playground. The size of the spot is designed for easy touchscreen operation.

3. **Navigating the Playground:** The green board always appears at the top of the list. If you’ve scrolled down, you can use the “jump to the top” transparent icon to quickly return to the top.

4. **Troubleshooting:** If you’re having trouble triggering the green board to appear, try moving your cursor away from the window and then back in. If this doesn’t work, try slowing down your movement as moving too quickly can sometimes cause the operating system to miss the event.

5. **Adding Recommended Videos:** The process for adding recommended videos (those suggested by YouTube’s algorithm after playing a video) varies between scenarios:

   - **With the green spot:** Simply drag the thumbnail of the recommended video onto the playground. If this doesn’t trigger the green board, try dragging it away from and back into the playground.

   - **Without the green spot:** Dragging a thumbnail does not trigger the green board. However, you can work around this by dropping it onto the address bar and then dragging it back into the playground.

Please note that dragging across the handle (the three dots) of the windows splitter in Android may prevent the dragenter event from being noticed.

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
