# Project Preinfusion Overview

Understanding a topic means digesting a ton of different, often conflicting subject material. 
Later, we might want to re-locate sources of information we consumed but find it difficult.

## Rediscovery

Browser histories and bookmarks aren't working. The state of the art is re-Googling your past queries 
and hoping to find the same results again.

What can be done differently to capture and preserve knowledge in-context later?

### How can we explore this?

Automatically collect any content you view longer than a certain amount of time.
Implement a local search index (integrate it into your google search results?) for that content.
Consider new visualizations of browser search history.
Include better referral data in history -- who shared with you? what search term got you there?

## Conceptual Integration (Concept-completion?)

People are good pattern-matchers. We see patterns in everything. That said, we have anecdotal evidence that an effective connection-detector can be a super-power for a researcher building context. DevonTHINK provides perhaps the best example of this, by automatically scoring documents for similarity and by allowing fast queries of documents by simply highlighting an interesting word or other search term.

### How can we explore this?

We cannot integrate information we have not got access to. One approach would be to pull all the information into another system -- DevonTHINK does this in a very desktop-app way. Another approach
would be to create ingestion engines.

If we apply "tool thinking" here, we consider how to build this in a way that, like the LSP protocol, 
we can take advantage of this kind of query across many systems: the browser, the user's text editor, Slack.

We'll also need to explore how to compare many documents efficiently. The open source text2vec project seems promising. PostgreSQL has a good text vector approach integrated, and there are open source cloud-style search engines as well. It would be nice to pick something easily embeddable rather than a project with heavy-weight operational overhead like Postgres or Lucene. This may also be a chance to play with [Bloom/Cuckoo filters](https://brilliant.org/wiki/cuckoo-filter/)! See also [text similarity](http://text2vec.org/similarity.html#:~:text=).
 
## Sharing & Recommendation

Often, researcher and creators will collaborate in small groups and pool their knowledge discoveries in small circles of shared interests. Ink & Switch is one example, with a Slack channel which sees a steady flow of interesting articles & brief discussions around them. Cade at the New Design Congress expressed frustration with his existing desktop tools being unable to easily share ingested content. It is very common in the Ink & Switch channel to post a link, then follow up with a brief excerpt and/or a comment explaining why the link was interesting or relevant. Then a discussion will ensue, often as a thread below the link.

Not all discussions will occur in a structured way, so collecting context and associating discussion that is adjacent both in content and in space/time is important. 

### How can we explore this?

Xcr.pt is a first approach here. It at least improves the user experience of grabbing and sharing a link, but it doesn't collect any feedback / context back into the system. It does have several benefits though, like making it easier to durably share content as-it-is-seen with some highlighting of why it's being shared for that group.

## Active Reading

TBD
