# markdown.lua
This is an implementation of the popular text markup language Markdown in pure Lua. Markdown can convert documents written in a simple and easy to read text format to well-formatted HTML.

I (develephant) did not make this module, I am simply archiving it, as it is a pretty good Pure Lua Markdown parser, though a bit outdated.

# markdown.lua -- version 0.32

<http://www.frykholm.se/files/markdown.lua>  
**Author:** Niklas Frykholm, <niklas@frykholm.se>  
**Date:** 31 May 2008

This is an implementation of the popular text markup language Markdown in pure Lua.
Markdown can convert documents written in a simple and easy to read text format
to well-formatted HTML. For a more thorough description of Markdown and the Markdown
syntax, see <http://daringfireball.net/projects/markdown>.


The original Markdown source is written in Perl and makes heavy use of advanced
regular expression techniques (such as negative look-ahead, etc) which are not available
in Lua's simple regex engine. Therefore this Lua port has been rewritten from the ground
up. It is probably not completely bug free. If you notice any bugs, please report them to
me. A unit test that exposes the error is helpful.


## Usage
    require "markdown"
    markdown(source)


``markdown.lua`` exposes a single global function named ``markdown(s)`` which applies the
Markdown transformation to the specified string.


``markdown.lua`` can also be used directly from the command line:

    lua markdown.lua test.md

Creates a file ``test.html`` with the converted content of ``test.md``. Run:

    lua markdown.lua -h

For a description of the command-line options.


``markdown.lua`` uses the same license as Lua, the MIT license.


## License
Copyright &copy; 2008 Niklas Frykholm.
Permission is hereby granted, free of charge, to any person obtaining a copy of this
software and associated documentation files (the "Software"), to deal in the Software
without restriction, including without limitation the rights to use, copy, modify, merge,
publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons
to whom the Software is furnished to do so, subject to the following conditions: 
The above copyright notice and this permission notice shall be included in all copies
or substantial portions of the Software. 
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

## Version history

-	**0.32** -- 31 May 2008
	- Fix for links containing brackets
-	**0.31** -- 1 Mar 2008
	-	Fix for link definitions followed by spaces
-	**0.30** -- 25 Feb 2008
	-	Consistent behavior with Markdown when the same link reference is reused
-	**0.29** -- 24 Feb 2008
	-	Fix for <pre> blocks with spaces in them
-	**0.28** -- 18 Feb 2008
	-	Fix for link encoding
-	**0.27** -- 14 Feb 2008
	-	Fix for link database links with ()
-	**0.26** -- 06 Feb 2008
	-	Fix for nested italic and bold markers
-	**0.25** -- 24 Jan 2008
	-	Fix for encoding of naked <
-	**0.24** -- 21 Jan 2008
	-	Fix for link behavior.
-	**0.23** -- 10 Jan 2008
	-	Fix for a regression bug in longer expressions in italic or bold.
-	**0.22** -- 27 Dec 2007
	-	Fix for crash when processing blocks with a percent sign in them.
-	**0.21** -- 27 Dec 2007
	- 	Fix for combined strong and emphasis tags
-	**0.20** -- 13 Oct 2007
	-	Fix for < as well in image titles, now matches Dingus behavior
-	**0.19** -- 28 Sep 2007
	-	Fix for quotation marks " and ampersands & in link and image titles.
-	**0.18** -- 28 Jul 2007
	-	Does not crash on unmatched tags (behaves like standard markdown)
-	**0.17** -- 12 Apr 2007
	-	Fix for links with %20 in them.
-	**0.16** -- 12 Apr 2007
	-	Do not require arg global to exist.
-	**0.15** -- 28 Aug 2006
	-	Better handling of links with underscores in them.
-	**0.14** -- 22 Aug 2006
	-	Bug for *`foo()`*
-	**0.13** -- 12 Aug 2006
	-	Added -l option for including stylesheet inline in document.
	-	Fixed bug in -s flag.
	-	Fixed emphasis bug.
-	**0.12** -- 15 May 2006
	-	Fixed several bugs to comply with MarkdownTest 1.0 <http://six.pairlist.net/pipermail/markdown-discuss/2004-December/000909.html>
-	**0.11** -- 12 May 2006
	-	Fixed bug for escaping `*` and `_` inside code spans.
	-	Added license terms.
	-	Changed join() to table.concat().
-	**0.10** -- 3 May 2006
	-	Initial public release.
// Niklas
