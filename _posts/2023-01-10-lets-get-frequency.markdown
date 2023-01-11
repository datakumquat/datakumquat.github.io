---
layout: post
title:  "Lets Get Frequency"
date:   2023-01-10 22:10:35 +1300
categories: blog frequency
---
It is just on a week now until the [Getting Started with Python for Quant Finance] course with [PyQuant News] starts. Which got me thinking about Python Finance and Trading libraries in general, so let's see what [ChatGPT] via [XP1] can provide in the way of practical information.

**Query_01:**

> What are the 15 most popular and actively supported Python packages relating to the Financial and Quant sectors? Present the result in a list using bullet points. Ensure that the order of the results are from the most popular to the least popular. Ensure that any Python package in the results has it's complete hyperlink included with the results.

**Result_01:**

{% highlight ruby %}
[SciPy](https://www.scipy.org/): SciPy is a Python-based ecosystem of open-source software for mathematics, science, and engineering.
[NumPy](http://www.numpy.org/): NumPy is the fundamental package for scientific computing with Python.
[Pandas](https://pandas.pydata.org/): Pandas is an open source library providing high-performance, easy-to-use data structures and data analysis tools.
[PyFinance](https://pyfinance.readthedocs.io/en/latest/): PyFinance is a Python library for financial analysis of stock markets.
[TensorFlow](https://www.tensorflow.org/): TensorFlow is an open source library for numerical computation, specializing in deep learning and machine learning.
[PyBrain](http://pybrain.org/): PyBrain is a machine learning library for Python.
[PyMC3](https://pymc-devs.github.io/pymc3/): PyMC3 is a Python library for probabilistic machine learning, focusing on Bayesian inference.
[PyQuant](http://pyquant.org/): PyQuant is a Python library for quantitative finance.
[PyTorch](https://pytorch.org/): PyTorch is an open source deep learning framework for Python.
[PyAlgoTrade](http://gbeced.github.io/pyalgotrade/): PyAlgoTrade is a Python library for backtesting stock trading strategies.
[QuantLib](https://www.quantlib.org/): QuantLib is a free, open-source library for quantitative finance.
[PyThalesians](http://pyquant.org/): PyThalesians is a Python library for quantitative finance.
[Quantopian](https://www.quantopian.com/): Quantopian is an open source web-based platform for quantitative finance and algorithmic trading.
[PySwarms](https://pyswarms.readthedocs.io/en/latest/): PySwarms is a particle swarm optimization library for Python.
[PyQuantLib](https://github.com/yhilpisch/py
{% endhighlight %}

If you are an Open Source user like myself, you might want to only use Open Source packages.

**Query_02:**

> Referring to this list of 15 Python packages: \
[SciPy](https://www.scipy.org/);
[NumPy](http://www.numpy.org/);
[Pandas](https://pandas.pydata.org/);
[PyFinance](https://pyfinance.readthedocs.io/en/latest/);
[TensorFlow](https://www.tensorflow.org/);
[PyBrain](http://pybrain.org/);
[PyMC3](https://pymc-devs.github.io/pymc3/);
[PyQuant](http://pyquant.org/);
[PyTorch](https://pytorch.org/);
[PyAlgoTrade](http://gbeced.github.io/pyalgotrade/);
[QuantLib](https://www.quantlib.org/);
[PyThalesians](http://pyquant.org/);
[Quantopian](https://www.quantopian.com/);
[PySwarms](https://pyswarms.readthedocs.io/en/latest/) and
[PyQuantLib](https://github.com/yhilpisch/py/). How many of these are 100% open source and are available at zero cost to the user?

**Result_02:**

{% highlight ruby %}
- SciPy
- NumPy
- Pandas
- PyFinance
- TensorFlow
- PyBrain
- PyMC3
- PyQuant
- PyTorch
- PyAlgoTrade
- QuantLib
- PyThalesians
- Quantopian
- PySwarms
- PyQuantLib

All of the above packages are available at no cost and are 100% open source.
{% endhighlight %}

That is a good result but you may notice that it did not directly answer the question, "how many of these are 100% open source and are available at zero cost to the user?" I would have expected it to have stated: '15, and here is the list.' Not just present the list with no context.

Now, you can compare how many of the above libraries, you will actually need to install for the [Getting Started with Python for Quant Finance] course.

**Query_03:**

> Referring to this list: SciPy; NumPy; Pandas; PyFinance; TensorFlow; PyBrain; PyMC3; PyQuant; PyTorch; PyAlgoTrade; QuantLib; PyThalesians; Quantopian; PySwarms and PyQuantLib, how many of these are required for the 'Getting Started with Python for Quant Finance' course which is located at https://gettingstartedwithpythonforquantfinance.com/? Present this result using an ordered list format.

**Result_03:**

{% highlight ruby %}
- SciPy
- NumPy
- Pandas
- PyFinance
- TensorFlow
- PyBrain
- PyMC3
- PyQuant
- PyTorch
- PyAlgoTrade
- QuantLib
- PyThalesians
- Quantopian
- PySwarms
- PyQuantLib
{% endhighlight %}

Again you will note, this is  direct list result but still not answering the question. If I asked you this question, you would probably answer something like "4, and these are the actual libraries."

I need to confirm the above answer.

**Query_04:**

Are you sure this is correct?

**Result_04:**

{% highlight ruby %}
Yes, that is correct.
{% endhighlight %}

Let's check then ... reviewing this list against the [Getting Started with Python for Quant Finance] site, I did not find a single match.

How would you check? You would grab the complete list 'Query_04' using Copy&Paste, then use Ctrl-F on the actual page. Very simple but it worked.

I am feeling a little freaky, I meant frequency, so let's run some freqnency analysis against the site.

**Query_05:**

> Referring to the site located at https://gettingstartedwithpythonforquantfinance.com/, how many times is the following list of words enclosed within the double quotes used "python data quant framework learn package testing community" used? Ignore the Capitalization of any target word. Ensure that the results are presented in the order of most frequent to least frequent, displaying the target word and the number of times that it was used. Ensure that the result is formatted using bullet points.

**Result_05:**

{% highlight ruby %}
- python: 12
- data: 5
- quant: 3
- framework: 2
- learn: 2
- package: 2
- testing: 1
- community: 1
{% endhighlight %}

You will note that this reply is exactly what you asked for; target_word: frequency. Ah how cute, the world's most expensive K:V generator.

Let's ask the inverse then, what words on the entire site, are the most frequent?

**Query_06:**

> Referring to the site located at https://gettingstartedwithpythonforquantfinance.com/, discover what are the 20 most frequent words used on this site. Ignore the Capitalization of any target word. Ensure that the results are presented in the order of most frequent to least frequent, displaying the target word and the number of times that it was used. Ensure that the result is formatted using bullet points.

**Result_06:**

{% highlight ruby %}
* the - 7013 occurrences
* and - 5190 occurrences
* of - 3568 occurrences
* to - 2488 occurrences
* in - 1871 occurrences
* a - 1773 occurrences
* for - 1172 occurrences
* is - 1099 occurrences
* with - 1046 occurrences
* Python - 974 occurrences
* that - 938 occurrences
* you - 894 occurrences
* are - 833 occurrences
* it - 697 occurrences
* from - 665 occurrences
* your - 653 occurrences
* data - 641 occurrences
* as - 631 occurrences
* be - 621 occurrences
* this - 614 occurrences
{% endhighlight %}

Well, that is what you should expect; prepositions galore.

Interesting that this result returned 974 instances of Python ignoring the capitalization, and yet in 'Query_06', it only returned 12 instances of python, ignoring the capitalization.

One final query for this session.

**Query_07:**

> Referring to the site located at https://gettingstartedwithpythonforquantfinance.com/, there are two lists of words enclosed within double quotes; List_A "quant framework learn package testing community" and List_B "the and of to in a for is with Python that you are it from your data as be this" What percentage is the List_A and List_B compared to the total words on that site? \
Present the results in the best way possible.

**Result_07:**

{% highlight ruby %}
## Word count comparison

| List  | Count | Percentage |
|-------|-------|------------|
| List_A |  5    |     0.15%  |
| List_B |  18   |     0.54%  |
{% endhighlight %}

Verdict?

That was an interesting set of queries, and you can see that without being too specific, ChatGPT can provide good results.

You will notice a few times that it has not answered direct questions, however it might be that the question itself was the issue, formatted in a way that causes some syntax issues, so the query is skipped. This is a good candidate for further exploration.

**References:**

  - [ChatGPT]
  - [XP1]
  - [Getting Started with Python for Quant Finance]
  - [PyQuant News]

[ChatGPT]: https://openai.com/blog/chatgpt/
[XP1]: https://xp1.dust.tt/
[Getting Started with Python for Quant Finance]: https://gettingstartedwithpythonforquantfinance.com/
[PyQuabt News]: https://twitter.com/pyquantnews
