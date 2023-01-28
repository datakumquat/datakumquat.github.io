---
layout: post
title:  "Start Anaconda Navigator Using A Menu"
date:   2023-01-27 12:44:56 +1300
categories: blog update
---
As part of the [PyQuantNews] course, we have to install [Anaconda Navigator], as a core tool for learning and testing. The instructions are written from the perspective of a MacOS user, so that when you finish, there is GUI application available in the system menu.

However with Ubuntu Linux, we do not get that luxury. Maybe not a luxury, but surely a convenience.

There are some [Mesa-LibGL] errors that I am getting when invoking `anaconda-navigator` from the commandline. While I was researching that Mesa-LibGL warning issue, I thought that it would be nice to start Anaconda Navigator from the Ubuntu Activities menu, and not using `$ anaconda-navigator`.

A quick Google Search (Is there any other kind?), these instructions were found in the following Slackoverflow discussion: [Anaconda-Navigator - Ubuntu16.04]

Even though the Ubuntu version used is v16.04, it works as per spec in v22.04 LTS.

**Instructions:**

{% highlight ruby %}
# Navigate to the Desktop directory:
$ cd ~/Desktop
{% endhighlight %}

In an open Terminal, create a new text document called 'anaconda-navigator.desktop'.

{% highlight ruby %}
# Create text file
$ gedit anaconda-navigator.desktop
{% endhighlight %}

Enter the following information into the text document.

{% highlight ruby %}
# Edit anaconda-navigator.desktop
#

#!/usr/bin/env xdg-open
[Desktop Entry]
Name=Anaconda
Version=2.0
Type=Application
Exec=/home/dk/anaconda3/bin/anaconda-navigator
Icon=/home/dk/anaconda3/lib/python3.9/site-packages/anaconda_navigator/static/images/anaconda-icon-256x256.png
Comment=Open Anaconda Navigator
Terminal=false
{% endhighlight %}

Save and close the file.

Move the 'anaconda-navigator.desktop' file to the system Applications directory.

{% highlight ruby %}
# Move file to Applications directory
$ mv anaconda-navigator.desktop ~/.local/share/applications/
{% endhighlight %}

**Test the new Application menu entry:**

  - Exit the Terminal
  - Navigate to the Ubuntu Activities menu, type in 'anaconda', the icon will present
  - Click and the application will open
  - Screenshot below

![Screenshot image of Anaconda Navigator in the Ubuntu Activities menu](/assets/img/Screenshot_Anaconda_Navigator_in_Ubuntu_Activities_Menu_2023-01-27.png)

I would strongly suggest that any quality application that you need to open using the commandline, should have an applications menu entry created, and accessed through the menu.

It just looks better. However as always with most Open Source Software, the choice is yours.

**References:**

  - [PyQuantNews]
  - [Anaconda Navigator]
  - [Mesa-LibGL]
  - [Anaconda-Navigator - Ubuntu16.04]

[PyQuantNews]: https://pyquantnews.podia.com/
[Anaconda Navigator]: https://docs.anaconda.com/navigator/index.html
[Mesa-LibGL]: https://www.mesa3d.org/
[Anaconda-Navigator - Ubuntu16.04]: https://stackoverflow.com/questions/43030871/anaconda-navigator-ubuntu16-04
