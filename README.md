# Reckless

Reckless is a proposed personal knowledge manager for research and writing. It
organizes notes, bookmarks, events, email notes, and connections in a local GNU
Recutils collection.

## Version 1 harness

The first harness feature supports natural-language reads and inserts. It uses
a local model to select record types and fields, choose operations, and extract
filter or record values. The model receives the available schema, not saved
record contents, and returns ordered JSON operations.

The Python harness discovers record types and allowed fields from Recutils
descriptors, validates the model response, and uses reviewed, operation-specific
Jinja templates to construct Recutils arguments. Reads query the collection.
Inserts are checked on temporary file copies before the originals are replaced.
Prompts in a batch run independently and in order; one operation does not pass
its results to the next.

Version 1 does not support updates, deletes, clarification questions, or
dependent operations. Multi-file inserts are committed one file at a time, so
a failure during replacement can leave some files committed.

## Project status

The harness feature is specified but not implemented. Local OpenTelemetry traces
are planned as best-effort review artifacts. Model evaluation and fine-tuning,
a systematic evaluation suite, and systematic trace analysis remain future
work.