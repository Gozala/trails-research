# KSP

The Knowledge Server Protocol is inspired by the Language Server Protocol and is an out-of-process approach to indexing and searching information a user is exposed to.

The KSP is a process that runs against a directory in a known, local directory, and storage is implemented in a thread-safe fashion to allow multiple uncoordinating clients to access the same repository.

## Browser Plugin

The KSP browser plugin automatically submits the location and text of all content a user visits while it is active. The KSP index replies with a list of likely-related content in the index. KSP is visible as a sidebar that can be toggled off and on.

A browser action to query for a selected phrase in the index is also supported. 

### Auto-linking

A possible enhancement to this approach would be for the KSP to return unusual or "interesting" candidate phrases from the input document to convert to links via 


## Editor Plugin

The KSP editor plugin performs the same task as the browser plugin, sending and receiving queries for local files. As with LSP, open/in-memory files are treated a little differently from on-disk files as the current editor panel becomes the source of truth at any time.

### Topic Completion

In an ide-like environment where auto-documentation or tab completion can appear, we can also provide references to other related documents on-demand as a term is entered. For example, if one types "Daniel<tab>", we could show all the Daniels in your corpus with the documents they're associated with.

## Technical Considerations

### Sync

Users have multiple computers, and so we need to synchronize this data between their machines. We could use a dropbox/shared folder approach (easy to sync!) or, data-format depending, something like automerge for the indices. 

### Collaboration

We may want to be able to publish subsets of the index (everything associated with a topic, perhaps?) to our peers, so considering how to decompose these documents would be helpful.

