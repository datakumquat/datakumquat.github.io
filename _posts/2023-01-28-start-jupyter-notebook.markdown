---
layout: post
title:  "Start Jupyter Notebook"
date:   2023-01-28 12:36:47 +1300
categories: blog update
---
As part of the [PyQuantNews] course, we have to install [Jupyter Notebook], a core application for learning.

This article will take you through the process of Starting and Stopping a Jupyter Notebook from a virtual environment, titled `my_quant_lab` and show various scenarios that arise from using it.

**Prerequisites:**

  - Ubuntu 20.04/22.04 (LTS)
  - Python version 3.9+
  - Terminal (Default Gnome-Terminal
  - Terminator (Enhanced Gnome-Terminal)
  - Brave Browser

**Instructions to Start a Jupyter Notebook:**

{% highlight ruby %}
# Start Ananconda Navigator
Activities > anaconda
{% endhighlight %}

If you do not have an entry in the Activities menu for Anaconda, visit the article [Start Anaconda Navigator Using A Menu] and work through that, then return to here and continue with the next process.

{% highlight ruby %}
# Navigate to Environments
Select 'my_quant_lab', wait until it loads
{% endhighlight %}

{% highlight ruby %}
# Load Environment
Select Play Button, choose [Open Terminal] option

# Note: This action loads the default System Terminal,
# which in this case is Gnome Terminal, v3.44.0

Currently you are a default User $SHELL (/bin/bash) but not the main $SHELL
{% endhighlight %}

{% highlight ruby %}
# Note: Anaconda Navigator opens an instance of
# Gnome Terminal but not in the default Userspace
dk@qbox:~$
{% endhighlight %}

{% highlight ruby %}
# To confirm which $SHELL you are in, do this:
$ echo $SHELL
/bin/bash
{% endhighlight %}

{% highlight ruby %}
# Source ~/.bashrc to force the $SHELL to use ~/.bashrc
$ source ~/.bashrc
dk ~ $
{% endhighlight %}

If you have setup the Bash ALIAS as mentioned in the [Got Anaconda In Yet] article, do this:

{% highlight ruby %}
# Activate the Python Quant Environment
#
# ALIAS Method
$ conon
$ source ~/.bashrc
(base) dk ~ $
{% endhighlight %}

If you do not have the Bash ALIAS as mentioned in the [Got Anaconda In Yet] article, do this:

{% highlight ruby %}
# Activate the Python Quant Environment
#
# Manual Method
$ conda config --set auto_activate_base True
$ source ~/.bashrc
(base) dk ~ $
{% endhighlight %}

{% highlight ruby %}
# Start Jupyter Notebook; Logout flow
(base) dk ~ $ jupyter notebook
{% endhighlight %}

{% highlight ruby %}
# If Successful
Browser_Tab = http://localhost:8888/tree?
{% endhighlight %}

{% highlight ruby %}
# Logout of Jupyter Notebook
Select [Logout]
Browser_Tab = http://localhost:8888/logout
{% endhighlight %}

{% highlight ruby %}
# Log back in from Logout Tab
Select [Proceed to the login page]

This will load a page at http://localhost:8888/login
which will request a [Password or token:]

To discover this, you will need the URL of a currently
running Jupyter Service and it's token, do this:

# Password or Token Discovery
# In another Terminal or Terminal Tab as the first one
# is still running the Jupyter Notebook session
$ jupyter notebook list
Currently running servers:
http://localhost:8888/?token=054e8ee5072c48016fc974ab42845e24d0b060f718ffa794 :: /home/dk
{% endhighlight %}

{% highlight ruby %}
# Use the Discovered Token to Login
# Copy&Paste the Token from the URL string into 
# the [Password or token:] input field, Select [Log in]

# Note: Only use the Token numbers, not the string token=054...794
054e8ee5072c48016fc974ab42845e24d0b060f718ffa794

# If Successful
Browser_Tab = http://localhost:8888/tree?

# If Unsuccessful
Browser_Tab = http://localhost:8888/login?next=%2F
{% endhighlight %}

{% highlight ruby %}
# Start Jupyter Notebook; Logout flow
(base) dk ~ $ jupyter notebook

# Logout of Jupyter Notebook
Select [Quit]
Browser_Tab = http://localhost:8888/tree?
{% endhighlight %}

You will now see a popup message stating:

> Server stopped.
> You have shut down Jupyter. You can now close this tab.

> To use Jupyter again, you will need to relaunch it.

Screenshot below:

![Screenshot image of Jupyter Notebook Server Stopped message](/assets/img/Screenshot_Jupyter_Notebook_Server_Stopped_2023-01-29.png)

{% highlight ruby %}
# Exit the current Jupyter Notebook session,
# by closing the relevant tab
Close Browser_Tab = http://localhost:8888/tree?
{% endhighlight %}

This is a straightforward process but you need to remember where you are in the $SHELL at all times.

If in doubt, close the Terminal(s) & Browser; start again.

**References:**

  - [PyQuantNews]
  - [Jupyter Notebook]
  - [Start Anaconda Navigator Using A Menu]
  - [Got Anaconda In Yet]

[PyQuantNews]: https://pyquantnews.podia.com/
[Jupyter Notebook]: https://jupyter.org/
[Start Anaconda Navigator Using A Menu]: https://datakumquat.github.io/blog/update/2023/01/26/start-anaconda-navigator-using-a-menu.html
[Got Anaconda In Yet]: https://datakumquat.github.io/blog/update/2023/01/23/got-anaconda-in-yet.html

