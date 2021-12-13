---
layout: post
title:  "Codespaces on iPad"
date:   2021-12-12
author: curtis
description: "codespaces on ipad"
---

Technology marches on... My dream of full-time coding on an iPad continues to progress.

This entire post, some layout changes, and all images were captured and written on my iPad.

What technologies helped make this possible?

- GitHub Codespaces
- Jekyll
- DO Apps (Builds many applications, including Jekyll sites, upon a push to a repoß)

We are still a long way away from being able to do most coding tasks without a traditional computer. But we get closer and closer.

I'll have a tutorial series soon to help walk others through all the steps (I'm also writing a book about creating a developer portfolio website). But for now, I'll just highlight how I've made more changes than I expected I could directly on the iPad (including marked-up screenshots using only iOS tools).

## Codespaces

The main tool that makes this whole workflow possible is Codespaces. If you're curious about the files that drive Codespaces, you can view them in the [actual repo](https://github.com/curtisspendlove/knightoftheoldcode-com/tree/main/.devcontainer).

The `.devcontainer` directory contains the files which Github will detect and use to create or spin up a Codespace. This can be accessed via the browser (as I'm doing on the iPad) or locally (using VS Code and Docker Desktop).

Running a Codespace locally is much more flexible as you have the full power of your desktop or laptop; and it should run on a variety of Operating Systems.

However, you can do a surprising number of things directly in the browser. I continue to be impressed with the tech that Microsoft is releasing.

[![Github Codespaces - KotOC](/img/codespaces-on-ipad/github-codespaces-knightoftheoldcode-repo.png)](/img/codespaces-on-ipad/github-codespaces-knightoftheoldcode-repo.png)

The above shows the primary, default view that Codespaces opens in the browser. If you look closely, you'll see the iPad topbar and that Safari is in full-screen mode. I have the repo open in the first tab, Codespaces in the second, and a preview in the third.

Those who've used VS Code before might notice some similarities. ;)

(I'm a bit embarrassed that it's configured for `Spaces: 4`, but hopefully I'll remember to fix that in the future.)

As youy can see, Codespaces in the browser is fully functional and includes many creature comforts (including linting warnings and errors and a robust terminal).

### Launching Codespaces

If you have Codespaces active on your account, you'll see an option in the dropdown for the `<> Code` button in Github's UI for any Codespaces-enabled repo.

(If you don't have [Codespaces](https://github.com/features/codespaces) active, you'll need to sign up for the beta. Or have your Organization sign up, if applicable. There **will** be a cost to Codespaces at some point, so make sure you familiarize yourself with the [pricing](https://docs.github.com/en/billing/managing-billing-for-github-codespaces/about-billing-for-codespaces#codespaces-pricing).)

[![Github Codespaces - Launching in a Browser](/img/codespaces-on-ipad/codespaces-launching-in-browser.jpeg)](/img/codespaces-on-ipad/codespaces-launching-in-browser.jpeg)

[![Github Codespaces - Codespaces - List](/img/codespaces-on-ipad/codespaces-launching-list.jpeg)](/img/codespaces-on-ipad/codespaces-launching-list.jpeg)

(I like to right-click and Open in Background. BTW, it's best to have a mouse and keyboard.)

[![Github Codespaces - Open in Background](/img/codespaces-on-ipad/codespaces-launching-open-in-background.jpeg)](/img/codespaces-on-ipad/codespaces-launching-open-in-background.jpeg)

You'll see this screen quite a bit. (But it's good that it sleeps the VPS running your Codespace when it's inactive. Although this does **not** stop billing. You need to delete the Codespace when you're done with it.)

[![Github Codespaces - Connecting](/img/codespaces-on-ipad/codespaces-connecting.png)](/img/codespaces-on-ipad/codespaces-connecting.png)

### Exploring Codespaces (a Bit)

A Codespace is essentially a Virtual Private Server (VPS) in the cloud. It's preinstalled  (via a Dockerfile) with the software to run your project. But, it's also just a standard VPS and you have `root` elevation privelages (via `sudo`).

You can install and execute `tree`.

[![Github Codespaces - Install and Execute tree](/img/codespaces-on-ipad/codespaces-install-and-execute-tree.png)](/img/codespaces-on-ipad/codespaces-install-and-execute-tree.png)

### Launching Jekyll

It's easy to install and run your toolchain. Since my `Dockerfile` and `devcontainer.json` contain the commands to preinstall Ruby and Jekyll, it's a simple matter to start `jekyll` from the terminal (you can also run via Tasks and even autostart. I like to launch it manually. I actually want to trim the Dockerfile down a bit and add a `bin` directory with handy utility scripts like I do with my standard Ruby projects.)

[![Github Codespaces - Launch Jekyll](/img/codespaces-on-ipad/codespaces-launch-jekyll.png)](/img/codespaces-on-ipad/codespaces-launch-jekyll.png)

Note in the screenshot above Codespaces (via VS Code) provides helpful shortcuts for many things. Here, it's telling us we launched something that requests port permissions. It provides a GUI shortcut to open a second browser tab for previewing our Jekyll site.

### Ports and Previews

By default, all ports run in `private` mode. But you can set them to `public` if you wish to connect and preview.

[![Github Codespaces - Public Ports for Preview](/img/codespaces-on-ipad/codespaces-ports-public.png)](/img/codespaces-on-ipad/codespaces-ports-public.png)

At which case, you can preview your site by clicking the button in the ports list or right-clicking the URL.

[![Github Codespaces - Jekyll Preview](/img/codespaces-on-ipad/codespaces-preview.png)](/img/codespaces-on-ipad/codespaces-preview.png)

## Conclusion

You get the exact same preview and nearly the same development experience as you'd have locally; without having to install anything on your workstation.

Remember, in this case, my "workstation" was my iPad Air. And it has **plenty** of power for this. All of the linux-y goodness is offloaded to a VPS on Github's Cloud (probably somewhere in Azure).

And remember, if you don't like coding in the browser, you can open a codespace directly in the VS Code app. In fact, I do this routinely on my laptop and desktop. Across multiple operating systems: macOS, Windows, and various flavors of Linux. (I've even succeded on my Raspberry Pi 4 / 8GB running Manjaro XFCE).

Codespaces are amazing.

You even have full Git tooling for managing branches, committing code, and handling pull requests. I used them to post this article from the iPad and trigger the build and deploy workflow. But, as they say, that's a story for another time.

A future article series will explore creating a Jekyll portfolio site from scratch.
