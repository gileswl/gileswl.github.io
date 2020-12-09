---
title: Adventures in getting started
layout: post
author: giles
---
So I thought, well, let's give using github pages for hosting a blog a try. This turned out to be somewhat more involved than you might hope.

I'm trying to use a windows desktop PC for this. It has Visual Studio Code and Python 3 installed, but is otherwise straight out of the box as far as a development environment goes.

The github pages site tells you how to set up using "a terminal" or the GitHub Desktop application. My first hope was that VSCode might include git, so I could just open a powershell terminal (within VSCode) and run git from there. I mean, microsoft own GitHub now, right? Anyway, nope. I installed the MS-maintained github extension for VSCode, but apparently that doesn't give you a git install *either*. I guess I'd been spoiled by linux package managers. 

So then I downloaded GitHub Desktop. That doesn't help, it's purely self-contained. Nothing was complaining that I didn't have git - unless I tried to run it directly from a powershell terminal, it just wasn't working. At this point I downloaded Git directly and set it up. This somewhat worked but issuing the commands given on the GitHub Pages site still returned an error when trying to push my changes (i.e. upload a bare index.hmtl that just said Hello World!). However trying to commit and push using the GUI extension did work. Okay, so now there's a site at gileswl.github.io. So that's progress.

On to Jekyll. "Get up and running *in seconds* promises the Jekyll website. Well, not really. Because you need Ruby. So off I went to get Ruby. The Ruby installer worked but then it tried to fetch the MSYS2 toolchain and install that, which failed to fetch some component or other and couldn't install pacman. I gave up on that and went and got a version of the installer that supposedly included the devkit bits. This apparently still fetches what it needs remotely. This appeared to work but the installer doesn't do anything sensible like report success and exit gracefully, it just reiterates the install prompt. ANYWAY.

I opened a powershell window to confirm that I could run gem. Yep. It doesn't work from the powershell terminal within VSCode though, even after opening a new terminal instance. I had to restart VSCode. "gem install bundler jekyll" - something finally did what I expected first time. Once Jekyll was up and running things got a lot more straightforward - the [jekyll tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/) is very good.