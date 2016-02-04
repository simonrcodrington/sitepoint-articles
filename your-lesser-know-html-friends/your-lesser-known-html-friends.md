


#Your lesser known HTML friends. 

When work on your latest up and coming site you probably use a whole range of different tags to piece it all together. 

While there are a heap of different tags out there, you will probably all be familiar with some of the new tags introduced in HTML5 such as `<article>`, `<header>`, `<footer>` etc.  What you mightn't be aware about are some of the lesser known / edge case tags you could be taking advantage of.  

Some of these tags are either brand new in HTML5 or have been re-purposed from the HTML4 specification (changing their meaning and how they should be used). 

For each tag we will go through what the W3C specification says and apply a practical example to showcase how you might use it. Lets roll! 

###A quick word on interpretation
While the W3C specifications are great for conceptual overviews, sometimes they lack any solid practicality. The lack of real world examples / common uses has meant for that some of these tags it's hard to find out what is the **proper** way to use them.

You might have used some of these tags before and perhaps not in the same way. There often isn't any hard and fast rules about what is considered **good practice** . These are how I treat and use these elements. 



##1 - Contextual highlighting with `<mark>`
The [specification for the  `<mark>` tag](https://www.w3.org/TR/html5/text-level-semantics.html#the-mark-element) says that this tag should be used to denote *'relevance' or 'scrutiny'*. 

'Relevance' is hard to describe but overall elements / text are relevant when we are performing an activity and they are useful to us right now (or could be useful in the future)

For example, if you searched a site with the keyword "jQuery" and several articles showed up, you could wrap the resulting matches inside the `<mark>` tag. The purpose of the mark tag is to say to the browser *"hey, this thing right here is relevant to what you are doing"*.

###Practical examples

We can use the mark tag for highlighting content that is relevant. To illustrate, consider the following scenario:

We are on a page called 'Cheapest Holiday Packages' and it shows us a grid of holiday packages sorted by price range. It starts off from the cheapest at the top to the most expensive at the bottom. 

For the top level holidays, the price itself could be highlighted with the `<mark>` tag because we have come to this page for cheap holiday deals and these are the cheapest the page has to offer, they are the most relevant. 

```

<section class="deal-list">
	<article>
		<h2>Vanuatu Cruise</h2>
		<mark>$499</mark> - 5 Nights</mark>
		<p>A relaxing cruise around the southern most parts of Vanuatu</p>
	</article>
	<article>
		<h2>Fiji Resort Getaway</h2>
		<mark>$649</mark> - 6 Nights</mark>
		<p>Includes all you can eat buffet and entertainment</p>
	</article>
		<article>
		<h2>Pacific Island Hiking</h2>
		$1199 - 5 Nights</mark>
		<p>Hike your way though several pacific islands on this exercise focused holiday</p>
	</article>
</section>

```

For the first two results the price (which is what we are focused on) is wrapped withing the `<mark>` tag. However the third result, which is much more expensive isn't marked, it isn't as relevant as the others.


###Best Practices and considerations

While people generally associate this tag with a quick way to style something, that isn't correct, it shouldn't be used just for styling (you should be another element like a `<span>` for that). 

Don't use this tag to denote textual importance, that is what the `<strong>` tag should be used for. If you want to highlight strength then use `<strong>`, if you want to pinpoint something of relevance to the current user you should use `<mark>`. 


##2 - Lower Importance with `<small>` 

You've probably used the `<small>` tag before; It does exactly what you think it would do, which is make your text smaller. While browsers might make your text smaller, that is actually a byproduct of using the small tag. 

[The specification for the `<small>` tag](https://www.w3.org/TR/html5/text-level-semantics.html#the-small-element) explains that this tag should be used to lower the importance of text or information. Browsers interpret this by making the font smaller so it has less visible impact. 

This tag should be used to denote **'low importance'** when it comes to content or information.  Information of low importance is generally used in the footer of a website or off in the sidebar (away from the main content of the page). 

###Examples###

Overall your usage of the mark tag should say to the browser *"This content right here isn't really important in the grand scheme of things"*.  For example, in the footer you could use this for your legal attribution and copyright

```
<footer>
	<small>Designed and developed by Simon Codrington. </small>
	<small>&copy; 2016 My Company - All rights reserved</small>
</footer>
```

You can even use the `<small>` tag inside regular content to denote that the content is not as important as the content surrounding it. For example in a product listing, you could include the legal disclaimer "tax not included" near the price of a product as follows


```
<section>
	<article>
		<h3>Woolen Llama Print Jumper</h3>
		<em>$65.99</em><small> - Excludes tax</small>
		<p>A warm, woolly jumper made from 100% llamas. You will love the wamth</p>
		<button>Add to cart</button>
	</article>
</section>

```
Overall if you want to make something have a perceived lower importance use `<small>`; Don't just use it to control the size of elements.

###Best Practices and considerations
You can't lower the importance or emphasis of content that has been affected by the `<strong>` or `<em>` tags. Applying the `<small>` tag might affect its visual look (depending on the browser), but it won't affect its semantics. 



## 3 - Quotations with `<q>` and `<blockquote>`

While you might just used a styled `<div>` or `<span>` to enclose your quotes; A better way is to use either the `<q>` tag or `<blockquote>`. Both of these are meant to be used for external quotations (i.e when your'e quoting something), but they differ in how you should use them.

[According the spec](https://www.w3.org/TR/html5/text-level-semantics.html#the-q-element), the `<q>` tag should be used to define a 'short inline quotation' of text. 

[The `<blockquote>` tag](http://www.w3.org/TR/html5/grouping-content.html#the-blockquote-element) on the other hand should be used for large spans of text. 

In practice you should be using the `<q>` tag for smaller quotes and using `<blockquote>` for everything else. Keep in mind that these are for quotes or resources only, they shouldn't be used just for stylistic purposes (use spans for that).


###Practical Examples
Lets look at how we can use both of these tags. 

If you have a small quote, use `<q>`
```
<div class="big-banner">
	<h2>Try our latest sandwitch!</h2>
	<p>Come and try our latest, biggest and tastiest sandwich. John Smith told us <q>hasn't eaten anything as good in his whole life!</q></p>
</div>
```

If you have a longer quote, or something more complex you can wrap it inside `<blockquote>`

```
<div class="motiviational-quote">
	<blockquote cite="http://www.brainyquote.com/quotes/quotes/b/bradleywhi410518.html">Infuse your life with action. Don't wait for it to happen. Make it happen. Make your own future. Make your own hope. Make your own love. And whatever your beliefs, honor your creator, not by passively waiting for grace to come down from upon high, but by doing what you can to make grace happen... yourself, right now, right down here on Earth.<cite>Bradley Whitford - Author</blockquote>
</div>
```

For the above example we've wrapped a long quote withing the `<blockquote>` tag and supplied both the `cite` attribute (the link to the resource) and the `<cite>` tag (explaining what this resource is). 



###Best practices and considerations
As shown above, both of these quote elements can support the [`cite` attribute](http://www.w3schools.com/tags/att_q_cite.asp) and the [`cite` element](https://www.w3.org/TR/html5/text-level-semantics.html#the-cite-element).  

The cite attribute specifies the URL of the resource itself, for example the link to the website where this quote came from.  The cite tag should be used to specify what exactly this quote is, for example the title of the quote or what type it is. There is some debate as to how the `cite` attribute and the `<cite>` tag should be used, but overall I've always found using them like this works just fine.

##4 - Insertion, Deletion and Correction with `<ins>`, `<del>` and `<s>` 

The `<ins>`, `<del>` and `<s>` tags are useful when you're using dealing with text / content that has been changed or it's relevance has been updated.

[The `<ins>` tag](https://www.w3.org/TR/html5/edits.html#the-ins-element) defines text that has been added to a document, it represents new content. You'd use this tag generally to mark text that has been added / is relevant to a given content. 

[The `<del>` tag](https://www.w3.org/TR/html5/edits.html#the-del-element) defines text that has been removed from the document, it represents deleted content. (Even though it signifies deleted content, it still physically exists in the document). 

These two tags support two optional attributes; The `cite` attribute for linking to a resource that explains this change and also the `datetime` attribute for when this occurred. The datetime must be a [valid datetime string which unfortunately isn't very easy to understand](https://www.w3.org/TR/html5/infrastructure.html#valid-date-string). You can cheat and use a [timestamp generator](http://www.timestampgenerator.com/) if you're in a rush. 


These attributes are useful for when you want to provide context to your additions / deletions. You might see this with update logs / revision lists where an author lists all of their changes and provides resources as to why these changes happened.

[The `<s>` tag](https://developer.mozilla.org/en/docs/Web/HTML/Element/s) is similar but instead defines text that is no longer correct.  This is used to signify to the browser that the wrapped text isn't relevant anymore and is usually followed by its replacement text (for example new content wrapped inside the `<ins>` tag). This tag often renders as strike-through text to show that it's no longer relevant. You shouldn't use this just for stylistic purposes though (you can do this easily enough with `<span>`)

###Practical Examples

Imagine that you have a list of changes to a plugin you're developing. On your release log page you could outline your latest updates using the `<ins>` tag and attributes.

```
<h2>Latest Changes</h2>
<p>Outlined below are the latest changes</p>
<h3>Version 1.X branch</h3>
<ins cite="http://www.johnsmithsblog/changes/1-0-1.html" timestampe="2012-08-09T15:15:00+00:00">Version 1.0.1 - August 2012</ins><br/>
<ins cite="http://www.johnsmithsblog/changes/1-0-2.html" timestampe="2012-11-15T06:15:00+00:00">Version 1.0.2 - November 2012</ins><br/>
<h3>Version 2.X branch</h3>
<ins cite="http://www.johnsmithsblog/changes/2-0-0.html" timestampe="2013-01-17T02:50:00+00:00">Version 2.0.0 - January 2013</ins><br/>

```

Another example that showcases how you can use the `<del>` tag is inside a note taking app. This tag should be used when content no longer exists at all (and isn't being replaced) so it's perfect for that situation.

```
<ul class="to-do-list">
	<li><del datetime="2015-12-03T13:21:32+00:00">Pick up the groceries</del></li>
	<li><del datetime="2015-12-03T15:15:00+00:00">Collect the kids from school</del></li>
	<li>Cook dinner</li>
	<li>Work on fancy side projects</li>
</ul>

```

You can see that two of our tasks have been completed so they have been wrapped with the `<del>` tag. This shows to the user (and the browser) that the content no longer exists. We supplied both with the `datetime` attribute as it's actually a handy piece of data to keep considering we are tracking task completion.


The `<s>` tag is best used for when content has been removed and then updated, for example when correcting documents, 

```
<article class="news-item">
	<h1>WordPress 4.4 Updates</h1>
	<section class="summary">
	WordPress 4.4 (code-named <s cite="https://codex.wordpress.org/Version_4.4"> Bobby Brown</s>Clifford Brown) was released to the public on the 8th of December 2015.
	</section>
	<section class="main-content">
	<p>There were several changes in V4.4 including the following</p>
	<ul>
		<li>New default theme - <s>Twenty Fifteen</s> Twenty Sixteen</li>
		<li>Responsive image support (image elements in the content now support display based rendering)
		<li>Additional embed object support such as Cloudup, Reddit Comments etc</li>
	<ul>
	</section>
</article>

```
In the above example we have corrected several pieces of information, citing a reference URL inside our `<s>` tag where possible. 

##5 - Organising options with `<optgroup>`
This tag is one of the oldest, but oddly enough it's still overlooked by developers.

[The `<opgroup>` tag](http://www.w3.org/TR/html5/forms.html#the-optgroup-element) is used within the `<select>` form control tag to help categorize the various `<options>` elements. 

If you have dozens (or hundreds) of options inside your select field, having the ability to categorize them into some local format is really handy. 

The `<optgroup>` tag must be inside the `<select>` element and contains two attribute; `label`, which acts as the visible label seen when the list is opened and `disabled` which when used ensures none of the options inside of it can be selected. 

The optgroup itself can't be selected and can't be styled (at least not in any cross browser centric way). 

###Practical example
The `<optgroup>` element works great in any situation when you're using the `<select>` tag. For example consider a dropdown list of computer price ranges (on an eCommerce site).

```
<label for="comp-price-filter">Select the price range of your next computer</label>
<select class="price-filter" name="comp-price-filter" id="comp-price-filter">
	<optgroup label="Low End">
		<option value="100-300">$100 - $300</option>
		<option value="301-500">$301 - $500</option>
		<option value="501-700">$501 - $700</option>
	</optgroup>
	<optgroup label="Middle Range">
		<option value="701-1200">$701 - $1200</option>
		<option value="1201-1601">$1201 - $1600</option>
	</optgroup>
	<optgroup label="High End">
		<option value="1601-2500">$1600 - $2500</option>
		<option value="2500-3200">$2501 - $3200</option>
	</optgroup>
</select>
```

Here's an example where you can use the `disabled` attribute to disallow a range of options (though there's nothing really stopping people from just removing this attribute from the `<optgroup>` so don't rely on it for validation). 

```
<label for="vacation-dest">Vacation Destinations</label>
<select name="vaction-dest" id="vacation-dest">
	<optgroup label="East Coast - Australia">
		<option value="NSW">New South Wales</option>
		<option value="QLD">Queensland</option>
		<option value="TAS">Tasmania</option>
		<option value="ACT">Australian Capital Territory</option>
		<option value="VIC">Victoria</option>
	</optgroup>
	<optgroup disabled label="West Coast - Australia">
		<option value="WA">Western Australia</option>
		<option value="NT">Northern Territory</option>
		<option value="SA">South Australia</option>
	</optgroup>
</select>

```

In the above example you shouldn't be able to select anything within the 'West Coast - Australia' optgroup.


##6 - Predefined options with `<datalist>`

One of the great things about the `<select>` element, along with the `radio` / `checkbox` input types is that it restricts your users to a set of predefined choices. 

You can now use the `<datalist>` element to define the list of valid choices for your various `<input>` tags.  This component is slightly different on various browsers, but the common way it works is by showing a small drop-down carrot to the right of the field indication that this field has options. When selected usually the options will fold down and show themselves. The user can start typing and the options will highlight if they partially match (for example writing 'Chr' inside a field that has 'Chrome' as an option will narrow down the option list to show it). 

This is still a growing element but overall it works well.

###Practical Examples

If you wanted to provide a list of URL's that the user could select from, you could create a `<datalist>` and connect it to your `<input>` as follows.

```
<label for="favourite-sites">Select your favorite website!</label>
<input type="url" name="favourite-sites" id="favourite-sites" list="site-list"/>
<datalist id="site-list">
  <option value="http://www.google.com.au">
  <option value="http://www.reddit.com.au">
  <option value="http://www.sitepint.com">
</datalist>
```

This will let you constrict your inputs to just a few values.


###Notes and consideration
The datalist itself will perform validation based on the `type` attribute for the `<input>` element. For example if you have chosen to use `type="email"` and then supply a `<datalist>` element to it, the options inside this list must confirm to email types. This means that it has some level of smart processing and should make it easier for you to control values.

The `<datalist>` tag is [fairly well supported](http://caniuse.com/#search=datalist), however Apple have decided not to support this element at all (on both desktop and on iOS). Microsoft supports this from IE10 onwards (with no support on mobile IE). When support isn't available the `<input>` element should fall back to its normal input mode.

This component can be a bit buggy, for example if you mark the input as `required` and don't enter a value, the form will prevent processing till you select a value (which is what you expect). However, if you manually type in a value (even if it isn't correct) and press submit this won't trigger an error, nothing will happen (you expect it would flag an error that the value is incorrect). 


##Wrapping it all up!

Hopefull you've picked up a useful element or two from this article and going forward you can use them in your upcoming sites.

If you know of any other lesser know / useful HTML tags we'd be keen to hear how you've used them and how they work for you.
