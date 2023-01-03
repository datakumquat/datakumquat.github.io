---
layout: post
title:  "Create A GitHub Pages Site Using Jekyll"
date:   2023-01-03 12:42:21 +1300
categories: jekyll github
---
START_OF_ARTICLE

## Introduction

This tutorial details the process to configure, create and publish a new [GitHub Pages] static site using the Ruby Gem package, [Jekyll].

The benefit of this particular stack is that it is free as in cost, and free as in you only need open source software to complete the task. It also gives you further experience in the use of the GitHub platform beyond pushing commits, to showcase not only your writing, but your GitHub skills.

At the end of this tutorial, you will have a basic but working GitHub Pages sites, using the Ruby Gem Jekyll, that provides a platform to publish content to, using either [Cleartext], [Markdown] or [Kramdown]. Once this is working, you can read further and extend this as you need to.

## Prequisites

To complete this tutorial, you will need:

 - One Ubuntu 20.04/22.04 Desktop setup in the default configuration with [sudo] privileges
 - New [SSH Keys] generated on your Local_Machine and added to your GitHub account
 - Git installed on your Local_Machine
 - A functioning GitHub account where you are the Owner/Admin
 - A Linux Terminal [Gnome-Terminal] or [Xterm]
 - Familiarity with using the Linux Command Line
 - A maximum of 2 hours

**Create new REMOTE repository using the GitHub UI:**

{% highlight ruby %}
https://github.com/youtheuser/youtheuser.github.io
{% endhighlight %}

**Create README.md:**

This new REMOTE repository will be empty, so you will need to add one file to enable selection of the `main` branch, to be served via the repository `/ROOT.`
Do this using the GitHub UI.

#### Select Main branch
**Source:**
Goto Settings > Pages > Build and Deployment > Source, select `Deploy from a branch.`
**Branch:**
Goto Settings > Pages > Build and Deployment > Branch, select `main` and `/(root)`

**Create a LOCAL version, using the GitHub UI, to clone the REMOTE repository using SSH:**

Using the `git` command in a Linux terminal.

{% highlight ruby %}
$ git clone git@github.com:youtheuser/youtheuser.github.io.git
{% endhighlight %}

**Once complete, change into LOCAL repository:**

{% highlight ruby %}
$ cd youtheuser.github.io
{% endhighlight %}

**Create a new file titled 'index.html':**

Using the `echo` command.

{% highlight ruby %}
$ echo "Hello World" > index.html
{% endhighlight %}

**Check the current LOCAL repository:**

Using the `ls -al` command, check the current contents of this directory.

{% highlight ruby %}
$ ls -al
total 13
drwxrwxr-x 3 youtheuser youtheuser  5 Jan  3 11:23 .
drwxrwxr-x 5 youtheuser youtheuser  5 Jan  3 11:23 ..
drwxrwxr-x 8 youtheuser youtheuser 14 Jan  3 11:24 .git
-rw-rw-r-- 1 youtheuser youtheuser 12 Jan  3 11:23 index.html
-rw-rw-r-- 1 youtheuser youtheuser 23 Jan  3 11:23 README.md
{% endhighlight %}

**Add the new 'index.html' file:**

Use the `git add` command.

{% highlight ruby %}
$ git add --all
{% endhighlight %}

**Commit the new 'index.html' file:**

Use the `git commit` command.

{% highlight ruby %}
$ git commit -m "Initial commit from LOCAL repository"
{% endhighlight %}

**Push the LOCAL changes to the REMOTE repository:**

Use the `git push` command.

{% highlight ruby %}
$ git push -u origin main
{% endhighlight %}

**View the modified REMOTE Github Pages site:**

Using the Google Chrome web browser.

{% highlight ruby %}
$ google-chrome-stable https://youtheuser.github.io/
{% endhighlight %}

There is a now a working but minimalist Github Pages site at:

