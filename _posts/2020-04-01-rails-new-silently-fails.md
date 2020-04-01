---
title: "Why is Ruby on Rails silently failing to generate my new site?"
layout: post
---

So here's a little wrinkle I ran into on one occasion where I was setting up a Rails project in a new environment.

{% highlight shell %}
bjt@paravel:rails_projects$ rails new cool_app && cd cool_app
      create
      create  README.md
      create  Rakefile
      create  .ruby-version
      create  config.ru
      create  .gitignore
      create  Gemfile
         run  git init from "."
bjt@paravel:cool_app$ ls -l
total 4
-rw-rw-rw- 1 bjt bjt 2196 Apr  1 11:16 Gemfile
-rw-rw-rw- 1 bjt bjt  374 Apr  1 11:16 README.md
-rw-rw-rw- 1 bjt bjt  227 Apr  1 11:16 Rakefile
-rw-rw-rw- 1 bjt bjt  130 Apr  1 11:16 config.ru
{% endhighlight %}

As you can see, Rails never complained, yet almost everything is missing. Without an error message, this was a real head-scratcher for me at first, although the observant reader might notice the hint in the last thing Rails executs before bailing out to the shell.

Fortunately, the solution is simple. The only problem is that the system is either missing Git or doesn't have it in the user's `PATH`. Installing the `git` package with your Linux distribution's package manager normally does the trick.

{% highlight shell %}
$ sudo apt-get install git
{% endhighlight %}

Or if you have git in a custom location, just add it to your path.
{% highlight shell %}
$ export PATH="/custom/location/git:$PATH"
{% endhighlight %}

And in other good news, this was noticed by the devs and is [fixed in version 6](https://github.com/rails/rails/issues/38035).
