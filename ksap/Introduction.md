# Introducing KSAP

Knowledge Service Association Protocol (KSAP) is component of a larger _(yet to be defined)_ Knowledge Service Protocol (KSP). The goal is to enable knowledge tools (that people use) to associate knowledge across own boundaries.

### Problem statement

Today information is scattered across various app / service silos. People often use various tools for note taking (e.g.: notion, evernote, roam research, google docs, hand crafted tools). Collect some reference materials (PDFs, Screenshots, Excerpts). Have discussions with peers on various platforms (Slack, Twitter, Github Issues, Email, …).

However connecting data points across tools, services and source is often lost. Linking across relevant resources is a way to create associations across them. However that does not always works e.g. I can not just go and amend arbitrary website to add links to all the associated information. Amount of manual work to keep things liked grows with each new association (as all the existing resources need to reflect it).

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

#### Web Extension Interface

Web extension that surfaces associations with a currently active document URL.





[LSP]:https://microsoft.github.io/language-server-protocol/
[Web Annotation Model]:https://www.w3.org/TR/annotation-model/