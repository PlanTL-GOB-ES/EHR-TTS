# EHR-TTS: Electronic Health Record (EHR) Temporal Tagger for Spanish

## Digital Object Identifier (DOI)

https://doi.org/10.5281/zenodo.2560356



## Introduction
------------

This grammar is an adaptation to the medical domain of the cross-domain grammar available
in HeidelTime [1] (https://github.com/HeidelTime/heideltime), a multilingual, domain-sensitive 
temporal tagger developed at the Database Systems Research Group at Heidelberg University. 
HeidelTime extracts temporal expressions from documents and normalizes them according to the TIMEX3 
annotation standard. It is available as UIMA annotator and as standalone version. 

This adapted grammar can be used to detect temporal expressions in real clinical data in Spanish.


## Prerequisites
-------------

This software requires HeidelTime installed on your system. The grammar has been tested with version 
2.2.1 and it should work with more recent versions. HeidelTime is licensed  under the GNU General Public 
License (Version 3). You can download it from the following website: 
https://github.com/HeidelTime/heideltime


Please, note that HeidelTime is an UIMA [2] component. It requires UIMA and sentence, token, 
and part-of speech annotations (HeidelTime includes a wrapper of TreeTagger [3] for UIMA).


## Directory structure
-------------------

<pre>
normalization/
This folder contains the files for normalized expressions. These files contain normalized values 
of expressions included in the repattern folder. They correspond to the ISO format for temporal 
information.

repattern/
This folder contains the files for expression patterns. Patterns are used to create regular 
expressions, which can be accessed by every rule. This allows to use category names 
(e.g., "month") instead of listing all items every time the category is needed in a rule.

rules/
This folder contains the rules to identify and normalize temporal expressions.
</pre> 


## Usage
-----

Install and test your HeidelTime installation following the instructions given by HeidelTime
developers. Copy the "spanish_ehr/" directory into the "resources/" directory of HeidelTime. 


## Examples

Run UIMA Collection Processing Engine:

<pre>
$ cpeGui.sh
</pre>

Create a workflow with the following components:

<pre>
Collection reader:
  - UIMA's file system collection reader:
    $UIMA_HOME/examples/descriptors/collection_reader/FileSystemCollectionReader.xml
    set "Input directory" to $HEIDELTIME_HOME/doc/
Analysis Engines
  - TreeTaggerWrapper located at
    HEIDELTIME_HOME/desc/annotator/TreeTaggerWrapper.xml
    set "Language" to "english"
    set "Annotate_tokens" to "true"
    set "Annotate_partofspeech" to "true"
    set "Annotate_sentences" to "true"
    set "Improvegermansentences" to "false"
  - HeidelTime located at
    HEIDELTIME_HOME/desc/annotator/HeidelTime.xml
    set "Date" to "true"
    set "Time" to "true"
    set "Duration" to "true"
    set "Set" to "true"
    set "Temponym" to "false"
    set "Language" to "english"
    set "Type" to "narratives"
CAS Consumer
  - UIMA's XMI Writer CAS Consumer located at
    $UIMA_HOME/examples/descriptors/cas_consumer/XmiWriterCasConsumer.xml
    set "Output Directory" to OUTPUT
</pre>


Save the workflow, set "spanish_ehr" as "language" and run the workflow.



## Contact
------

Aitor Gonzalez-Agirre (aitor.gonzalez@bsc.es)


## License
-------

See LICENSE file.

Copyright (c) 2017-2018 Secretaría de Estado para el Avance Digital (SEAD)

## References

[1] Strötgen, Gertz: HeidelTime: High Qualitiy Rule-based Extraction and Normalization of Temporal Expressions. SemEval'10. [PDF](http://www.newdesign.aclweb.org/anthology/S/S10/S10-1071.pdf)  [Bibtex](http://dbs.ifi.uni-heidelberg.de/fileadmin/Team/jannik/publications/stroetgen_bib.html#SEMEVAL2010)

[2] UIMA: https://uima.apache.org/

[3] TreeTagger: http://www.cis.uni-muenchen.de/~schmid/tools/TreeTagger/
