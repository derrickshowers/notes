# How Your Brain is Conspiring Against You Making Good Software
_[Jenna Zeigen](http://twitter.com/zeigenvector)_

* People will endorse a bad argument if they believe it to be true
* Why is debugging hard? We favor information in a way that proves pre-existing theories
* Breaks are more important than you think!
* We tend to prefer our own code over someone else's, we choose code assemble by ourselves over code assembled by others
* We're bad at making predictions about how long it will take to do something (sprint planning)
* We tend to overestimate our own skills and abilities
* We prefer the status quo when assembling a team
* We rely on examples that come to mind when evaluating someting (stereotypical programmer is only a stereotype because its what people think of first)

### How do we fix this?
Thinking slow (thinking fast is good for certain situations, but not when programming, picking a team, etc.)

<sup>[Slides](http://jenna.is/at-forwardjs.pdf) | [Video](https://youtu.be/Kf2u8BLMyU4?t=34m20s)</sup>

# Bringing Dynamic Back
_[Raymond Camden](https://twitter.com/raymondcamden)_

* Why a static site generator?
  - Ability to work with data without a database
  - Application server gives much more power than you might need
  - Less things break
* Options: Jekyll, Hugo, Harp
  - Jekyll focused on blogs
* Might miss forms, comments, search, calendar, data

### Forms
* WuFoo - great site, but only allows 100 per month on free tier
* Google Doc - no limit, free, but tricky to navigate ([this](https://github.com/kctess5/jqGoogleForms) might be a helpful option)
* [Formspree](https://formspree.io)
* [FormKeep](https://formkeep.com)

### Comments
* Disqus - fancy dashboard with lots of analytics
* Livefyre
* Facebook comments
* Do you need comments? Daring Fireball famous for not having comments

### Search
* [Google custom search engine](https://cse.google.com/cse/all)
* [Tapir](https://tapirgo.com) - Super easy, but project might be dead (Github repo not touched in 5 years)

### Calendars
* Google Calendar
* [FullCalendar](http://fullcalendar.io)
* Eventbrite

### Working with clients
* [Forestry](https://forestry.io/) - CMS for Jekyll and Hugo, great option for working with clients who want to manage their own content
* Raymond's blog has some other ideas

# React Native: Learn from my mistakes
_Joe Fender_

* Why reactive native?
  - React is fun
  - It really is native
  - Not necessarily a way to build one app for iOS and Android, but a way for engineers to have the same skill sets.

### "What I learned"
* Know flexbox - used heavily for layout (cool!)
* Know how devices work, what APIs are available, etc.
* Use react-native-cli to easily spin up a new app - creates iOS and Android directories which can be opened up in Xcode/Android Studio

<sup>[Dummy app](https://github.com/derrickshowers/react-native-test-app)</sup>

# Inclusive Code
_[Estelle Weyl](https://twitter.com/estellevw)_

* The first rule of ARIA is don't use ARIA (use semantic elements when available)
* Lots of examples on how to write more performant code, which also happens to be accessible

<sup>[Slides](http://instartlogic.github.io/p/velocity/) | [Video](https://youtu.be/Kf2u8BLMyU4?t=5h54m11s)</sup>

# Advanced Debugging with Google Chrome
_[Rocco Balsamo](https://twitter.com/TheRoccoB)_

### Snippets
![screenshot](/resources/images/conferences-forward-001.png)

* Sources window -> top left panel, to the right of 'sources' and 'content scripts'. (How did I not know about this?)
* Run blocks of code in Chrome (much easier than writing code in the console)
* Save snippets to run later
* Use with stuff like `console.profile` to add listeners to key events. Example: add a keypress event to the shift key to start/stop profiling. Much easier for small chunks of time debugging hard to capture interactions.

### Other cool stuff
* Style console text with CSS! `console.log("%cStop!", "color: red; font-size: 4.5em;)`
* Use `console.table` to output object properties in table format `console.table({ foo: 'foo', bar: 'bar' })`
* Cmd+Shift+P: Search all tasks
* Cmd+Alt+F: Search all resources at once
* Use conditional breakpoints to insert a `console.log` in your code (neat idea!)
* XHR breakpoints in sources panel

<sup>[Slides](http://www.roccobalsamo.com/debug/advDebug.pdf) | [Notes](http://www.roccobalsamo.com/debug/)</sup>
