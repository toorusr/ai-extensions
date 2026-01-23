# semantic-search extension

## Tools

- local_semantic_search(query, path?, mode?, logSubagent?)
  - Embedding search preview plus a search subagent that can refine results.
- local_embedding_search(query, path?, mode?)
  - Embedding search only (one result per file).
- local_rg(pattern, path?, maxMatches?, contextLines?)
  - Read-only ripgrep-style search.

## Notes

- mode is accepted but currently ignored; "code" includes markdown. TODO: split docs/code handling.
- path follows ripgrep-style usage (file or directory). If the path does not exist, the tool falls back to simple glob or substring matching.
- Indexing is per-cwd. If no index exists, a full index is created and path only filters results.
- logSubagent writes the JSON event stream to ~/.pi/agent/cache/semantic-search/subagent-logs and returns the log path.
- Legacy tools (semantic_index, semantic_search, /semantic) are disabled by default. Set PI_SEMANTIC_LEGACY=1 to re-enable.
