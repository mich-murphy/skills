---
name: no-comments
description: "Review comments for code smells and relevance, remove anything not clearly justified."
disable-model-invocation: true
---

# No comments

Review all comments within the codebase, only these exceptions are clearly allowed.

- Legal or license headers.
- Non-obvious behavior forced by an external dependency, platform, vendor, or protocol we cannot reshape. Surprises in our own code require removal. Mark them for rename, extract, type, or rearchitecture that makes the behavior obvious without prose.
- Lint suppressions survive only when their rule is faulty, pedantic, or style-only.
- Doc comments that define a public API contract.
- Issue or RFC links that explain a constraint code cannot express.

eslint-disable, @ts-ignore, @ts-expect-error, and similar suppressions are code smell. Look up the rule. If it catches real bugs or protects correctness or safety, kill the suppression and mark the exact guilty symbol for removal.

IMPORTANT, do not remove, too risky, fine for now, and long justifications are smells. Before judging, read nearby code. If its claim is not obvious there, search more broadly for a proven exception to justify its existence. If not found, the comment should be removed.

A long justification without a proven exception is a smell. Remove it. Do not touch the code, report removal findings only

Touch comments and identify refactor targets. Never write application code.

Report only. Name touched files, deletion count, and skips.
