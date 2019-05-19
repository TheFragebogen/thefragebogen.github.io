---
layout: default
title: Getting started
---

Getting started
===

[The concept](#the-concept)
---

### [Structure](#structure)
TheFragebogen follows the _paper metaphor_, i.e., a paper-based questionnaire is actually a sequence of paper sheets, which each consists of one or more items.
An item consists, in fact, of a question and a scale.
Sheets are represented in TheFragebogen by so-called `Screens` and items by so-called `QuestionnaireItems`.
In TheFragebogen, a questionnaires consists of one or more `Screens` while only one `Screen` is shown at a time.
A `Screen` encapsulates a specific functionality, such as presenting of items, waiting for some time, or exporting the stored data.
For presenting `QuestionnaireItems` or HTML content (`UIElementHTML`), TheFragebogen provides `ScreenUIElements`.

The lifecycle of a questionnaire is handled by the `ScreenController`, which organizes the presentation of all `Screens` and also data export.

TheFragebogen is completely implemented using [object-oriented programming (OOP)](https://en.wikipedia.org/wiki/Object-oriented_programming).

### [Technical details](#technical-details)
TheFragebogen enables to implement questionnaires as [_single-page applications_](https://en.wikipedia.org/wiki/Single-page_application).
This is a specific implementation approach of a web page that modifies it's content using JavaScript.
This allows to implement a questionnaire without requiring a web server or any other network infrastructure, as all necessary data can be included in this application.
Nevertheless, all functionality that can be used to implement web pages can be used.
For more information on available functionalities see [Mozilla's Developer Network](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5).

[Code](#code)
---
This is a minimal implementation.

```javascript
//This array stores all screens that will be shown.
var screens = [];

//First we create an HTML UI-Element with "Hello World"
var htmlWelcome = new UIElementHTML(undefined, "Welcome to the TheFragebogen!<br/>Please press 'Next'.");

//now we add a radio box with just one option 'yes'
var readyRadioBox = new QuestionnaireItemDefinedOne(undefined, "Are you ready?", true, ["Yes"]);

//to display the welcome message and the radio box
//we add both to a screen UI-Element
var screen1 = new ScreenUIElements(htmlWelcome, readyRadioBox);
//and add that screen to our screens list
screens.push(screen1);

//finally we create a ScreenController and add the screens list
var screenController = new ScreenController(screens);

function start() {
    document.body.innerHTML += "Everything loaded.";
    screenController.init(document.body);
    screenController.start();
}
```

[The data export](#the-data-export)
---

During execution a questionnaire by a web browser the collected data is stored only _within_ the web browser.  
__IMPORTANT__: The collected data is _not_ stored by default (i.e., closing the tab/window clears the data.)

For data export, the following options are available:

* _Download_ the data to local device from the web browser: `ScreenWaitDataDownload`.
* _Upload_ the data to a web server: `ScreenWaitDataUpload`.
* _Show_ the data to the user: `ScreenDataPreview`.

The data is exported as a file ([comma seperated value (CSV)](http://en.wikipedia.org/wiki/CSV)).

The data consists of _five_ columns.

For each row (usually a row represents _one_ `QuestionnaireItem`):

* Column _1_ contains the index of the `Screen`.
* Column _2_ contains the type of this data item (i.e., the [class](https://en.wikipedia.org/wiki/Class_(computer_programming)) of the object this data item was collected by).
* Column _3_ contains the question (might be empty or a generic identifier).
* Column _4_ contains the potential answers (might be `undefined`).
* Column _5_ contains the answer(s) (might contain an array; depends on the answers to be exported).

__NOTE:__ TheFragebogen also supports tracking changes of the answer of `QuestionnaireItems`.
In this case, _column 5_ contains an `array<array<timestamp, answer>>`.

[Next steps](#next-steps)
---
1. Take a look...
    1. ... at the [demos](/demo).
    2. ... at [TheFragebogen's README](https://github.com/thefragebogen/thefragebogen/README).
    3. ... at the JSDoc documenation.
2. Setup your development tools
    1. Choose your [HTML editor](https://en.wikipedia.org/wiki/Comparison_of_HTML_editors).
    2. Get familiar with web browser development tools (i.e., [Firefox Developer Console](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_are_browser_developer_tools) or [Chrome Devtools](https://developers.google.com/web/tools/chrome-devtools/)).
3. Start by modifying the [developer template](https://github.com/TheFragebogen/TheFragebogen/blob/master/examples/developer_template.html).
4. When done your implementation test it on different web browsers.
5. Think about using version-control software (e.g., [GIT](https://git-scm.com/)).
