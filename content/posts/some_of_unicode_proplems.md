---
title: "Some of unicode problems"
date: 2023-10-09
description: ''
featured_image: ""
tags: ["#unicode", "#text"]
draft: false
---

# Some of text problems or some of falsehoods 

A long time ago, I came across a wonderful list of things [Falsehoods Programmers Believe](https://github.com/kdeldycke/awesome-falsehood) and [Falsehoods Programmers Believe About Falsehoods Lists](https://kevin.deldycke.com/2016/12/falsehoods-programmers-believe-about-falsehoods-lists/)

Now its time to update some knoleage about it

> Text is everything.

![](images/4J7Il0m.png)


During my life, text has been a major source of information. 
In my work, I have regularly encountered the nuances of storing textual information, from illegibly written text and messy layout and fonts in a Word document to the processing of streaming data

In 2008, the following story happened [A Cellphone's Missing Dot Kills Two People, Puts Three More in Jail](https://gizmodo.com/a-cellphones-missing-dot-kills-two-people-puts-three-m-382026)

Or how [the Wubi Effect](https://radiolab.org/podcast/wubi-effect) is affecting Chinese language

So there is no doubt about the importance of textual information

For example, here are a couple of articles with lists of misconceptions that are true not only for programmers
* [Falsehoods About Language](http://garbled.benhamill.com/2017/04/18/falsehoods-programmers-believe-about-language) 
* [Falsehoods About Plain Text (non-tech/tech/regexp)](https://jeremyhussell.blogspot.com/2017/11/falsehoods-programmers-believe-about.html#main)

What about standarts?

## Unicode

[Unicode](https://home.unicode.org/) is a big table that assigns numbers (codepoints) to a wide variety of characters you might want to use to write text. We often say “Unicode” when we mean “not ASCII”, but that’s silly since of course all of ASCII is also included in Unicode.

There are already plenty of introductions to Unicode floating around (wikipedia, [nedbat](https://nedbatchelder.com/text/unipain.html), [joel](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)).


UTF-8 is an encoding, a way of turning a sequence of codepoints into bytes. All Unicode codepoints can be encoded in UTF-8. ASCII is also an encoding, but only supports 128 characters, mostly English letters and punctuation.

A character is a fairly fuzzy concept. Letters and numbers and punctuation are characters. But so are Braille and frogs and halves of flags. Basically a thing in the Unicode table somewhere.

Unicode refers to these numbers as code points.

Since everybody in the world agrees on which numbers correspond to which characters, and we all agree to use Unicode, we can read each other’s texts.

Currently, the largest defined code point is 0x10FFFF. That gives us a space of about 1.1 million code points.

About 170,000, or 15%, are currently defined. An additional 11% are reserved for private use. The rest, about 800,000 code points, are not allocated at the moment. They could become characters in the future.

Here’s roughly how it looks:

![](/images/overview@2x.png)

#### Private Use?
These are code points reserved for app developers and will never be defined by Unicode itself.

For example, there’s no place for the Apple logo in Unicode, so Apple puts it at U+F8FF which is within the Private Use block. In any other font, it’ll render as missing glyph 􀣺, but in fonts that ship with macOS, you’ll see .




### Principles of the Unicode Standard

The Unicode Standard set forth the following fundamental principles:
* Universal repertoire - Every writing system ever used shall be respected and represented in the standard
* Logical order - In bidirectional text are the characters stored in logical order, not in a way that the representaion
* Efficiency - The documentation must be efficient and complete.
* Unification - Where different cultures or languages use the same character, it shall be only included once. This point is
* Characters, not glyphs - Only characters, not glyphs shall be encoded. In a nutshell, glyphs are the actual graphical
* Dynamic composition - New characters can be composed of other, already standardized characters. For example, the character “Ä” can be composed of an “A” and a dieresis sign (“ ¨ ”).
* Semantics - Included characters must be well defined and distinguished from others.
* Stability - Once defined characters shall never be removed or their codepoints reassigned. In the case of an error, a codepoint shall be deprecated.
* Plain Text - Characters in the standard are text and never mark-up or metacharacters.
* Convertibility - Every other used encoding shall be representable in terms of a Unicode encoding.

[Dark corners of Unicode](https://eev.ee/blog/2015/09/12/dark-corners-of-unicode/)




Even email


Are you sure that your email validation is right?
[I Knew How To Validate An Email Address Until I Read The RFC](https://haacked.com/archive/2007/08/21/i-knew-how-to-validate-an-email-address-until-i.aspx/)
[Your E-Mail Validation Logic is Wrong](https://www.netmeister.org/blog/email.html)
does next emails valid
```
Joe.\\Blow@example.com
"jd..oe"@domain
" "@netmeister.org
"<>"@netmeister.org
"put a literal escaped newline here\ <--"@domain
mail -s "a very long To" $(perl -e 'print "a" x 526;')@netmeister.org
"josé.arrañoça"@domain
"сайт"@domain
"💩"@domain
"🍺🕺🎉"@domain
poop@xn--ls8h.la
poop@💩.la
"🌮"@i❤️tacos.ws
jschauma@شبكةمايستر..شبكة
jschauma@[166.84.7.99]
jschauma@[IPv6:2001:470:30:84:e276:63ff:fe72:3900]
jschauma@[IPv6:::1]
"[IPv6:::1]"@[IPv6:::1]
@1st.relay,@2nd.relay:user@final.domain
```
and `Alla.jd.Doe@domain.com` same as `alla.jd.doe@domain.com` and .toLower(Alla.jd.Doe@domain.com)?



twitter
https://x.com/nikitonsky/status/1171115067112398849?s=20

> Text is everything.
>
> Fonts is everywhere

https://github.com/RoelN/Font-Falsehoods


> Case is also a broblem

For example there are more than two cases. Unicode actually has three cases. There’s lowercase, and there’s uppercase. And there’s titlecase. 

1. A character is uppercase if its general category is Lu (“Letter, uppercase”), and lowercase if its general category is Ll (“Letter, lowercase”). The Unicode Standard admits this is a very limiting definition, because each character gets only one general category, so many characters which “should be” uppercase or lowercase may fail this definition on account of their general category indicating something else.
2. A character is uppercase if it has the derived property Uppercase, and lowercase if it has the derived property Lowercase. These are based on combining the characters in definition (1) with characters possessing other properties which indicate case.
3. A character is uppercase if applying the Unicode case mapping to uppercase (“uppercasing it”) leaves it unchanged, and lowercase if applying the Unicode case mapping to lowercase (“lowercasing it”) leaves it unchanged. This is comprehensive, but may also behave unintuitively (see later sections).

Meanwhile some characters have no case
> A character C is defined to be cased if and only if C has the Lowercase or Uppercase property or has a General_Category value of Titlecase_Letter.

Some characters may appear to have multiple cases

Read more in [Falsehoods about case](https://www.b-list.org/weblog/2018/nov/26/case/)


**Case is context-locale-sensitive**

String length is typically determined by counting codepoints. This means that surrogate pairs would count as two characters. Combining multiple diacritics may be stacked over the same character. a + ̈  == ̈a   , increasing length, while only producing a single character.

Similarily, reversing strings often is a non-trivial task. Again, surrogate pairs and diacritics must be reversed together. ES Reverser provides a pretty good solution.

Upper and lower case mappings are not always one-to-one. They can also be:

One-to-many: (ß → SS )
Contextual: (…Σ ↔ …ς AND …ΣΤ… ↔ …στ… )
Locale-sensitive: ( I ↔ ı AND İ ↔ i )

More [Awesome-Unicode](https://github.com/jagracey/Awesome-Unicode)


[W.T.F. Japan: Top 5 most insane kanji place names in Japan【Weird Top Five](https://web.archive.org/web/20210310050932/https://soranews24.com/2016/12/01/w-t-f-japan-top-5-most-insane-kanji-place-names-in-japan%E3%80%90weird-top-five%E3%80%91/)

Great text about unicode in 2023
https://tonsky.me/blog/unicode/
And https://hsivonen.fi/string-length/

[It’s Not Wrong that "🤦🏼‍♂️".length == 7](https://hsivonen.fi/string-length/)

[Breaking Our Latin-1 Assumptions](https://manishearth.github.io/blog/2017/01/15/breaking-our-latin-1-assumptions/)

# More Reading
* [The Absolute Minimum Every Software Developer Absolutely, Positively Must Know About Unicode and Character Sets](http://www.joelonsoftware.com/articles/Unicode.html) - By Joel Spolsky
* [What Every Programmer Absolutely, Positively Needs To Know About Encodings And Character Sets To Work With Text](http://kunststube.net/encoding/)
* [The Unicode Consortium's Recommended Reading List](http://www.unicode.org/resources/readinglist.html)
* [Space Yourself](https://www.smashingmagazine.com/2015/10/space-yourself/) - Smashing Magazine's Spacing Guide
* [JavaScript has a Unicode Problem](https://mathiasbynens.be/notes/javascript-unicode)
* [Creative usernames and Spotify account hijacking](https://labs.spotify.com/2013/06/18/creative-usernames/)


[Falsehoods programmers believe about text](https://wiesmann.codiferes.net/wordpress/archives/30296)

[Internationalis(z)ing Code - Computerphile](https://www.youtube.com/watch?v=0j74jcxSunY)