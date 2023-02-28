---
layout: post
title:  "Extract 9 Parameters List"
date:   2023-02-28 12:42:21 +1300
categories: blog update
---
I read an interesting [Medium] article the other day, titled [Become the best GPT Master Chef], and thought I would grab the required parameters from the article to use in my future Text Prompts.

Deciding to use XP1, not ChatGPT, this is how it went.

**Query_01:**

{% highlight ruby %}
Review this page; extract the 9 GPT model parameters; present as a simple list.
{% endhighlight %}

{% highlight ruby %}
{% endhighlight %}

**Result_01:**

> GPT Model Parameters:
1. Temperature
2. Maximum Length
3. Top P
4. Stop Sequence
5. Frequency Penalty
6. Presence Penalty
7. Best of
8. Inject Start Text
9. Inject Restart Text

**Query_02:**

{% highlight ruby %}
Modify this list to include Item 9 from the article Summary list.
{% endhighlight %}

**Result_02:**

> GPT Model Parameters:
1. Temperature
2. Maximum Length
3. Top P
4. Stop Sequence
5. Frequency Penalty
6. Presence Penalty
7. Best of
8. Inject Start Text
9. Inject Restart Text
10. Show Probabilities

Verdict?

Not a bad result, although I am a little surprised to see that initially, instead of placing the two closely-related items 'Inject Start Text' and 'Inject Restart Text' onto 1 line as was the article; it split them out into 2 separate points; then did a recount; deciding to delete the last required entry.

Well, I did say 9, right?

Still, this was likely quicker than typing these 9 parameters out into a list, but possibly only just.

This extracted list now gives me the ability to force ChatGPT or XP1 to produce different results, which is a great idea for series of articles, that I will plan for this week.

**References:**

  - [Medium]
  - [Become the best GPT Master Chef]

[Medium]: https://medium.com/
[Become the best GPT Master Chef]: https://medium.com/thelatestai/become-the-best-gpt-master-chef-707f0c9d7c39

