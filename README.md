# @cantonese/phonology

A library for working with Cantonese phonology and other romanizations (syllabaries, syllabic orthographies) of Cantonese. Useful for both mundane conversion tasks and possibly able to serve as a foundation for linguistic research and visualization.

## Usage

### Installation

Published as a modules-only JavaScript package.

`npm install --save @cantonese/phonology`

### Examples

For simple conversion between syllabaries:
```js
var sentence = 'ngo5dei6 wui5 jat1cai4 sik6faan6.';

// convert(string, from, to);
convert(sentence, { syllabary: 'jyutping' }, { syllabary: 'yale', { tones: 'numeric' } });
convert(sentence, { syllabary: 'jyutping' }, { syllabary: 'yale', { tones: 'diacritic' } });
```

## Romanizations (Syllabaries, Syllabic Orthographies)

Romanizations and other syllabic orthographies are a good source of phonological data as they represent an inventory of the phonemes of a language at a particular point in time. You can build upon data and patterns in this library to convert between any two syllabarizations.

### Included Syllabaries

This library includes full support for the following syllabaries:

- IPA
- Jyutping
- Yale

### Extant Syllabaries

Further, this library should eventually include support for all other known Cantonese syllabaries, including (but not limited to):

- 1828 - Robert Morrison, Vocabulary of the Canton Dialect
- 1847 - Devan
- 1854 - Bonney
- 1855 - Chalmers (Updated Morrison)
- 1888 Standard Romanization (Cowles)
- S.L. Wong
- Guangzhou
- HKIEd
- Sidney Lau
- Meyer-Wempe
- Barnett-Chao
- Hong Kong Government Cantonese Romanisation
- Macau Government Cantonese Romanization
- 1971 常用字廣州話讀音表:拼音方案 AKA 教院式拼音方案 by Yu Ping Chiu (余秉昭)

Please file issues with references to primary sources for any missing syllabary in order to have it included.

## Phonologies

Cantonese, without an orthographic anchor for phonemes, has changed significantly throughout the years. You can build upon data and patterns in this library to review the evolution of the language as well as its divergence from other Sinitic languages.

This library uses a descriptive method of describing how a particular sound is produced (using IPA descriptions) and then specifies the relationship between that description and an orthographic representation—including standard IPA symbols for that description. Since the phonetics are decoupled from from orthographic representation it is further possible to programmatically adjust phonetics. This should allow for conversions between separate systems created in different time periods.

### Syllabaries

Syllabaries, by nature, provide a fixed phonetic representation relative to the orthography that the syllabary is specified within. This, paired with an intent to be complete, makes them an ideal source of phonological data.

### Rimes

Rime tables specify sound relationships between characters within the Sinitic language family. We have rime tables all the way back to 切韻 from 601 CE, to 廣韻 in 1008 CE, and many more produced since then. Based on comparative studies of loan words in adjacent languages, some phonemes can be guessed.

These rime tables can be used to create estimated phonologies for historic periods which could possibly be used to allow for conversion between syllabaries of different branches. Additional data for particular branches may enable penciling in additional phonetic guesses.

## Education & Research

It is possible that, in time, this library could be used to produce visualizations of:
- the introduction of the `ei` dipthong into Cantonese.
- the merger between dental and alveolar affricates.
- and more!

Any phonological data or models made available here could possibly be used as inputs for computational linguistic models to improve upon results for:
- Converting characters to pronuncations.
- Converting between differing character sets.

And entirely new (and possibly bad) ideas might be attemptable, such as direct conversion between wildly divergent syllabaries. For example, converting between Cantonese Jyutping and Mandarin Pinyin without needing to use an intermediate character-based orthographic representation.

## Legal

The code in this repository is not licensed for reuse.

## Development

Information for contributors to this library.

### TODO

- [ ] Add a build step.
  - [ ] Pre-calculate and pack coordinates.
  - [ ] Dynamically check for confusables and populate the appropriate array.
- [ ] Specify the phonological description schema.
- [ ] Implement phonological mapping helpers.
