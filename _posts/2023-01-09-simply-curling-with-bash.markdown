---
layout: post
title:  "Simply Curling with Bash"
date:   2023-01-09 20:45:13 +1300
categories: bash blog
---
Since I was Bashing today for Work on some Web SaaS reporting tasks, I'll keep with the same theme.

You will see the creation of a simple Bash Script that will do nothing more than hit a hyperlink using the tool [cURL] and return the contents, unformatted and ugly.

It will run, but making it pretty or readable for Humans will be your job.

Open up ChatGPT, and you will enter a simple brief and get this done fast.

** Query_01:**

> I will provide you with a HTTPS hyperlink between double quotes and you will do nothing until instructed to do so. The hyperlink is "https://discuss.widgets.com/u/mike_jules/activity/solved". Using the Bash scripting language, create a script that will use cURL to source the information and output into a file titled 'curl_output_file.txt'

**Result_01_01:**

> To use cURL to download the content of the URL "https://discuss.widgets.com/u/mike_jules/activity/solved" and save it to a file called "curl_output_file.txt", you can use the following Bash script:

**Result_01_Code:**

{% highlight ruby %}
#!/bin/bash

curl "https://discuss.widgets.com/u/mike_jules/activity/solved" > curl_output_file.txt
{% endhighlight %}

**Result_01_02:**

> This script will use cURL to download the content of the specified URL and save it to a file called "curl_output_file.txt". The file will be created if it doesn't already exist, and the existing contents will be overwritten if the file already exists. To use this script, make sure to save it to a file with a .sh extension and make it executable by running the following command:

{% highlight ruby %}
chmod +x script.sh
{% endhighlight %}

**Result_01_03:**

> You can then run the script by typing ./script.sh at the command prompt.

I did not prompt for that extra information, in terms of the file format, naming or executing string.

Workable, but let's ensure that it will run on any system that uses Bash (In theory).

**Query_02:**

> Referring to the above result, regenerate the original Bash script with the code fix above. Set the hyperlink as a variable using 'url='. Also set the filename to equal 'curl_output_file.txt'. Ensure that you insert a Bash Shebang using the 'env' variable at the top of the file. Also, ensure that the code is commented for future Human code maintainers. Add the line '# EOF' twice lines below the last current line. Do not provide an explanation for this new code and do not advise how to run the script.

**Result_02_01:**

> Here is the modified Bash script with a shebang and comments:

**Result_02_Code:**

{% highlight ruby %}
#!/usr/bin/env bash

# set hyperlink
# Modify the hyperlink to suit your needs
url="https://discuss.widgets.com/u/Mke_Jules/activity/solved"
# set filename
# Modify the output filename to suit your needs also
filename=curl_output_file.txt

# Use cURL to download the content of the URL and save it to the curl_output_file.txt
curl "$url" > "$filename"

# EOF
{% endhighlight %}

Verdict?

Once again, a simple result and this would certainly be very helpful for a new Bash user. ChatGPT now seems to provide additional information to a Code query that is both contextual and practical.

The best part is that you can always use the phrase, 'Do not provide an explanation for this new code and do not advise how to run the script.' to remove any over-sharing from ChatGPT.

Time to completion: Likely 2 minutes of briefing and ChatGPT time.

A suggestion to reduce the overall process time:

  - Use Voice-to-Text to FILE
  - Copy&paste into ChatGPT
  - Review using Voice-to-Text to FILE
  - Copy&paste into ChatGPT
  - Repeat until complete

**References:**

  - [cURL]

[cURL]: https://curl.se/
