# Requirements

## Definitions

* `domain`: An area of knowledge.
* `topic`: A subject, theme, category, or general area of interest<sup>1</sup>.
* `concept`: An understanding, generalization, or abstraction of a particular set of instances or occurrences<sup>1</sup>.
  * `lexical concept`: Concept that can be equated to a single word<sup>2</sup>.
  * `extensions`:
    * `monadic concept`: (or "one-place" concept) Concept or expression that a single object by itself can satisfy<sup>3</sup>.
    * `polyadic concept`: (or "relational" or "many-place") Concept or expression that represents the set of all sequences of objects that satisfy the concept or expression in question<sup>3</sup>, e.g.:
      * The `extension` of "before" is the set of all (ordered) pairs of objects such that the first one is before the second one.
* `keyword`: #TODO
* `multiword expression`: (`mwe`) e collections of words which co-occur and are idiosyncratic in one or more aspects of their form or meaning<sup>4</sup>.
  * `compositional mwe`: The meaning of the `lexical concept` can be composed (i.e. aggregated) from those of its constituent parts.
    * Tend to evolve from "institutional usage", e.g. "traffic signal", "good morning", "Prime Minister".
  * `non-compositional mwe`: The meaning of the `lexical concept` can not be composed from those of its constituent parts.
    * e.g. "red tape", "spill the beans", "run for office".
  * `collocations`: are MWEs which are only statistically idiosyncratic; in other respects they conform with the general rules
of the language for syntactic well-formedness and semantic compositionality<sup>4</sup>.
* `seed term`: A `keyword` or `mwe` representing a `lexical concept`.

## User Stories

### Domain Scoping

1. Research `domain`.
2. Identify main `topics`.
3. Scope key `concepts`.
4. Define `seed terms` for each `topic` and `concept`.

### Corpus Building

1. Identify data sources with content relevant to the `domain` of interest.
2. Use `seed terms` to mine/extract for `domain`-relevant sample data (e.g. documents, sentences, utterances, tweets, etc.).
3. Label every sample datum with the respective `seed_term` used to filter/search for it.
     * Do not use "OR" conditions.
     * You can use "AND" conditions, and add both/all `seed terms` used in the condition.
4. Aggregate all sample datum and their corresponding metadata (i.e. labels, researcher's notes, etc.)

### Information Extraction Phase: Term Extraction

1. Import corpus.
2. Extract `keywords`.
3. Extract `mwe`.
4. Extract `collocations`.

### Curation Phase: Semantic Modelling

1. Group `keywords` and `mwe` into concepts.
2. Find synonyms for `keywords` and `mwe`.
3. Add synonyms of `keywords` and `mwe` to concepts.
4. If a bigger corpus is required, use `keywords` and `mwe` as `seed terms` by iterating: [Corpus Building](requirements.md#corpus-building)

### Ontology Curation

1. Organise concepts into a hierarchy.
2. Define relationships between concepts.
3. Define rules and conditions for relationships.

### Text Alignment Phase

1. Cluster key segments by similarity (symbolically, e.g. Jaccard).
2. Identify variant tokens within each cluster of key segments.
3. Identify groupable variant tokens into a coarser-grained concept.
4. Map tokens to all possible concepts (i.e. from the leaf concept all the way up the inheritance chain).
5. Extract all possible traces of concepts from cluster.
6. Iterate: [Curation Phase](requirements.md#curation-phase-semantic-modelling)

### QA Phase

1. Tag test corpus with concept traces.

## References

[1] [Concepts vs. Topics](https://wikidiff.com/concept/topic)
[2] [Concept](https://en.wikipedia.org/wiki/Concept)
[3] [Extension](https://en.wikipedia.org/wiki/Extension_(semantics))
[4] [Linguistic Fundamentals for Natural Language Processing II, Chapter 6](https://link.springer.com/chapter/10.1007/978-3-031-02172-5_6)
