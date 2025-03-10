![Version](https://img.shields.io/github/v/release/DCMLab/ravel_piano?display_name=tag)
[![DOI](https://zenodo.org/badge/{{ zenodo_badge_id }}.svg)](https://doi.org/{{ concept_doi }})
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/ravel_piano)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/ravel_piano](https://github.com/DCMLab/ravel_piano) and the corresponding
* documentation page [https://dcmlab.github.io/ravel_piano](https://dcmlab.github.io/ravel_piano)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/ravel_piano/introduction).

# Maurice Ravel – Piano Pieces (A corpus of annotated scores)

These piano showpieces are emblematic of the initial flowering of Ravel's advanced style that occurred around the end of
his troubled years at the Paris Conservatoire. Both Jeux d'eau and the suite Miroirs were products of Ravel's
association with the avant-garde artists' collective Les Apaches, and each of the five pieces of Miroirs is dedicated to
one or another of Ravel's colleagues in the group. The latter pieces are also well-known in orchestral versions, which
have been scored by composers including (besides Ravel himself) Percy Grainger and Steven Stucky.

## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/ravel_piano/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [ravel_piano.zip](https://github.com/DCMLab/ravel_piano/releases/latest/download/ravel_piano.zip)
  * [ravel_piano.datapackage.json](https://github.com/DCMLab/ravel_piano/releases/latest/download/ravel_piano.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/ravel_piano.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the piano piece *Jeux d’eau* has the following files:

* `MS3/Ravel_-_Jeux_dEau.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/Ravel_-_Jeux_dEau.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/Ravel_-_Jeux_dEau.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/Ravel_-_Jeux_dEau.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/Ravel_-_Jeux_dEau.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10 or later) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/Ravel_-_Jeux_dEau.harmonies.tsv")
notes = ms3.load_tsv("notes/Ravel_-_Jeux_dEau.notes.tsv")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/ravel_piano/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/ravel_piano/issues) and/or feel free to fork and submit pull requests.

## Cite as

> Johannes Hentschel, Yannis Rammos, Markus Neuwirth, & Martin Rohrmeier. (2025). Maurice Ravel – Piano Pieces (A corpus of annotated scores) [Data set]. Zenodo. https://doi.org/{{ concept_doi }}

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)

## Scores

Scores from musescore.com, transcribed by user PhilTA https://musescore.com/user/2749876

5th movement of Miroirs (*La vallée des cloches*) currently missing.

The three annotated files in this repository were initial experiments in applying the DCML harmony standard to 20th-century chromatic repertoire, an effort which has since been fruitfully extended. The language in these pieces is an ideal case study for this effort as many passages are demarcated by repeated alternations between some tall tertian chromatic harmony and the tonic triad. The harmonies present are therefore linked explicitly to a tonal center in a palpable way. Relating such tall tertian harmonies to one another in the absence of an obvious tonic triad is the focus of research efforts that are still ongoing.

## Overview
|                 file_name                 |measures|labels|standard| annotators |
|-------------------------------------------|-------:|-----:|--------|------------|
|Ravel_-_Jeux_dEau                          |      85|   257|2.1.0   |Adrian Nagel|
|Ravel_-_Miroirs_I._Noctuelles              |     132|     0|        |            |
|Ravel_-_Miroirs_II._Oiseaux_tristes        |      32|     0|        |            |
|Ravel_-_Miroirs_III._Une_Barque_sur_l'ocean|     143|   236|2.1.0   |Adrian Nagel|
|Ravel_-_Miroirs_IV._Alborada_del_gracioso  |     229|   368|2.1.0   |Adrian Nagel|


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
