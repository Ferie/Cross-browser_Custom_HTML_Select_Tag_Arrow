# Cross-browser Custom Select Tag Arrow

Have you ever faced with the problem that the **HTML tag *select* has with his arrow on different browsers**, especially on older Internet Explorer ones?

Well, if the answer is "YES", or maybe you want a **select arrow that appear the same** in every most famous browsers and in the old ones, here there is an easy trick.

You can find all the CSS and HTML code in the example file in this repository.

######*It's all CSS, no JavaScript needed!*######

(NOTE: I have put all the CSS and HTML code in the same file because it is only a very simple and easy to understand example).



### Chrome, Firefox, Opera, Internet Explorer 10+ Custom Select Tag Arrow

For these browser, it is easy to **set the same background for the *select* tag** in order to have the same arrow.

To do so, you have to reset the browser's default style for the *select* tag and set the custom background with the arrow.

See the example file for more details about the CSS rules.



### Internet Explorer 8 (IE8) and Internet Explorer 9 (IE9) Icon Font Custom Select Tag Arrow

This is the hardest part, or not?

The solution is to **hide the part of the *select* tag that contains the default arrow** and put an icon font similar to the custom that I have created for the other browsers.

The very first step is to set a class that can recognize the browser: this is the reason why I have used the conditional IE IFs at the beginning of the code.

After that, evry *select* tag in the HTML have to be wrapped by a *div* (or whatever tag that can wraps an element). At this wrapper just add the class that contain the icon font.

In easy words, this wrapper simulates the *select* tag and is used only for these IEs browsers. This is the reason why in the css rules, you have to specify the classes that you have put at the beginning of the HTML.

To act like a *select* tag, this wrapper has a border and his *:before* must have the rule *content* that contains the icon font reference.

The *select* CSS rules hide the border (because we use the wrapper one) and put a width a 20% longer than the wrapper, to do so the default arrow may be hidden by the *overflow* rule that has to be set for the wrapper.

Finally, set (or adjust) the arrow position, if needed.



----------

NOTE: You can easily create and substitute the background arrow and the icon font arrow with every one that you want simply changing it on the *background-image* rule or making a new icon font file by yourself.
