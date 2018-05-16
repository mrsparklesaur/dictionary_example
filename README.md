# dictionary_example

Two files required:

## config.yaml
The configuration for the dictionary. Attributes must include:

name:
case_sensitive (bool) : Whether or not case matters for the terms. If case_sensitive
word_stemming (bool) : Whether or not words should be stemmed before matching is considered. If true, word stemming is applied and the effect is that the matching is looser. For example, "cretaceous" and "cretacallis" both have word stemmings of "cretac". As a general rule, if you want to find proper nouns as terms, word stemming should be false. If you want matching to include variants of a word (pluralizations, verbified nouns, etc), word_stemming should be true

## dictionary.csv

A list of terms, one per line.
If multiple words are provided, the first word is treated as the key term,
and the others are required as additional terms. This is useful
for creating hierarchical/synonym/filter structures. 

For example, an entry of:
Homo sapiens,mammalia,primates,hominidae

Will create a dictionary entry of "Homo sapiens" and require one of [mammalia, primates, hominidae] to also be mentioned within a document to be considered a match.


