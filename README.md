# Cross-browser Custom Select Tag Arrow

Have you ever faced with the problem of cross-browsing that the HTML tag "select" has with his arrow especially on older Internet Explorer browsers?

Well, if the answer is "YES", or maybe you want a select arrow that appear almost the same as the Chrome's HTML Select tag arrow on these old browsers, here there is an easy trick.

It's all CSS, no JavaScript!



# Chrome, Firefox, Opera, Internet Explorer 10+ Custom Select Tag Arrow

For these browser it is easy to set the same background, so the arrow can be the same.

To do so, you have to reset the browser's default style for the HTML select tag and then set the background.

See the example file for more details about the code.
(NOTE: I have put all the code in the same file because it is only a simple example).



# Internet Explorer 8 (IE8) and Internet Explorer 9 (IE9) Icon Font Custom Select Tag Arrow

This is the hardest part, or not?

The solution hide the part of the select tag that contain the default arrow and put an icon font similar to the the custom that I have created for the other browsers.

The very first step is to set a class that can recognize the browser: this is the reason why I have used the conditional IE IFs at the beginning of the code.

After that, evry select tag in the code have to be wrapped by a 'div' or whatever tag that can wrap an element.

This wrapper is used only for these browsers so, in the css, you have to specify the class that you have put at the beginning to simulate the select on this wrapper.

Add the class that contain the icon font to this wrapper.

Last point is to set (or adjust) the custom arrow made by icon font in the CSS.




NOTE: You can easily create and substitute the background arrow and the icon font arrow with every one that you want simply changing them or making a new ones by yourself.
