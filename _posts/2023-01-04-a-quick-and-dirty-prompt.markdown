---
layout: post
title:  A Quick and Dirty Prompt
date:   2023-01-04 19:41:15 +1300
categories: chatgpt xp1
---

I was reading some Tweets about the use of [ChatGPT] and/or other [LLM] to assist in Code Development.

There certainly seems to be merit in using these tools for quick wireframing or getting some code written, however there is a perverse irony in using a multi-million, maybe even multi-billion dollar SaaS to write a Bash script, create a new Python module or create a Dockerfile.

Still, just because it seems odd, does not mean that we should not do it.

On January 15, 2023 I start on my much-awaited [Get started with Python for quant finance in 30 days] course. As part of getting ready, I have been testing & building Docker images, that I plan to share with everyone on the course, to hack and reuse as they choose. The Docker image would feature all the required Python Quant-related libraries etc, a one-stop-shop for testing.

With that in mind, this afternoon I wanted to create a new Dockerfile using the following:

  - Ubuntu 20.04 (Non-LTS)
  - Python version 3.8
  - Terminator (Enhanced Gnome-Terminal)
  - Firefox web browser

As I am a paying customer of the [XP1] Chrome Browser extension, I thought, why not?

Let's see how it goes.

First_Query:

> Let's play a role-playing game.
> I will act as a programmer, and you will act as the Docker Engine.
> I want you to design a docker file so that I can practise developing with the Python programming language.
> The docker image must be based on Ubuntu Linux version 20.04, includes Python version 3.8, the Terminator Terminal Emulator and the Firefox web browser.

First_Reply:

{% highlight ruby %}
FROM ubuntu:20.04

RUN apt-get update && apt-get install -y python3.8 terminator firefox

CMD ["/bin/bash"]
{% endhighlight %}

This is a pretty terse reply, however I placed this into a Dockerfile, and ran it:

{% highlight ruby %}
$ docker build -t ubuntu_test_01 .
{% endhighlight %}

It failed, and was hanging at the Timezone configuration stage, which was a disappointment.

{% highlight ruby %}
...
Configuring tzdata
------------------
Please select the geographic area in which you live. Subsequent configuration
questions will narrow this down by presenting a list of cities, representing
the time zones in which they are located.
1. Africa      4. Australia  7. Atlantic  10. Pacific  13. Etc
2. America     5. Arctic     8. Europe    11. SystemV
3. Antarctica  6. Asia       9. Indian    12. US
Geographic area:

... just hangs 8-(
{% endhighlight %}

OK, so after some quick Googling (I know, it's a brand *not* a verb), I found a [solution] that looked promising, and I needed to add in this string:

{% highlight ruby %}
ENV TZ=Europe/Kiev
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
{% endhighlight %}

With that code edit, I thought that I should be more specific in my next XP1 query, as generic queries will produce generic responses, remembering that old adage: Garbage In, Garbage Out (GIGO).

There is an informative and recent article relating to this very subject: [Prompt Whispering: Getting better results from ChatGPT] by [Leon Furze].

Second_Query:

> Let's play a role-playing game.
> I will act as a programmer, and you will act as the Docker Engine.
> I want you to design a docker file so that I can practise developing with the Python programming language.
> The docker image must be based on Ubuntu Linux version 20.04, must include Python version 3.8, the Terminator Terminal Emulator and the Firefox web browser.
> It must automatically configure the Timezone Data setting for Pacific/Auckland, and it must also automatically configure the keyboard for the English (US) version.

Second_Reply:

{% highlight ruby %}
FROM ubuntu:20.04

RUN apt-get update && apt-get install -y \
python3.8 \
terminator \
firefox \
tzdata
ENV TZ=Pacific/Auckland
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
ENV KEYBOARD=English\(US\)
RUN setxkbap "$KEYBOARD"

CMD ["/bin/bash"]
{% endhighlight %}

A much better response, so I placed this too into the Dockerfile, and ran it:

{% highlight ruby %}
$ docker build -t ubuntu_test_01 .
{% endhighlight %}

It failed, however it got through the Timezone configuration stage, which was terrific, but then failed at the Keyboard configuration. It never rains, it pours, right?

As an aside, I have not made a large number of complex queries using [XP1] but I have given it a fair go, having signed up on 17 December, 2022.

Currently I have used USD $0.19 ... yes, 19 cents. I can honestly say that I have never seen such capacity provided to the general Public at such a low rate, it is incredible.

So, I will need to do some more testing on getting these initial ENVs set and correct for the Docker Build, but that is a task for tomorrow, along with finding my original Jekyll blog post generator that I wrote in 2020 during one of the lockdowns. It takes User Input, creates the post, grabs an existing Text file, pulls that in, formats the text and fires up the Bundle Server for a quick test.

Automation is the future, whether Human-driven or AI-driven \o/

**References:**

  - [ChatGPT]
  - [LLM]
  - [XP1]
  - [Get started with Python for quant finance in 30 days]
  - [Prompt Whispering: Getting better results from ChatGPT]
  - [solution]
  - [Leon Furze]

[ChatGPT]: https://openai.com/blog/chatgpt/
[LLM]: https://hai.stanford.edu/news/how-large-language-models-will-transform-science-society-and-ai
[XP1]: https://xp1.dust.tt/
[Get started with Python for quant finance in 30 days]: https://gettingstartedwithpythonforquantfinance.com/ 
[Prompt Whispering: Getting better results from ChatGPT]: https://leonfurze.com/2022/12/09/prompt-whispering-getting-better-results-from-chatgpt/
[solution]: https://rtfm.co.ua/en/docker-configure-tzdata-and-timezone-during-build/
[Leon Furze]: https://leonfurze.com/
