---
layout: default
title: Getting started
---

Getting started
===

The concept
---

TheFragebogen follows the _paper metaphor_, i.e., a paper-based questionnaire is actually a sequence of paper sheets, which each consists of one or more items.
An item consists, in fact, of a question and a scale.
Sheets are represented in TheFragebogen by so-called `Screens` and items by so-called `QuestionnaireItems`.
In TheFragebogen, a questionnaires consists of one or more `Screens` while only one `Screen` is shown at a time.
A `Screen` encapsulates a specific functionality, such as presenting of items, waiting for some time, or exporting the stored data.
For presenting `QuestionnaireItems` or HTML content (`UIElementHTML`), TheFragebogen provides `ScreenUIElements`.

The lifecycle of a questionnaire is handled by the `ScreenController`, which organizes the presentation of all `Screens` and also data export.

TheFragebogen is completely implemented using [object-oriented programming (OOP)](https://en.wikipedia.org/wiki/Object-oriented_programming).

The data export
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
