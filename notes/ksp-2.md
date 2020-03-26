# The Knowledge Server

We want to discover & surface connections between ideas, documents and concepts. This ability is something other tools have specialized in but each within their own silos.  By creating an index of that knowledge for a user, we can give them the superpower to discover connections among their own work where ever they go.

## Representative User Experience

I've already set up KSP to ingest my notes directory and installed the browser plugin.

Someone shares a link to a tool they've started using, Typora. I click that link and a little overlay in the bottom of the page appears showing me that the term "Typora" also appears in the notes `irakli-user-survey.md` and `martin-tools.md`. Clicking one of those notes opens the note in a text editor scrolled to the place that term appears.

Later, I'm using VSCode to transcribe some notes about Zettelkasten. A panel in my VSCode sidebar shows other notes with similar terms, like "memex", or "Gordon Brander". The term "memex" is interesting enough (not a stop word, appears in multiple documents) that it is highlighted blue in the text editor. Placing my cursor there and pressing "find all references" unfolds a window below that term showing me not just the other notes where it appears `gordon-workshop.md` but also a Zettelkasten introduction blog I read at [lesswrong.com](https://lesswrong.com) and the "about" page for Roam Research.

## Technical Components

* a VSCode plugin that can submit text, query & surface results
* a browser plugin that renders similar data and submits the text of webpages
* a daemon that holds all the data and responds to queries