[https://youtheuser.github.io/]

**Change into LOCAL repository:**

{% highlight ruby %}
$ cd youtheuser.github.io
{% endhighlight %}

**Confirm current files in the directory:**

{% highlight ruby %}
$ ls -al
total 13
drwxrwxr-x 3 youtheuser youtheuser  5 Jan  3 11:23 .
drwxrwxr-x 5 youtheuser youtheuser  5 Jan  3 11:23 ..
drwxrwxr-x 8 youtheuser youtheuser 14 Jan  3 11:24 .git
-rw-rw-r-- 1 youtheuser youtheuser 12 Jan  3 11:23 index.html
-rw-rw-r-- 1 youtheuser youtheuser 23 Jan  3 11:23 README.md
{% endhighlight %}

**Create a new Jekyll site:**

Using the `jekyll new` command.

{% highlight ruby %}
$ jekyll new --skip-bundle .
Conflict: /home/youtheuser/Projects/youtheuser.github.io exists and is not empty.
Ensure /home/youtheuser/Projects/youtheuser.github.io is empty or else try again with `--force` to proceed and overwrite any files.
{% endhighlight %}

**As this directory is not empty, use the `--force` option:**

{% highlight ruby %}
$ jekyll new --force --skip-bundle .
New jekyll site installed in /home/youtheuser/Projects/youtheuser.github.io.
Bundle install skipped.
{% endhighlight %}

**Modify the Gemfile:**

{% highlight ruby %}
$ nano Gemfile
{% endhighlight %}

Required changes, as follows:

{% highlight ruby %}
Modify:
gem "jekyll", "~> 4.3.1"
To:
# gem "jekyll", "~> 4.3.1"

Modify:
# gem "github-pages", "~> GITHUB-PAGES-VERSION", group: :jekyll_plugins
# REF https://pages.github.com/versions/
To:
gem "github-pages", "~> 227", group: :jekyll_plugins
{% endhighlight %}

**Save and close the Gemfile:**

Use the `Bundler` Gem to install the required dependencies.

{% highlight ruby %}
$ bundle install
Fetching gem metadata from https://rubygems.org/...........
Resolving dependencies...
Using concurrent-ruby 1.1.10
Using public_suffix 4.0.7
Using bundler 2.4.2
Using minitest 5.17.0
Using thread_safe 0.3.6
Using execjs 2.8.1
Using colorator 1.1.0
Using commonmarker 0.23.6
Using unf_ext 0.0.8.2
Using zeitwerk 2.6.6
Using ffi 1.15.5
Using faraday-net_http 3.0.2
Using ruby2_keywords 0.0.5
Using http_parser.rb 0.8.0
Using coffee-script-source 1.11.1
Using eventmachine 1.2.7
Using forwardable-extended 2.6.0
Using liquid 4.0.3
Using mercenary 0.3.6
Using rexml 3.2.5
Using gemoji 3.0.1
Using rouge 3.26.0
Using racc 1.6.2
Using rubyzip 2.3.2
Using jekyll-swiss 1.0.0
Using unicode-display_width 1.8.0
Using i18n 0.9.5
Using safe_yaml 1.0.5
Using jekyll-paginate 1.1.0
Using unf 0.1.4
Using tzinfo 1.2.10
Using ethon 0.16.0
Using faraday 2.7.2
Using jekyll-commonmark 1.4.0
Using addressable 2.8.1
Using em-websocket 0.5.3
Using pathutil 0.16.2
Using kramdown 2.3.2
Using coffee-script 2.4.1
Using rb-inotify 0.10.1
Using nokogiri 1.13.10 (x86_64-linux)
Using rb-fsevent 0.11.2
Using simpleidn 0.2.1
Using sawyer 0.9.2
Using kramdown-parser-gfm 1.1.0
Using jekyll-coffeescript 1.1.1
Using sass-listen 4.0.0
Using terminal-table 1.8.0
Using typhoeus 1.4.0
Using octokit 4.25.1
Using sass 3.7.4
Using dnsruby 1.61.9
Using activesupport 6.0.6
Using jekyll-gist 1.5.0
Using listen 3.7.1
Using jekyll-sass-converter 1.5.2
Using jekyll-watch 2.2.1
Using github-pages-health-check 1.17.9
Using html-pipeline 2.14.3
Using jekyll 3.9.2
Using jekyll-avatar 0.7.0
Using jekyll-commonmark-ghpages 0.2.0
Using jekyll-default-layout 0.1.4
Using jekyll-include-cache 0.2.1
Using jekyll-github-metadata 2.13.0
Using jekyll-feed 0.15.1
Using jekyll-mentions 1.6.0
Using jekyll-redirect-from 0.16.0
Using jekyll-remote-theme 0.4.3
Using jekyll-readme-index 0.3.0
Using jekyll-relative-links 0.6.1
Using jekyll-optional-front-matter 0.3.2
Using jekyll-seo-tag 2.8.0
Using jekyll-sitemap 1.4.0
Using jekyll-theme-architect 0.2.0
Using jekyll-theme-cayman 0.2.0
Using jekyll-theme-hacker 0.2.0
Using jekyll-titles-from-headings 0.5.3
Using jekyll-theme-merlot 0.2.0
Using jekyll-theme-dinky 0.2.0
Using jekyll-theme-leap-day 0.2.0
Using jekyll-theme-modernist 0.2.0
Using jekyll-theme-midnight 0.2.0
Using jekyll-theme-primer 0.6.0
Using jemoji 0.12.0
Using jekyll-theme-minimal 0.2.0
Using jekyll-theme-slate 0.2.0
Using jekyll-theme-tactile 0.2.0
Using jekyll-theme-time-machine 0.2.0
Using minima 2.5.1
Using github-pages 227
Bundle complete! 7 Gemfile dependencies, 91 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
{% endhighlight %}

**Modify the _config.yml file:**

{% highlight ruby %}
$ nano _config.yml
{% endhighlight %}

Modify or delete as required.

{% highlight ruby %}
Modify:
title: Your awesome title
To:
title: This is the title of this blog

Modify:
email: your-email@example.com
To:
email: youtheuser@youtheuser.domain

Modify:
url: "" # the base hostname & protocol for your site, e.g. http://example.com
To:
url: "https://youtheuser.github.io/"

Modify:
twitter_username: jekyllrb
To:
twitter_username: youtheuser

Modify:
github_username: jekyllrb
To:
github_username: youtheuser

# Exclude from processing.
# This is a default list, however being explicit is a better idea
exclude:
  - .sass-cache/
  - .jekyll-cache/
  - gemfiles/
  - Gemfile
  - Gemfile.lock
  - node_modules/
  - vendor/bundle/
  - vendor/cache/
  - vendor/gems/
  - vendor/ruby/
{% endhighlight %}

**Save and close _config.yml**

**The current directory should look like this:**

Using the `ls -al` command in a Linux terminal.

{% highlight ruby %}
~/Projects/youtheuser.github.io $ ls -al
total 53
drwxrwxr-x 4 youtheuser youtheuser   13 Jan  3 13:15 .
drwxrwxr-x 5 youtheuser youtheuser    5 Jan  3 11:23 ..
-rw-r--r-- 1 youtheuser youtheuser  419 Jan  3 12:42 404.html
-rw-r--r-- 1 youtheuser youtheuser  539 Jan  3 12:42 about.markdown
-rw-r--r-- 1 youtheuser youtheuser 2076 Jan  3 13:15 _config.yml
-rw-rw-r-- 1 youtheuser youtheuser 1319 Jan  3 12:53 Gemfile
-rw-rw-r-- 1 youtheuser youtheuser 7435 Jan  3 12:53 Gemfile.lock
drwxrwxr-x 8 youtheuser youtheuser   14 Jan  3 11:24 .git
-rw-r--r-- 1 youtheuser youtheuser   56 Jan  3 12:42 .gitignore
-rw-rw-r-- 1 youtheuser youtheuser   12 Jan  3 11:23 index.html
-rw-r--r-- 1 youtheuser youtheuser  175 Jan  3 12:42 index.markdown
drwxrwxr-x 2 youtheuser youtheuser    3 Jan  3 12:42 _posts
-rw-rw-r-- 1 youtheuser youtheuser   23 Jan  3 11:23 README.md
{% endhighlight %}

**Test your GitHub Pages site locally:**

Using the bundle exec jekyll serve command in a Linux Terminal.

{% highlight ruby %}
$ bundle exec jekyll serve
Configuration file: /home/youtheuser/Projects/youtheuser.github.io/_config.yml
To use retry middleware with Faraday v2.0+, install `faraday-retry` gem
            Source: /home/youtheuser/Projects/youtheuser.github.io
       Destination: /home/youtheuser/Projects/youtheuser.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating... 
       Jekyll Feed: Generating feed for posts
                    done in 0.19 seconds.
 Auto-regeneration: enabled for '/home/youtheuser/Projects/youtheuser.github.io'
/home/youtheuser/gems/gems/jekyll-3.9.2/lib/jekyll/commands/serve/servlet.rb:3:in `require': cannot load such file -- webrick (LoadError)
  from /home/youtheuser/gems/gems/jekyll-3.9.2/lib/jekyll/commands/serve/servlet.rb:3:in `<top (required)>'
  from /home/youtheuser/gems/gems/jekyll-3.9.2/lib/jekyll/commands/serve.rb:184:in `require_relative'
  from /home/youtheuser/gems/gems/jekyll-3.9.2/lib/jekyll/commands/serve.rb:184:in `setup'
  from /home/youtheuser/gems/gems/jekyll-3.9.2/lib/jekyll/commands/serve.rb:102:in `process'
  from /home/youtheuser/gems/gems/jekyll-3.9.2/lib/jekyll/commands/serve.rb:93:in `block in start'
  from /home/youtheuser/gems/gems/jekyll-3.9.2/lib/jekyll/commands/serve.rb:93:in `each'
  from /home/youtheuser/gems/gems/jekyll-3.9.2/lib/jekyll/commands/serve.rb:93:in `start'
  from /home/youtheuser/gems/gems/jekyll-3.9.2/lib/jekyll/commands/serve.rb:75:in `block (2 levels) in init_with_program'
  from /home/youtheuser/gems/gems/mercenary-0.3.6/lib/mercenary/command.rb:220:in `block in execute'
  from /home/youtheuser/gems/gems/mercenary-0.3.6/lib/mercenary/command.rb:220:in `each'
  from /home/youtheuser/gems/gems/mercenary-0.3.6/lib/mercenary/command.rb:220:in `execute'
  from /home/youtheuser/gems/gems/mercenary-0.3.6/lib/mercenary/program.rb:42:in `go'
  from /home/youtheuser/gems/gems/mercenary-0.3.6/lib/mercenary.rb:19:in `program'
  from /home/youtheuser/gems/gems/jekyll-3.9.2/exe/jekyll:15:in `<top (required)>'
  from /home/youtheuser/gems/bin/jekyll:25:in `load'
  from /home/youtheuser/gems/bin/jekyll:25:in `<main>'
{% endhighlight %}

**The Build & Serve has failed due to the lack of the Ruby Gem package: WEBRICK:**

Install the missing package using the `bundle add webrick` command.

{% highlight ruby %}
$ bundle add webrick
Fetching gem metadata from https://rubygems.org/.........
Resolving dependencies...
Fetching gem metadata from https://rubygems.org/.........
Resolving dependencies...
Using minitest 5.17.0
Using public_suffix 4.0.7
Using zeitwerk 2.6.6
Using thread_safe 0.3.6
Using coffee-script-source 1.11.1
Using colorator 1.1.0
Using commonmarker 0.23.6
Using execjs 2.8.1
Using concurrent-ruby 1.1.10
Using eventmachine 1.2.7
Using http_parser.rb 0.8.0
Using bundler 2.4.2
Using ruby2_keywords 0.0.5
Using ffi 1.15.5
Using faraday-net_http 3.0.2
Using unf_ext 0.0.8.2
Using rexml 3.2.5
Using gemoji 3.0.1
Using rb-fsevent 0.11.2
Using rouge 3.26.0
Using liquid 4.0.3
Using racc 1.6.2
Using forwardable-extended 2.6.0
Using jekyll-paginate 1.1.0
Using rubyzip 2.3.2
Using jekyll-swiss 1.0.0
Using safe_yaml 1.0.5
Using webrick 1.7.0
Using mercenary 0.3.6
Using unicode-display_width 1.8.0
Using addressable 2.8.1
Using coffee-script 2.4.1
Using i18n 0.9.5
Using em-websocket 0.5.3
Using ethon 0.16.0
Using jekyll-commonmark 1.4.0
Using tzinfo 1.2.10
Using kramdown 2.3.2
Using unf 0.1.4
Using pathutil 0.16.2
Using faraday 2.7.2
Using rb-inotify 0.10.1
Using typhoeus 1.4.0
Using activesupport 6.0.6
Using kramdown-parser-gfm 1.1.0
Using nokogiri 1.13.10 (x86_64-linux)
Using jekyll-coffeescript 1.1.1
Using sass-listen 4.0.0
Using sawyer 0.9.2
Using terminal-table 1.8.0
Using sass 3.7.4
Using octokit 4.25.1
Using html-pipeline 2.14.3
Using listen 3.7.1
Using simpleidn 0.2.1
Using jekyll-sass-converter 1.5.2
Using jekyll-watch 2.2.1
Using dnsruby 1.61.9
Using jekyll-gist 1.5.0
Using jekyll 3.9.2
Using github-pages-health-check 1.17.9
Using jekyll-avatar 0.7.0
Using jekyll-commonmark-ghpages 0.2.0
Using jekyll-github-metadata 2.13.0
Using jekyll-default-layout 0.1.4
Using jekyll-optional-front-matter 0.3.2
Using jekyll-feed 0.15.1
Using jekyll-include-cache 0.2.1
Using jekyll-mentions 1.6.0
Using jekyll-remote-theme 0.4.3
Using jekyll-readme-index 0.3.0
Using jekyll-sitemap 1.4.0
Using jekyll-relative-links 0.6.1
Using jekyll-redirect-from 0.16.0
Using jekyll-titles-from-headings 0.5.3
Using jemoji 0.12.0
Using jekyll-seo-tag 2.8.0
Using jekyll-theme-cayman 0.2.0
Using jekyll-theme-dinky 0.2.0
Using jekyll-theme-hacker 0.2.0
Using jekyll-theme-leap-day 0.2.0
Using jekyll-theme-merlot 0.2.0
Using jekyll-theme-midnight 0.2.0
Using jekyll-theme-architect 0.2.0
Using jekyll-theme-slate 0.2.0
Using jekyll-theme-minimal 0.2.0
Using jekyll-theme-modernist 0.2.0
Using jekyll-theme-primer 0.6.0
Using jekyll-theme-tactile 0.2.0
Using jekyll-theme-time-machine 0.2.0
Using minima 2.5.1
Using github-pages 227
{% endhighlight %}

**Confirm Rubygem package: WEBRICK is installed:**

Confirm using the `bundle list` command.

{% highlight ruby %}
$ bundle list | grep webrick
* webrick (1.7.0)
{% endhighlight %}

**Test your GitHub Pages site locally:**

Test your site using the `bundle exec jekyll serve` command.

{% highlight ruby %}
$ bundle exec jekyll serve
Configuration file: /home/youtheuser/Projects/youtheuser.github.io/_config.yml
To use retry middleware with Faraday v2.0+, install `faraday-retry` gem
            Source: /home/youtheuser/Projects/youtheuser.github.io
       Destination: /home/youtheuser/Projects/youtheuser.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
       Jekyll Feed: Generating feed for posts
                    done in 0.214 seconds.
 Auto-regeneration: enabled for '/home/youtheuser/Projects/youtheuser.github.io'
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
{% endhighlight %}

**View the locally created Github Pages site:**

Using the Google Chrome web browser.

{% highlight ruby %}
$ google-chrome-stable http://127.0.0.1:4000/
{% endhighlight %}

When the site loads, you will notice that all it displays is `Hello World` which is the content from the original `index.html` file.
Delete both the `index.html` and `README.md` files and the new GitHub pages site will be automatically served at [http://127.0.0.1:4000/]

### Remote Deployment

**Deploy the LOCAL Jekyll site to the REMOTE repository:**

Check the LOCAL repository status, using the `git status` command.

{% highlight ruby %}
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
      deleted:    README.md
      deleted:    index.html

Untracked files:
  (use "git add <file>..." to include in what will be committed)
      .gitignore
      404.html
      Gemfile
      Gemfile.lock
      _config.yml
      _posts/
      about.markdown
      index.markdown

no changes added to commit (use "git add" and/or "git commit -a")
{% endhighlight %}

**Add the new site:**

Add the LOCAL repository, using the `git add` command.

{% highlight ruby %}
$ git add --all
{% endhighlight %}

**Check the LOCAL repository status:**

Check the LOCAL repository status, using the `git status` command.

{% highlight ruby %}
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
      new file:   .gitignore
      new file:   404.html
      new file:   Gemfile
      new file:   Gemfile.lock
      deleted:    README.md
      new file:   _config.yml
      new file:   _posts/2023-01-03-welcome-to-jekyll.markdown
      new file:   about.markdown
      deleted:    index.html
      new file:   index.markdown
{% endhighlight %}

**Commit the new site:**

Commit these new changes, using the `git commit` command.

{% highlight ruby %}
$ git commit -m "Initial Jekyll site commit from LOCAL repository"
[main 02348ec] Initial Jekyll site commit from LOCAL repository
 10 files changed, 444 insertions(+), 3 deletions(-)
 create mode 100644 .gitignore
 create mode 100644 404.html
 create mode 100644 Gemfile
 create mode 100644 Gemfile.lock
 delete mode 100644 README.md
 create mode 100644 _config.yml
 create mode 100644 _posts/2023-01-03-welcome-to-jekyll.markdown
 create mode 100644 about.markdown
 delete mode 100644 index.html
 create mode 100644 index.markdown
{% endhighlight %}

**Push the LOCAL site to the REMOTE repository:**

Push these new changes, using the `git push` command.

{% highlight ruby %}
$ git push -u origin main
Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 4 threads
Compressing objects: 100% (11/11), done.
Writing objects: 100% (11/11), 5.64 KiB | 825.00 KiB/s, done.
Total 11 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:youtheuser/youtheuser.github.io.git
   07ae88f..02348ec  main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
{% endhighlight %}

### Conclusion

**If you have followed this tutorial carefully, you will have a new GitHub Pages site, hosted on your GitHub REMOTE repository.
View the modified REMOTE Github Pages site:**

Using the Google Chrome web browser.

{% highlight ruby %}
$ google-chrome-stable https://youtheuser.github.io/
{% endhighlight %}

From here, you can add new posts, further customise the look of the GitHub Pages site, add in further functionality.

For further information, please visit these four sites:

  - [Jekyll]
  - [Getting started] with GitHub Pages
  - [Customize your Jekyll Website]
  - [Building a static website with Jekyll and GitHub Pages]

### References

This article used the following references:

  - [Jekyll]
  - [GitHub Pages] static site configuration
  - [Cleartext]
  - [Markdown] HTML markup library
  - [Kramdown] HTML markup library
  - [sudo]
  - [Getting started] with GitHub Pages
  - [SSH Keys]
  - [Gnome Terminal]
  - [Xterm] the standard terminal emulator for the X Window system
  - [https://youtheuser.github.io/]
  - [http://127.0.0.1:4000/] is the LOCAL GitHub Pages site.
  - [Customize your Jekyll Website]
  - [Building a static website with Jekyll and GitHub Pages]

[Jekyll]: https://jekyllrb.com/
[GitHub Pages]: https://docs.github.com/en/pages
[Cleartext]: https://simple.wikipedia.org/wiki/Cleartext
[Markdown]: https://daringfireball.net/projects/markdown/
[kramdown]: https://kramdown.gettalong.org/index.html
[sudo]: https://en.wikipedia.org/wiki/Sudo
[Getting started]: https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site
[SSH Keys]: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
[Gnome Terminal]: https://en.wikipedia.org/wiki/GNOME_Terminal
[Xterm]: https://en.wikipedia.org/wiki/Xterm
[https://youtheuser.github.io/]: https://youtheuser.github.io/
[http://127.0.0.1:4000/]: http://127.0.0.1:4000/
[Customize your Jekyll Website]: https://simondosda.github.io/posts/2021-09-16-blog-github-pages-4-custom.html
[Building a static website with Jekyll and GitHub Pages]: https://programminghistorian.org/en/lessons/building-static-sites-with-jekyll-github-pages
