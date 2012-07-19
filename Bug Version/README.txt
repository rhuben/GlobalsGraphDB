This is a version of the graphDB that shows the error I have run into. Note that most of the code here is superfluous, including just about all of the graph class.

For me, when I run the program in Node.js, it gets to i=169 and then a window pops up saying "Evented I/O for V8 JavaScript has stopped working".
 Interestingly, if I change the line <code> subscripts:[i, i], </code> to <code> subscripts:[i], </code>, it goes until i=255, and if I change that line to
<code> subscripts: i, </code> it runs until i=511.

I started running into this problem when I was installing cache. In particular, I changed some of my environment variables. Here is a chart comparing the values:


Variable		Old Value		New Value
GLOBALS_HOME		C:\Globals		C:\Intersystems\Cache
globalsroot		C:\Globals		C:\Intersystems\Cache
Path			...C:\Globals\bin...	...C:\Intersystems\Cache\bin...


Before these changes, this code would have run without the bug.