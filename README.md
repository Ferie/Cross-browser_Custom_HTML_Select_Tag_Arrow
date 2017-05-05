# Cross-Browser Custom Select Tag Arrow

### Custom Cross Browser Drop-down

Have you ever faced the problem that the **HTML tag `select` has with its default arrow appearance on different browsers**? Especially on the older Internet Explorers?

Well, if the answer is "YES", or maybe you want a **drop-down arrow that appear the same** in each browsers (including the old ones), here there is an easy trick.

You can find all the CSS code and some examples in this repository.

### *It's all CSS, no JavaScript needed!* ###

See the [Custom Cross Browser Drop-down in action](http://riccardoandreatta.com/web-app/HTML_Select_tag_custom_arrow/HTML_Select_tag_custom_arrow_-_Example.html) with all your browsers!!!



### Drop-down Arrow for Chrome, Firefox, Opera, Internet Explorer 10+

For these browser, it is easy to *set the same background image for the drop-down* in order to have the same arrow.

To do so, you have to reset the browser's default style for the `select` tag and set new background rules.
```
select {
	/* you should keep these firsts rules in place to maintain cross-browser behaviour */
	-webkit-appearance: none;
	-moz-appearance: none;
	-o-appearance: none;
	appearance: none;
	background-image: url('<custom_arrow_image_url_here>');
	background-position: 98% center;
	background-repeat: no-repeat;
	outline: none;
	...
}
```

The `appearance` rules are set to none to reset browsers default ones, if you want to have the same aspect for each arrow, you should keep them in place.

The `background` rules in the examples are set with SVG inline images that represent different arrows. They are positioned 98% from left to keep some margin to the right border (you can easily modify the position as you wish).

In order to maintain the correct cross-browser behavior, the only other rule that have to be left in place is the `outline`. This rule resets the default border that appears (in some browsers) when the element is clicked. All the others rules can be easily modified if needed.

See the `custom-dropdown.css` file for more details about the other rules and examples.



### Drop-down Arrow for Internet Explorer 8 (IE8) and Internet Explorer 9 (IE9) using Icon Font

This is the harder part... Or maybe not.

There is no standard rule to hide the default arrows for these browsers (like the `select::-ms-expand` for IE10+). The solution is to **hide the part of the *drop-down* that contains the default arrow** and insert an arrow icon font (or a SVG, if you prefer) similar to the SVG that is used in the other browsers (see the `select` CSS rule for more details about the inline SVG used).

The very first step is to set a class that can recognize the browser: this is the reason why I have used the conditional IE IFs at the beginning of the code. These IFs are used to attach specific classes to the `html` tag to recognize the older IE browser.

After that, every `select` in the HTML have to be wrapped by a `div` (or whatever tag that can wraps an element). At this wrapper just add the class that contains the icon font.
```
<div class="selectTagWrapper prefix-icon-arrow-down-fill">
	...
</div>
```

In easy words, this wrapper is used to simulate the `select` tag.

To act like a drop-down, the wrapper must have a border, because we hide the one that comes from the `select`.

Notice that we cannot use the `select` border because we have to hide the default arrow lengthening it 25% more than the wrapper. Consequently its right border should not be visible because we hide this 25% more by the `overflow: hidden` rule applied to the `select` itself.

The custom arrow icon-font is placed in the pseudo class `:before` where the rule `content` contains the reference for the arrow (in this case it is a right parenthesis).

We also place this arrow in an absolute position to center it as much as possible (if you use different icon fonts, remember to adjust them opportunely by changing top and left values and the font size).
```
.ie8 .prefix-icon-arrow-down-fill:before,
.ie9 .prefix-icon-arrow-down-fill:before {
	content: ")";
	position: absolute;
    top: 43%;
    left: 93%;
    font-size: 6px;
	...
}
```

NOTE: it is not possible, to change the `option` styles for browsers like IEs Chrome and Opera. Especially for the IEs there will be always an awful black border around the options box, when the drop-down is open.



---

You can easily create and substitute the background arrow or the icon font arrow, with every one that you want simply changing it in the `background-image` rule or making a new icon font file by yourself.
