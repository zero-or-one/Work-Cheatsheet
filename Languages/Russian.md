# Russian (Русский)

## Writing System

- Cyrillic script: 33 letters (А Б В Г Д Е Ё Ж З И Й К Л М Н О П Р С Т У Ф Х Ц Ч Ш Щ Ъ Ы Ь Э Ю Я)

## Linguistic Features

- Fusional morphology: six cases, three genders, verb aspect (perfective/imperfective)
- Flexible word order (often SVO, but topic/focus drives variation)

## NLP Considerations

- **Tokenization**: whitespace + handling of clitics (“-ся”)
- **Morphological tagging**: rich inflection → use dictionaries (e.g., pymorphy2)
- **Named-entity recognition**: capitalize distinctions may vary

## Resources

- Russian National Corpus
- OpenCorpora morphological lexicon
- Taiga Universal Dependencies treebank
