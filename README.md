Typogrify.ee_addon
==================

The typogrify plugin for Expression Engine is a reinterpretation of the Django templates of the same name.

The plugin includes the following functions:

`{exp:typogrify:amp}` - Wrap ampersands in a `span` with `class="amp"`.  This enables you to follow Bringhursts recommendation to "In heads and titles, use the best available ampersand".

`{exp:typogrify:caps}` - Wrap sequences of capital letters in a `span` with `class="caps"`.  This is useful if you want to set sequences of capitals as small capitals.  There must be at least two capital letters in the sequence, the letters may be separated by periods, and the sequence must be surrounded by characters other than letters.  This will _not_ wrap the initials in a name like W. B. Yeats, because it is not usually considered good practice in typography to set those capitals as small capitals.

`{exp:typogrify:initial_quote}` - Wrap a quote character that is the first character in a paragraph in the two `class`es "initial" and "quote".	 A paragraph in this context means either an actual paragraph element, a heading element or a list element.	 The quote characters that we recognize here are the left double angle, the left angle, the left double and the left single entities—the characters classified in Unicode as initial quote characters.

`{exp:typogrify:final_quote}` - Wrap a quote character that is the last character in a paragraph in the two `class`es "final" and "quote".	A paragraph in this context means either an actual paragraph element, a heading element or a list element.	The quote characters that we recognize here are the right double angle, the right angle, the right double and the right single entities—the characters classified in Unicode as final quote characters.

`{exp:typogrify:smartypants attr="2"}` - This is just a wrapping of the PHP port by Michel Fortin of John Grubers SmartyPants perl script.  I have made one change from the original script; the default attribute is set to 2, which means that	"---" is used for em-dashes and "--" for en-dashes; this default can be overridden with the attr parameter.

`{exp:typogrify:widont}` - Insert a non-breaking space entity between the two last words in every paragraph.	A paragraph in this context means either an actual paragraph element, a heading element or a list element.	This will avoid what typographers refer to as "widows"—a single word on its own line at the end of a paragraph.

`{exp:typogrify}` - A shortcut to apply all the functions in the plugin. To selectively remove a given function, set the function name equal to "n":

	{exp:typogrify widont="n"}