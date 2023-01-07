---
layout: post
title:  "Get Me a Twitter Developer Account"
date:   2023-01-07 18:39:50 +1300
categories: chatgpt blog
---
Well, what a day!

  - Shopping
  - Cleaning
  - Writing
  - Coding
  - Testing

I was going to write a post on using ChatGPT to create a content generator and formatting tool using the Bash scripting language. I got most of the way through the post, but my Open AI session seemed to jam on me, so I killed it, wiped the data. Fortunately I am now in the habit of recording my Queries & Results.

So, what to do?

Do something Bashy I think, to do with Automation ... 'cos I love Tooling.

Making things that do things, with ChatGPT <- **That's a T-shirt slogan right there.**

Referring to the [ChatGPT Magic] article by [Nate McCallister], let's not make a list about Cats, let's do something more practical: practical is useful, not just for me but for others also.

**Query_01:**

> What are 10 good uses for Bash scripting to automating writing documents?

**Result_01:**
{% highlight ruby %}
1. Generating reports: You can use bash scripts to gather data from various sources and automatically generate reports in the desired format (e.g. PDF, HTML).
2. Converting file formats: You can use bash scripts to batch convert files from one format to another (e.g. markdown to HTML).
3. Automating backups: You can use bash scripts to schedule regular backups of important files and directories.
4. Generating graphics: You can use bash scripts to automatically generate graphs and charts from data sets.
5. Building websites: You can use bash scripts to automate the process of building and deploying static websites.
6. Creating documents from templates: You can use bash scripts to populate templates with data to generate documents such as invoices or contracts.
7. Sending emails: You can use bash scripts to send emails with attachments or personalized messages.
8. Automating social media posts: You can use bash scripts to schedule and automate social media posts on platforms such as Twitter or Facebook.
9. Scraping websites: You can use bash scripts to scrape data from websites and store it for later analysis or use.
10. Automating system tasks: You can use bash scripts to automate tasks such as system updates or cleaning up temporary files.
{% endhighlight %}

Decent list, about what I thought it might return, although the Social Media automation seems interesting.

Might as well pursue the Social Media automation and see where that goes.

**Query_02:**

> Referring to the above result, how would I use a Bash Script to schedule and automate posting to Twitter?

**Result_02:**

{% highlight ruby %}
To use a bash script to automate posting to Twitter, you will need to use a command line tool or library that allows you to interact with the Twitter API.

Some options for doing this include:

* twurl: This is a command line tool that allows you to make authenticated requests to the Twitter API. You can use it to create and send tweets, as well as perform other tasks such as following users or retrieving user timelines.
* t: This is a command line utility that simplifies the process of interacting with the Twitter API. You can use it to send tweets, view your timeline, and perform other tasks.
* Twitter CLI: This is a command line interface for Twitter that allows you to perform a variety of tasks, including posting tweets and reading your timeline.

Once you have chosen a tool or library to use, you can then create a bash script that uses it to automate the process of posting to Twitter. For example, you could create a script that reads a list of tweets from a text file and automatically sends them at regular intervals. Alternatively, you could create a script that retrieves data from another source (e.g. a website or database) and uses it to create and send tweets.

To schedule your script to run at regular intervals, you can use a utility such as cron to execute it automatically. For example, you could use cron to run your script every hour, every day, or at any other interval you desire.
{% endhighlight %}

Since I am a **big** fan of CLI tools & Twitter, let's pursue that as a direction.

**Query_03:**

> Referring to the above result, how would I use the 'Twitter CLI' tool on an Ubuntu system?

**Result_03:**

{% highlight ruby %}
To use the Twitter CLI tool on an Ubuntu system, you will first need to install it. You can do this by downloading the latest release from the GitHub repository and extracting the files to a directory on your system.
Once the tool is installed, you will need to create a Twitter Developer account and obtain your API key and secret. You can do this by visiting the Twitter Developer website and following the instructions provided.
Once you have your API key and secret, you will need to configure the Twitter CLI tool to use them. You can do this by running the twitter configure command and following the prompts to enter your API key and secret.
Once the tool is configured, you can use it to perform a variety of tasks, including posting tweets and reading your timeline. Some examples of common commands include:

* twitter post "Hello, world!": This command will post a tweet with the text "Hello, world!"
* twitter timeline: This command will display your home timeline (i.e. the tweets from users you follow)
* twitter user timeline @username: This command will display the timeline of the specified user (replace @username with the desired username)
* For a complete list of available commands, you can consult the documentation or use the twitter help command.
{% endhighlight %}

If I recall correctly, I applied for a Twitter Developer about 7 years ago, and was unsuccessful.

Let's try to maximise the potential for success, this time.

**Query_04:**

> Referring to the above result, what reason do I need to provide to receive a Twitter Developer account?

**Result_04:**

{% highlight ruby %}
To apply for a Twitter Developer account, you will need to provide a reason for why you want to access the Twitter API. This is to help Twitter understand how you plan to use the API and ensure that you are using it in a way that is consistent with their terms of service.
There are a variety of reasons you might want to access the Twitter API, such as:

