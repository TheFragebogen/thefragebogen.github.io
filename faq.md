---
layout: default
title: FAQ
---

FAQ
===

What can I do with TheFragebogen?
---
TheFragebogen was developed to easily implement scientific questionnaires using HTML5 and JavaScript.
An overview on available functionality and use cases is given in the paper [TheFragebogen: A Web Browser-based Questionnaire Framework for Scientific Research](static/paper/2019-guse-et-al-qomex.pdf).
Also take a look at the provided [examples/demos](/demo).

In difference to cloud-based system, TheFragebogen allows to implement questionnaires that can be used without requiring any infrastructure (e.g., network access, servers etc.).
Also it is not necessary to share the collected data with any third-party server.

What does TheFragebogen require?
---
At least a [HTML5](https://en.wikipedia.org/wiki/HTML5)-capable web browser (almost any modern web browser).
Preferable one supporting the JavaScript standard [ES6](https://caniuse.com/#feat=es6) or later.

TheFragebogen also runs in web browsers on mobile devices.
For laboratory experiments on Android, there exists an app ([code](https://github.com/TheFragebogen/TheFragebogen-android)) that disables screen rotation and adaptive brightness.
This app implemented and used for experiments on [Quality of Experience](https://en.wikipedia.org/wiki/Quality_of_experience).

How do I implement a questionnaire?
---
You can start by reading the [getting started](/gettingstarted) section.

My questionnaire does not start. What can I do?
---
Please check that:
* required JavaScript files are loaded properly (mainly `thefragebogen.js`) and
* check that your code is actually valid.

If your web browser only supports ES5, please use `thefragebogen.es5.js`.

How can I debug a questionnaire implemented using TheFragebogen?
---
You can either use your favorite web browser development tools (e.g., [Firefox](https://developer.mozilla.org/en-US/docs/Tools), [Chrome/Chromium](https://developer.chrome.com/devtools), or [Opera](http://www.opera.com/dragonfly/) etc.).
In the standard configuration, TheFragebogen uses `console.{log, info, error}` (see [MDN](https://developer.mozilla.org/de/docs/Web/API/Console/log)).

How can I ask a question?
---
Please create an issue on the [issue tracker](https://github.com/TheFragebogen/TheFragebogen/issues) and tag it with _question_.

How can I report a bug?
---
For bugs, please create an issue on the [issue tracker](https://github.com/TheFragebogen/thefragebogen/).  
This should include at least:

* a _complete, precise, and understandable_ description of the bug, and
* example code and necessary information (e.g., web browser, version of TheFragebogen) to reproduce your issue.

Before report a bug, please verify that the issue is and _NOT_ with:
* the web browser your web browser (verify with other web browsers),
* the HTML5/Javascript/CSS-specs,
* your network connection, or
* your media is playable by your web browser.

How can I submit a patch?
---
Please create a pull request.  
Please create _one_ pull request for each related change.  
If you want to submit multiple changes (not related with each), please open multiple change requests.

Release cycle?
---
Up until now there is no planned release cycle.
If new features are added a new release is created.

The goal is to keep the API as stable as possible.

What can I do to support TheFragebogen?
---
* Use it and develop new use cases.
* Report and fix bugs / design issue.
* Implement new features. You can take a look at the missing features on the [issue tracker](https://github.com/TheFragebogen/TheFragebogen/issues).
* If possible please provide additional examples, describe your use cases, and lessons learned.

Use it.  
Be happy.  
Share your improvements.  
