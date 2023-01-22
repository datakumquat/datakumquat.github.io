---
layout: post
title:  "Rebuild A Better Ubuntu"
date:   2023-01-22 15:33:34 +1300
categories: blog update
---
This tutorial will assist you to reinstall a better version of Ubuntu, one that is secure and private.

Note: This is [Ubuntu Desktop], not [OpenBSD], so take `secure` and `private` with a grain of Salt or 10.

**Prerequisites:**

{% highlight ruby %}
  - A prepared install medium (USB HDD) containing the latest Ubuntu Desktop 22.04 LTS version
  - A basic competency in using the Linux command line on an Ubuntu 64Bit Operating System
{% endhighlight %}

**New Operating System:**

{% highlight ruby %}
# REF https://help.ubuntu.com/community/Full_Disk_Encryption_Howto_2019
# REF https://jumpcloud.com/blog/how-to-enable-full-disk-encryption-ubuntu-22-04
# Install Ubuntu 22.04 LTS x86_64
# Parameter_01: ZFS
# Parameter_02: Encrypted Disk
{% endhighlight %}

Once the new Ubuntu 22.04 LTS has rebooted, login with your Encryption Key and User Password.

> For the following process, you will initially require access to the GNOME Terminal. Once you have installed and/or configured the Terminator Terminal Emulator (Terminator), exit GNOME Terminal.

**Notes:**

{% highlight ruby %}
1. All commands unless otherwise stated require the use of the 'SUDO' command
2. All commands unless otherwise stated are to be executed in the $USER Home_Directory
3. Follow this process as it is written, as this will move from System to User tools
{% endhighlight %}

**Update & Upgrade the system:**

{% highlight ruby %}
$ sudo apt update && sudo apt upgrade
{% endhighlight %}

**Setup cURL:**

{% highlight ruby %}
# REF https://curl.se/
# Install cURL
$ sudo apt install curl
$ curl --version
curl 7.81.0 (x86_64-pc-linux-gnu) libcurl/7.81.0 OpenSSL/3.0.2 zlib/1.2.11 brotli/1.0.9 zstd/1.4.8 libidn2/2.3.2 libpsl/0.21.0 (+libidn2/2.3.2) libssh/0.9.6/openssl/zlib nghttp2/1.43.0 librtmp/2.3 OpenLDAP/2.5.13
{% endhighlight %}

**Switch default Terminal:**

{% highlight ruby %}
# REF https://gnome-terminator.org
# Install Terminator Terminal Emulator
$ sudo apt install terminator
$ terminator --version
terminator 2.1.1
{% endhighlight %}

**New SSH_Key:**

{% highlight ruby %}
# REF https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
# Create new SSH Private Key
$ ssh-keygen -t ed25519 -C "your_email@example.com"

# Verify key creation
cd ~/.ssh
~/.ssh $ ls -al
total 38
drwx------  2 dk dk   6 Jan 21 14:36 .
drwxr-x--- 21 dk dk  31 Jan 22 15:24 ..
-rw-------  1 dk dk 411 Jan 21 14:33 id_ed25519
-rw-r--r--  1 dk dk 103 Jan 21 14:33 id_ed25519.pub
-rw-------  1 dk dk 806 Jan 21 14:36 known_hosts
-rw-r--r--  1 dk dk 142 Jan 21 14:36 known_hosts.old

# Start ssh-agent
$ eval "$(ssh-agent -s)"

# Add SSH Private key to the ssh-agent
$ ssh-add ~/.ssh/id_ed25519
{% endhighlight %}

**Add new SSH_Key to GutHub:**

{% highlight ruby %}
# REF https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account
# Copy the SSH public key to clipboard
$ cat ~/.ssh/id_ed25519.pub

# Add SSH public key to GitHub account
# REF https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account?tool=webui

# REF https://docs.github.com/en/get-started/getting-started-with-git/setting-your-username-in-git
# Set global Git configs via command line on the Local_Machine
# Use either "User Name" or User Name; either will work, I prefer ""
$ git config --global user.name "User Name"
$ git config --global user.email "user.name@example.com"
{% endhighlight %}

**Setup Python Package Manager (Pip):**

{% highlight ruby %}
# REF https://linuxhint.com/install-python-pip-ubuntu-22-04/
# Install Pip
$ sudo apt install python3-pip
$ pip --version
pip 22.0.2 from /usr/lib/python3/dist-packages/pip (python 3.10)
{% endhighlight %}

**Setup OpenSSH-Server:**

{% highlight ruby %}
# REF https://linuxhint.com/install-enable-openssh-ubuntu-22-04/
# Install OpenSSH Server for Remote access
$ apt search openssh-server
$ sudo apt install openssh-server ssh-askpass
$ sshd -v
unknown option -- v
OpenSSH_8.9p1 Ubuntu-3ubuntu0.1, OpenSSL 3.0.2 15 Mar 2022
[TRUNCATED]

# Backup `sshd_config`
$ sudo cp -v /etc/ssh/sshd_config /etc/ssh/sshd_config.backup

# Modify /etc/ssh/sshd_config
$ sudo nano /etc/ssh/sshd_config

