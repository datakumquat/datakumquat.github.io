---
layout: post
title:  "Make Me A Great Tweet"
date:   2023-01-22 18:23:33 +1300
categories: blog update
---
I have not used [ChatGPT] for 10 days now, as I have either used [XP1] as the interface service or I have been too busy with Python and Content Creation learning.

Having just published a lengthy but process-driven blog post titled [Rebuild A Better Ubuntu], I thought that I would take the opportunity to request ChatGPT to create a Tweet to publicise that post.

**ChatGPT Text Prompt:**

> Create a Tweet mentioning using the phrase "Check out my latest blog post" and the hyperlink "https://datakumquat.github.io/blog/update/2023/01/22/rebuild-a-better-ubuntu.html". Do not suggest Hashtags. Use the terms; ubuntu better and install. Ensure that there is a blank line before and after the hyperlink. In the final result remove all instances of the double quotes. Also, at the end of the Tweet, insert the phrase "[Made by ChatGPT & Me]"

**ChatGPT Result:**

> Check out my latest blog post on how to rebuild a better Ubuntu! Learn about the latest install techniques and best practices for optimizing your system.

> https://datakumquat.github.io/blog/update/2023/01/22/rebuild-a-better-ubuntu.html

> [Made by ChatGPT & Me]

Verdict?

I like it as it is almost exactly what I asked for, however it did seem to take a slight artistic license with the term `install`, other than that the formatting and terseness gets a 9/10 from me.

Although from a Line and Character perspective, it actually would take you far longer to type out the ChatGPT Prompt, than it would to have typed out the ChatGPT Result.

See below for a quick breakdown.

**Analysis of ChatGPT Prompt:**

{% highlight ruby %}
# Create a text file titled prompt.txt
# Place contents of ChatGPT Prompt into that file
# Check the Line Count
$ cat prompt.txt | wc -l
3
# Check the Character Count
$ cat prompt.txt | wc -m
449
{% endhighlight %}

**Analysis of ChatGPT Result:**

{% highlight ruby %}
# Create a text file titled result.txt
# Place contents of ChatGPT Result into that file
# Check the Line Count
$ cat result.txt | wc -l
5
# Check the Character Count
$ cat result.txt | wc -m
261
{% endhighlight %}

So the ChatGPT Result was 2 more lines but 188 less characters than the ChatGPT Prompt, and it was generated in under 2 seconds.

Which brings me to the point, that inputting Text character-by-character via the ChatGPT UI directly, is quite inefficient. However if you created a Content Generatoring Tool that worked from the Desktop and produced a Text file as a result, which is then Copy&Pasted into the ChatGPT UI, this may help.

This needs some thinking, and possibly the creation of a tool.

The only difference between Us and the Other Great Apes is the sophistication and ubiquity of our Tools.

**References:**

  - [ChatGPT]
  - [XP1]
  - [Rebuild A Better Ubuntu]

[ChatGPT]: https://chat.openai.com/chat
[XP1]: https://xp1.dust.tt/
[Rebuild A Better Ubuntu]: https://datakumquat.github.io/blog/update/2023/01/22/rebuild-a-better-ubuntu.html
