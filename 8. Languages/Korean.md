# Korean (한국어)

## Writing System

- Alphabetic syllabary (Hangul): 24 basic letters (14 consonants, 10 vowels), combined into ~40 grapheme blocks
- ~11,000 valid syllable blocks (each block = 2–3 letters)

## Linguistic Features

- Agglutinative morphology: many suffixes for tense, honorifics, case, etc.
- Subject–Object–Verb word order (SOV) with topic-prominent constructions

## NLP Considerations

- **Tokenization**: syllable blocks vs. jamo (letter) decomposition
- **Morphological analysis**: require segmenting stems + agglutinative suffix chains
- **Word segmentation**: spaces are reliable, but clitics and compound nouns can be ambiguous

## Resources

- Unicode Hangul Jamo ranges (U+1100–U+11FF, U+AC00–U+D7AF)
- OpenKoreanText tokenizer
- Korean Universal Dependencies treebanks