* Building a Twitter bot [YES]
* Analyzing Twitter data for research or business purposes [YES]
* Integrating Twitter functionality into a mobile or web app [YES]
* Automating tasks such as posting tweets or sending direct messages [YES]
* All the above ... 8-)

When you apply for a Twitter Developer account, you will be asked to provide a brief description of your project and how you plan to use the API. You should be as specific as possible in your description to help Twitter understand your needs and ensure that you are granted the necessary permissions.
It is also a good idea to familiarize yourself with the Twitter Developer Agreement and Developer Policy before applying, as these documents outline the terms and conditions under which you can use the Twitter API.
{% endhighlight %}

Let's ask the AI for direct help with this task.

**Query_05:**

> Show me how to write a brief description to support my Twitter Developer account.

**Result_05:**

{% highlight ruby %}
Here is an example of how you might write a brief description to support your Twitter Developer account application:

  "I am building a Twitter bot that will automatically post updates about a
  specific topic. The bot will use the Twitter API to search for tweets
  containing certain keywords and retweet them to a dedicated account. The
  purpose of the bot is to provide a curated feed of information on the
  chosen topic to users who follow the account. I will only be accessing
  public data through the API and will not be collecting any personal
  information or engaging in spamming or abusive behavior. I plan to use the
  API in accordance with the Twitter Developer Agreement and Developer Policy."

In this example, the description provides a clear and concise overview of the project, outlining its purpose and explaining how the API will be used. It also mentions the specific API endpoints that will be accessed and reaffirms the commitment to following the terms of service.
When writing your own description, be sure to include information about the specific API endpoints you will be accessing, the purpose of your project, and any other relevant details. You should also make it clear that you understand and will comply with the terms of service.
{% endhighlight %}

Let's push the AI, and see if it generates some novel content or just rephrases the previous result.

My bet? Rehash.

**Query_06:**

> Referring to the result above, I am really motivated to quality for a Twitter Developer account, describe to me how I would maximise my opportunity to get a positive result, yet not be repetitive nor seem desperate.

**Result_06:**

{% highlight ruby %}
* To maximize your chances of getting a positive result when applying for a Twitter Developer account, it is important to be thorough and well-prepared. Here are some tips to help you increase your chances of success:
* Read the guidelines carefully: Make sure you understand the requirements and expectations for Twitter Developer account applicants. This will help you tailor your application to meet the needs of the review team.
* Be specific: Provide as much detail as possible about your project and how you plan to use the API. This will help the review team understand the value and purpose of your project, and ensure that you are granted the necessary permissions.
* Be honest: Be upfront about the capabilities and limitations of your project. If you are not sure about something, it is better to admit it and ask for clarification than to make false or misleading statements.
* Follow the rules: Make sure you are familiar with the Twitter Developer Agreement and Developer Policy, and be sure to comply with these guidelines when using the API.
* Keep it concise: While it is important to provide enough information to support your application, try to avoid repeating yourself or going into unnecessary detail. Keep your description concise and to the point.
* Use examples: If possible, provide examples of how you plan to use the API or any relevant experience you have. This can help the review team better understand your project and its potential value.
* Proofread: Make sure to double check your application for spelling and grammar mistakes, as well as any other errors that could affect the clarity or accuracy of your description.
* By following these tips, you can increase your chances of getting a positive result when applying for a Twitter Developer account. Remember to be honest, thorough, and respectful in your application, and you should be well on your way to success.
{% endhighlight %}

Pleasantly surprised! That was a far more comprehensive and helpful result than I was expecting. I quite liked the bit on being honest, and stating your limitations upfront.

Too many people are willing or even happy to, frankly, bullshit.

OK, finally, I am going to ask the AI to source me the following information:

* The main Twitter website
* The current reference to the Twitter Developer accounts
* The current API reference documentation

**Query_07:**

> Referring to the result above, detail the full hyperlink references for the following items: the main Twitter website; the current reference to the Twitter Developer accounts and the current API reference documentation. Present that information in a list form using bullet points, with the relevant headings.

**Result_07:**

{% highlight ruby %}
Here is a list of the hyperlink references you requested:

* Main [Twitter] website: https://twitter.com/
* [Twitter Developer] accounts: https://developer.twitter.com/en/docs/twitter-api/getting-started/getting-access-to-the-twitter-api
* [Twitter API] reference documentation: https://developer.twitter.com/en/docs/twitter-api/reference
{% endhighlight %}

Verdict?

I like it. With 7 questions I have gone from wanting to make a tool using Bash to now I will be applying to get a Twitter Developer account. With a far better understanding of what the current obligations are, and with a practical & reasonable framework to support the application.

Once the application has been submitted, and I am informed of the result, I will let you know.

**References:**

  - [ChatGPT Magic]
  - [Nate McCallister]
  - [Twitter]
  - [Twitter Developer]
  - [Twitter API]

[ChatGPT Magic]: https://entreresource.com/chatgpt-magic-for-bloggers/
[Nate McCallister]: https://twitter.com/entreresources
[Twitter]: https://twitter.com/
[Twitter Developer]: https://developer.twitter.com/en/docs/twitter-api/getting-started/getting-access-to-the-twitter-api
[Twitter API]: https://developer.twitter.com/en/docs/twitter-api/reference
