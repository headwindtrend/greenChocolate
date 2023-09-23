# greenChocolate
for those things outside of the logging sub-system, please refer to the readme of `main` or other branches (if there are any in the future).

## this is a sub-system of greenChocolate for logging.

### what data will be logged?
1. date and time of every drop event happened
2. date and time of every remove action taken

### how about the logging of the play-video event?
- logging of the date and time of a play event is possible, but it depends on how you invoked the play. the date and time of a play will be logged only if you invoke it by rightclicking the green transparent spot (if the green transparent spot is unavailable, clicking the pointing-up hand in the description (the white text on chocolate below the video) can log the date and time as a play event, though it cannot actually invoke the play automatically thus you have to invoke it separately this way. besides, there is one more difference between rightclicking of the green transparent spot and clicking of the pointing-up hand, that is, the former can also capture the video title, channel name, and video length for the logging, whereas the latter cannot.)

### how to show/hide the logged records?
- by doubleclicking anywhere with chocolate background, or by the hotkey `ctrl+;`.

### how to show the activities (all the logged events) of a particular video?
- by highlighting (selecting) the video id on the log. if the video id doesn't contain a hyphen, you may highlight it by doubleclicking it. as soon as the video id is highlighted, the respective video thumbnail will be shown with all of its activities grouped below. you may select/unselect (mark/unmark) these activities on the log by the button on the bottom-left corner.

### can i drag the thumbnail and drop it back to the playground?
- yes, you can if you want to.

### how to dismiss the video thumbnail?
- by a single click anywhere except the buttons or any "vehicles" for particular purposes.

### how to remove any records on the log?
- there is a white circle in front of every line (i.e. every record) if it is not marked. otherwise, a black circle if it is marked. whenever there is any lines being marked, the `R` button will appear, click it to get rid of all the marked lines.

### how to mark/unmark any records on the log?
- **for one single line**, by highlighting the entire line (including the circle mark), or tripleclicking anywhere on the line (except the video id, because it may trigger the video thumbnail instead.)
- **for a range of consecutive lines**, by highlighting those targeting lines. as soon as the highlighting operation is completed, all the marks (i.e. the black/white circles) within the highlighted range will be toggled. you may also toggle all by the hotkey `ctrl+a`. for example, let's say you have 5000 lines in the log, and you want to delete all of them except the recent 100 lines. you may `ctrl+a` to highlight all (thus all the lines are marked as a result), and select the last 100 lines to unmark them, and finally click the `R` button to proceed remove.

**note:** the "highlighting" i mentioned above means an ordinary text selection operation, which starts by moving your mouse to the beginning of the range, and press and hold the mouse button, and drag to the end of the range, and complete it by releasing the mouse button.
