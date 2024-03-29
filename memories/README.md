# Memories
**Memories are individual chatGPT sessions, formalized.**

This means a single chatGPT session with all of its content AND metadata is represented as a persistent entity (in this case, a yaml file in GitHub).

## Format
See [format.yml](/format.yml) for the latest information. The fundamental elements are:

```yaml
memory:
  conversation:
  tokens:
  prev:
  next:
  meta:
```

- `conversation`: *A list of all the prompts and responses in a session*

  **Example:** `conversation: [ ["prompt", "response"], ["prompt 2", "response 2"], ["prompt 3", "response 3"] ]`

- `tokens`: *The number of tokens used in a session*

  **Example:** `tokens: 36`

- `prev` and `next`: *Pointers to the previously linked session (if any) and the next linked session (if any); this facilitates a Linked List implementation*

  **Example:** `prev: 1`, `next: 3`

- `meta`: *Data and metadata taken directly from the internally stored values of the chatGPT session*

  **Example:** `meta: {tokens_used: 36, some_variable: "some value", some_list: ['steve', 'brian', 'mark']}`
