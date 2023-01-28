---
layout: post
title:  "Got Anaconda In Yet"
date:   2023-01-23 23:20:40 +1300
categories: blog update
---
This tutorial is a quick overview of the process to install Anaconda on an Ubuntua O/S.

**Upgrade & Update system:**

{% highlight ruby %}
# Update & Upgrade system
$ sudo apt update && sudo apt upgrade -y
{% endhighlight %}

**Install IDLE Editor:**

{% highlight ruby %}
# REF https://realpython.com/python-idle/
# Install IDLE Python IDE
$ apt search idle
$ sudo apt install idle
dpkg --list | grep ii | grep idle
ii   idle   3.10.6-1~22.04   all   IDE for Python using Tkinter (default version)
{% endhighlight %}

**Install Anaconda dependencies:**

{% highlight ruby %}
# REF https://www.anaconda.com/products/distribution
# REF https://docs.anaconda.com/anaconda/install/linux/
# Install Anaconda dependencies
$ sudo apt install libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2
$ sudo apt install libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6
{% endhighlight %}

**Verify Anaconda installer:**

{% highlight ruby %}
# REF https://docs.anaconda.com/anaconda/install/hashes/Anaconda3-2022.10-Linux-x86_64.sh-hash/
# Verify the Anaconda Installer Hash
$ shasum -a 256 Anaconda3-2022.10-Linux-x86_64.sh
e7ecbccbc197ebd7e1f211c59df2e37bc6959d081f2235d387e08c9026666acd  Anaconda3-2022.10-Linux-x86_64.sh
{% endhighlight %}

**Install Anaconda:**

{% highlight ruby %}
# Install Anaconda
# Follow the instruction, accept the defaults
$ /usr/bin/bash Anaconda3-2022.10-Linux-x86_64.sh
{% endhighlight %}

**Initialize Anaconda:**

{% highlight ruby %}
# Press Enter to review the license agreement.
# Enter “yes” to agree to the license agreement
# Use Enter to accept the default install location or use CTRL+C to cancel the installation
# The installer prompts you to choose whether to initialize Anaconda Distribution by running conda init
$ conda init
{% endhighlight %}

**Set Auto_Activate_Base:**

{% highlight ruby %}
# Installer finishes and displays, “Thank you for installing Anaconda3!”
# The base environment is activated by default
$ conda config --set auto_activate_base True
# The base environment is not activated by default
$ conda config --set auto_activate_base False
{% endhighlight %}

To select Activate_Base and turn it On/Off, create 2 ALIASES in ~/.bashrc or ~/.bash_aliases

{% highlight ruby %}
# Base=ON
alias conon='conda config --set auto_activate_base True'
# Base=OFF
alias conoff='conda config --set auto_activate_base False'
{% endhighlight %}

**Using the ALIASES:**

{% highlight ruby %}
# activate_base_auto=True
dk ~ $ conon
dk ~ $ source ~/.bashrc
(base) dk ~ $

# activate_base_auto=False
(base) dk ~ $ conoff
(base) dk ~ $ source ~/.bashrc
dk ~ $
{% endhighlight %}

**Verify Install:**

{% highlight ruby %}
# REF https://docs.anaconda.com/anaconda/install/verify-install/
# Verify Anaconda install
# Display a list of installed packages and their versions
$ conda list
# Execute the Python REPL
$ python
# Exit the Python REPL
$ quit()
# Open Anaconda Navigator
$ anaconda-navigator
{% endhighlight %}

Now, you should have a working Anaconda install, that looks like this:

![This is a screenshot image of the running Anaconda application on an Ubuntu Desktop](/assets/img/Running_Anaconda_Application_Ubuntu_OS_2023-01-23_21-45-03.png)

The next course of action will be a tutorial on installing Pip and other PyQuant-related packages.

**References:**

  - [Python-IDLE]
  - [Anaconda distribution]
  - [Install Anaconda on Linux]
  - [Anaconda Installer Hash]
  - [Verify Install]

[Python-IDLE]: https://realpython.com/python-idle/
[Anaconda distribution]: https://www.anaconda.com/products/distribution
[Install Anaconda on Linux]: https://docs.anaconda.com/anaconda/install/linux/
[Anaconda Installer Hash]: https://docs.anaconda.com/anaconda/install/hashes/Anaconda3-2022.10-Linux-x86_64.sh-hash/
[Verify Install]: https://docs.anaconda.com/anaconda/install/verify-install/
