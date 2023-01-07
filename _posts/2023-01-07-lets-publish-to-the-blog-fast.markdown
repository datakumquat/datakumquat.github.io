---
layout: post
title:  "Lets Publish to the Blog Fast!"
date:   2023-01-07 21:18:15 +1300
categories: jekyll blog
---
One of the key benefits of using a GitHub Pages static website is that you can use the Git tool system to interact with the blog for everything:

  - `git status`
  - `git add`
  - `git commit`
  - `git push`

These are almost the only Git commands that you will need with a GitHub Pages site.

On my Ubuntu/Debian systems, whether they are Desktop, Server or Raspberry Pi, I have an extensive list of `ALIASES` for everything. Usually I use a separate `~/.bash_aliases` file but lately I have been adding all of the `ALIASES` into the `~/.bashrc` file at the bottom.

Back to the GitHub Pages site.

* Main directory: /home/datakumquat/Projects/datakumquat.github.io
* Posts directory: /home/datakumquat/Projects/datakumquat.github.io/_posts
* Site assets: /home/datakumquat/Projects/datakumquat.github.io/_site

The relevant [Data Kumquat] site ALIASES are:

{% highlight ruby %}
## Data Kumquat Blog
alias gas='git status'
alias gad='git add --all'
alias gac='git commit -m "Modified blog post with minor grammar and content adjustment"'
alias gap='git push -u origin main'
alias pdk='cd /home/datakumquat/Projects/datakumquat.github.io/ && clear && pwd && ls'
alias pdp='cd /home/datakumquat/Projects/datakumquat.github.io/_posts && clear && pwd && ls -al'
alias pes=bundle exec jekyll serve --incremental'
# Combined commands for complete process
alias pub='cd /home/datakumquat/Projects/datakumquat.github.io/ \
&& git status && sleep 1 \
&& git add --all && sleep 1 \
&& git commit -m "Modified blog post with minor grammar and content adjustment" && sleep 1 \
&& git push -u origin main && sleep 1 \
&& clear && echo "Blog post published..."'

{% endhighlight %}

* Note 1: I include a SLEEP=1 period between commands, so I can see the process.
* Note 2: If this was a Production repository, my commit messages would be better ... honest.
* Note 3: I guess for a new Post, I could write a Bash automation for a better commit message.

**The usual process:**

* Change into the relevant `_posts` directory
* Create new Markdown file
* Edit & save the file
* Change back to the main directory
* Use `git status` to confirm the recent changes
* Use `git add` to add the recent changes
* Create a terse but meaningful commit message
* Push the changes to the REMOTE repository

All standard stuff.

**The usual ALIASES commands (In order):**

{% highlight ruby %}
1. $ gas
2. $ gad
3. $ gac
4. $ gap
{% endhighlight %}

**The revised, faster process:**

Once I have finished editing the new blog post, at the command line anywhere on the system, I type in `pub` and select [ENTER], and in about 10 seconds, I see the message 'Blog post published...'

Give it 5 minutes, then refresh the browser and see the changes live on the [Data Kumquat] site.

Now that my learnings and experimentation with ChatGPT, other LLM, the [AI Content Reactor] course, the upcoming [Getting Started with Python for Quant Finance] course ... if I am not finding ways to test & implement the Automation of *everything*, life will get interesting.

Automate or Die.

[Data Kumquat]: https://datakumquat.github.io/
[AI Content Reactor]: https://aicontentreactor.com/
[Getting Started with Python for Quant Finance]: https://gettingstartedwithpythonforquantfinance.com/

**References:**

  - [Data Kumquat]
  - [AI Content Reactor]
  - [Getting Started with Python for Quant Finance]
