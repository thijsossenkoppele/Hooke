# Hooke
This repository contains the appendix to Thijs Ossenkoppele's MA thesis (MA History and Philosophy of Science, Utrecht University 2022). The following resources can be found here:
  1. The Robert Hooke Bibliography.
  2. The Robert Hooke Corpus.
  3. Term-Concept Mappings.
  4. Annotations.
  5. My MA thesis: 'Robert Hooke's Baconianism. A Corpus-Based Study'.
# 1. The Robert Hooke Bibliography
The [Robert Hooke Bibliography](https://docs.google.com/spreadsheets/d/17OXFChkDK9xKA5oxtE6vi-GzYVqKVxd3-gcuD7q9yiw/edit?usp=sharing) is a Google Sheet with 356 entries. Each row is dedicated to a separate text by Robert Hooke, and the columns indicate dates, pages, sources, publishing information, notes, etc. The texts from the bibliography that are currently in the Robert Hooke Corpus are marked in the 'In Corpus' column.
# 2. The Robert Hooke Corpus
The Robert Hooke Corpus contains 229 documents, 4079 paragraphs, and 885.332 tokens. It has been manually corrected for OCR errors. Two versions of the corpus are available: [the Robert Hooke Corpus in txt format](https://drive.google.com/file/d/1TS7fM4wjH-79XxH0rML6zxLSPPXplvXr/view?usp=sharing) and [the Robert Hooke Corpus in FoLiA XML format](https://drive.google.com/file/d/1sMwz98ZPcHkM0pNsbPdUsyfwn2KkNmi0/view?usp=sharing). The txt files are paragraph segmented by double newlines. The [FoLiA](https://proycon.github.io/folia/) files have first been tokenized (word, sentence, and paragraph) by [UCTO](https://webservices.cls.ru.nl/ucto). The UCTO-FoLiA conversion was done through this simple script (UPDATE: using this script is not necessary, spaCy NLP can be added to your FoLiA files simply from the command line, see [here](https://github.com/proycon/spacy2folia)):
```
import spacy
import folia.main as folia
from spacy2folia import spacy2folia
import os

nlp = spacy.load("en_core_web_sm")

with os.scandir('HookeUcto/') as dir:
	for inputfolia in dir:
		f = open(inputfolia, 'r')
		fname = str(f.name)
			
		if fname.endswith(".xml"):
			foliadoc = folia.Document(file=fname)
			spacy2folia.convert_folia(foliadoc, nlp)
			foliadoc.save(fname + ".output.xml", 'w+')
		else:
			continue
```
# 3. Term-Concept Mappings
The term-concept mappings that were used in writing the thesis can be found [here](https://docs.google.com/spreadsheets/d/1srdBZElcMJlUF3-Hl6sdC08Vlv3dehmatInuPUdPd50/edit?usp=sharing). The sheet contains terms that are closely related (functionally synonymous or semantically similar) to subconcepts of the concept 'Baconianism'. Only lists C (Natural History), D (Bits of Theory), and F (False Appearances) have been used in this thesis.
# 4. Annotations
The annotations that were carried out in writing this thesis can be found [here](https://docs.google.com/spreadsheets/d/1bOhLmXqF191UaVrM1yzJ9cyduzuKUldC9jga7nvwzZk/edit?usp=sharing). The annotations correspond to two separate annotation tasks: 
1. **Research Question 1:** To what extent does Hooke’s conception of the (internal) sources of false appearances deviate from Bacon’s doctrine of the idols?
   - **Subquestion 1a:** Is at least one of Bacon’s four idols represented in this paragraph?
   - **Subquestion 1b:** Does Hooke introduce a source of false appearances that cannot be subsumed under one of Bacon’s idols?
   - **Subquestion 1c:** Does Hooke encourage the use of some method for detecting or avoiding the false appearances found in answering SQ1 and/or SQ2?
2. **Research Question 2a:** Is there, cf. Mulligan (1992) and Sacco (2019), indeed a ‘gradual merging’ of the natural historical and philosophical parts in Hooke’s methodological programme?
   **Research Question 2b:** If so, can we tell 1) when this merging sets in, and 2) whether the merging is apparent in all types of text?
   **Research Question 2c:** If not, does Hooke maintain a clear methodological distinction between the historical and the philosophical parts (as opposed to a mere conceptual distinction without a methodological division of labor between the historian and philosopher)?
   - **Subquestion 2a:** Does this paragraph contain a suggestion of a distinction between the historical and the philosophical components of investigation into nature?
   - **Subquestion 2b:** If 1 or 0 to SQ1a: Are there in this paragraph also clear methodological directions for the respective natural historical and natural philosophical parts, and/or directions for connecting the two?
   - **Subquestion 2c:** Does this paragraph contain expressions that explicitly suggest the merging of natural historical and philosophical methods?
Each paragraph was scored with 1 (yes), 0 (maybe/more context necessary), or -1 (no). For details about the columns in the annotation sheets, see [here](https://github.com/martinreynaert/HitPaRank#contents-of-output-list-a--extracted-paragraphs).
# 5. Robert Hooke's Baconianism. A Corpus-Based Study
The MA thesis to which this repository is the appendix, and which contain more details about the exact aim of the files in this repository, can be found [here](https://drive.google.com/file/d/1nsiBsahNoeX34K6dMSqc_79PWRUZ4GDs/view?usp=sharing). 

   






