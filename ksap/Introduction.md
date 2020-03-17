# Introducing KSAP

Knowledge Service Association Protocol (KSAP) is component of a larger _(yet to be defined)_ Knowledge Service Protocol (KSP). The goal is to enable knowledge tools (that people use) to associate knowledge across own boundaries.

### Problem statement

Today information is scattered across various app / service silos. People often use various tools for note taking (e.g.: notion, evernote, roam research, google docs, hand crafted tools). Collect some reference materials (PDFs, Screenshots, Excerpts). Have discussions with peers on various platforms (Slack, Twitter, Github Issues, Email, …).

However connecting data points across tools, services and source is often lost. Linking across relevant resources is a way to create associations across them. However that does not always works e.g. I can not just go and amend arbitrary website to add links to all the associated information. Amount of manual work to keep things linked grows with every new association introduced (as all the existing resources need to reflect it).

### User Story

While researching a specific subject I often use combination of tools in the process:

- A web browser to query web to find information available.
- Write personal notes (usually in markdown) to bring findings into my context. This ofter involves quoting fragments of web content.
- Share / discuss findings with peers on different messaging channels (depends on peer preference, usually keybase, slack, github, messages, email). Any insights / feedback needs to be captured manually by integrating those into notes through either
  -  linking (when supported)
  - quote pasting
  - elaboration

There are several limitation to this workflow:

1. Difficulty of connecting notes to the feedback from others (By incorporating feedback without capturing reference, ability to examining basis for conclusions is lost).
   - Sharing with group often means duplicating notes (e.g. gist, pasting content) which no longer connected to its origin.
   - Feedback needs to be incorporated into notes. This is lossy process and without backlinks connection with a feedback is lost.
   - With multiple discussion channels (disconnected from notes) significant effort is spend in keeping peers and notes synchronized.
2. Process involves documenting references in notes to keep the connection between sources. Connection between notes that share common reference is not visible and may not be discovered.
3. Cognitive load of switching between sources is too high. Often references index isn't enough and mechanics of quote pasting is incorporated to reduce a load.
4. You can only navigate information graph from notes.

### How does KSAP help ?

- My note taking app can call KSAP API  to associate note to the referenced web resource, creating association between two. Publishing draft note also gets associated with a note. Discussion channel can associate discussion thread with published notes indirectly creating association with original note and it's references.
- Keeping index of all the discussions is no longer needed as KSAP maintains the graph from which that can be projected.
- Other tools (e.g. Browser Extension) can query KSAP to surface connections in context. Making it possible to see it from places other than notes.
- Other tools (e.g. Browser Extension) can reduce context switching by brining excerpts of references into place (maybe something like https://notes.andymatuschak.org).

### Existing solutions

Some tools seem to attempt to address cross linking problem by scoping it a specific use case (e.g blogging) or keeping feedback loops out of the scope.

- Gordon's [patterns][]
- [Roam research][]

- [Notational Velocity][]

Others seem to take on the problems by moving all of the work to the confinements of their system.

- [Notion][]

- [Dropbox Paper][]

- [Google Suite][]

  

### Proposition

Define a standard protocol that enables arbitrary tools to associate resources across their own boundaries (e.g note taking tool can submit associations to every link, tag in it). And allow querying for associations so that users don't have to reflect new association across different data sources, they could be just surfaced by querying KSAP.

### Deliverables

#### Knowledge Association Service

Implement a daemon service (nodejs server) that exposes JSON-RPC based API (inspired by [LSP][]) for

1.  Submitting associations with an arbitrary targets and bodies ([Web Annotation Model][] offers a good starting point that can be extended beyond web using `file://` and app specific URLs).
2. Querying associations to discover connections across participating tools.

_Note: https://graphql.org/ seems very relevant, and probably there are plenty of building blocks available for us already._

#### CLI Interface

CLI interface for adding / querying associations.

#### Browser Extension Interface

Web extension that surfaces associations with a currently active document URL.





[LSP]:https://microsoft.github.io/language-server-protocol/
[Web Annotation Model]:https://www.w3.org/TR/annotation-model/
[patterns]:http://gordonbrander.com/pattern/
[Roam research]:https://roamresearch.com/
[Notational Velocity]:http://notational.net/
[Notion]:https://notion.so/
[Dropbox Paper]:https://paper.dropbox.com
[Google Suite]:https://drive.google.com/

