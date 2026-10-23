# Reckless

Reckless is a proposed personal knowledge manager for research and writing. People can ask it to save notes, bookmarks, events, email notes, and connections between records.

## How it should work

The user sends a request to the harness. The harness sends the request to a local language model. The model returns the record type and fields to save.

The harness checks the model's response. It then uses Bash and GNU Recutils to save the record. The model cannot edit collection files or create shell commands. The harness rejects unclear or invalid requests without writing anything.