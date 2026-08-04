# Corpus-Correction Registry

This directory tracks potential errors discovered while JiMS processes the Distant Listening Corpus (DLC), a collection of digitally encoded scores and harmonic analyses. The purpose is practical: preserve every credible discrepancy, distinguish evidence from inference, and make confirmed corrections available in our forks.

## Working policy

- Record a case when score data, an engraved edition, a generated table, or musical context gives a concrete reason to doubt a corpus value.
- Use `flagged_needs_adjudication` when the discrepancy is credible but the correct replacement is not yet established.
- Use `confirmed` only when the relevant source evidence establishes the replacement.
- Apply confirmed changes to the authoritative MuseScore source in a fork of the affected subcorpus, then regenerate derived tab-separated value (TSV) tables with ms3, the MuseScore corpus-processing toolkit.
- Use `fixed_in_fork` after the source change, regeneration, and focused validation are committed in our fork.
- Never convert an unresolved JiMS naming failure into a corpus correction merely because a different annotation would be easier to name.
- Preserve the original value, proposed value, evidence, discovery path, and fork commit or Pull Request (PR) in `candidates.tsv`.
- Keep upstream submission deferred until JiMS chord-naming successfully names the corpus, as directed by the project owner. Our forks remain the working correction authority in the meantime.

## Repository boundary

This repository is a meta-repository: its musical corpora are Git submodules, meaning links to separate repositories at fixed commits. The registry lives here because it spans subcorpora. A musical correction itself belongs in a fork of the affected subcorpus, where the authoritative `MS3/*.mscx` score and its regenerated tables live.

## Evidence inventories

`evidence-inventories.tsv` records larger JiMS-generated screening and adjudication sets that have not yet been converted into individual correction decisions. A screening warning is not automatically an error; it is a reproducible queue for investigation.

## Current cases

The Rachmaninoff Op. 42 variation 20 case is confirmed and fixed in our subcorpus fork. The Medtner Op. 48 No. 1 bass discrepancy is recorded without changing the corpus because the digital score alone does not settle whether the harmony label, its intended analytical root, or its figured bass should change.