# REF https://linuxhint.com/sshd-config-file-complete-guide-for-linux/
# Suggested mods
#
# Port=7931 [Non-standard Port numbers; odds only is easy to see in Logs]
# ListenAddress 0.0.0.0 [Reduce potential for IP-based weirdness]
# PermitRootLogin=YES [You just never know 8-)]
# LoginGraceTime=1m [Limit duration; go lower if you are paranoid]
# MaxAuthTries=3 [Limit events]
# MaxSessions=3 [Limit sessions]
# PasswordAuthentication=yes [Keep YES until SSH_Keys used & tested]
# PermitEmptyPasswords=no ['nuff said]

# Restart OpenSSH-Server
$ sudo systemctl restart ssh
{% endhighlight %}

**Install Brave Browser Latest:**

{% highlight ruby %}
# REF https://brave.com/linux/
# Download and add Brave Browser Key & APT repository to System
$ sudo apt install brave-browser
$ brave-browser --version
Brave Browser 109.1.47.171
{% endhighlight %}

**Setup Ruby:**

{% highlight ruby %}
# REF https://www.ruby-lang.org/en/documentation/installation/#apt
# Install Ruby
$ sudo apt install ruby-full ruby-devel
$ ruby --version
ruby 3.0.2p107 (2021-07-07 revision 0db68f0233) [x86_64-linux-gnu]
$ gem --version
3.3.5
{% endhighlight %}

**Setup Jekyll Static Site:**

{% highlight ruby %}
# REF https://jekyllrb.com/
# Install Rubygems `bundler` `jekyll`
$ gem update
$ gem install bundler jekyll webrick

# Create a new Jekyll Static Site
$ jekyll new jekyll_static_site

# Change to the new site directory
$ cd jekyll_static_site

# Start Jekyll Server
$ bundle exec jekyll serve

# Navigate to localhost:4000
$ brave-browser http://localhost:4000
$ brave-browser http://0.0.0.0:4000

# These 2 commands will cause a CPU-related error
MESA-INTEL: warning: Performance support disabled, consider sysctl dev.i915.perf_stream_paranoid=0

# To remove this error for this current User login-session only:
$ sudo sysctl dev.i915.perf_stream_paranoid=0

# To fix this issue, follow this thread to the lower solution
# REF https://ubuntuforums.org/showthread.php?t=2457426
{% endhighlight %}

This completes the build for your new Ubuntu operating system.

**This system has the following features:**

  - Full-disk Encryption
  - ZFS
  - cURL
  - Terminator Terminal
  - New SSH_Key
  - GitHub access using Git & SSH
  - Brave Browser
  - Python3
  - Python Package Manager (Pip)
  - Full Ruby 2.3
  - Functional Jekyll-based static site generator.

If any of this process fails, refer to any error to see if this was a misconfiguration issue.

If not a misconfiguration, use the installed application Manuals/Helpfiles to fault find.

After that, [Google Search] or [Stack Overflow] are your friend ... or not.

**Invoke the onboard help using:**

{% highlight ruby %}
  $ man curl
  $ man terminator
  $ man ssh
  $ man git
  $ man pip
  $ man sshd
  $ man brave-browser
  $ man ruby
  $ gem --help
  $ bundle --help
{% endhighlight %}

**TODO:**

  - Build an unattended install script
  - Benchmark full Manual/Unattended install

**References:**

  - [Ubuntu Desktop]
  - [OpenBSD]
  - [Full disk encryption HOWTO]
  - [Full disk encryption Ubuntu 22.04 LTS]
  - [cURL]
  - [Terminator Terminal Emulator]
  - [SSH Keys]
  - [Create SSH_Keys GitHub]
  - [Add SSH_Keys GitHub]
  - [Install Python Package Manager onto Ubuntu]
  - [Modify sshd_config on Linux]
  - [Install Brave Browser]
  - [Install Ruby Full onto Ubuntu]
  - [Install Jekyll Static Site dependencies]
  - [Google Search]
  - [Stack Overflow]

[Ubuntu Desktop]: https://ubuntu.com/download/desktop
[OpenBSD]: https://www.openbsd.org/
[Full disk encryption HOWTO]: https://help.ubuntu.com/community/Full_Disk_Encryption_Howto_2019
[Full disk encryption Ubuntu 22.04 LTS]: https://jumpcloud.com/blog/how-to-enable-full-disk-encryption-ubuntu-22-04
[cURL]: https://curl.se/
[Terminator Terminal Emulator]: https://gnome-terminator.org/
[SSH Keys]: https://www.ssh.com/academy/ssh-keys
[Create SSH_Keys GitHub]: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent 
[Add SSH_Keys GitHub]: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account
[Install Python Package Manager onto Ubuntu]: https://linuxhint.com/install-python-pip-ubuntu-22-04/
[Install OpenSSH-Server onto Ubuntu]: https://linuxhint.com/install-enable-openssh-ubuntu-22-04/
[Modify sshd_config on Linux]: https://linuxhint.com/sshd-config-file-complete-guide-for-linux/
[Install Brave Browser]: https://brave.com/linux/
[Install Ruby Full onto Ubuntu]: https://www.ruby-lang.org/en/documentation/installation/#apt
[Install Jekyll Static Site dependencies]: https://jekyllrb.com/
[Google Search]: https://www.google.com/
[Stack Overflow]: https://stackoverflow.com/
