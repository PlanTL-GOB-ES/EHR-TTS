# EHR-TTS: Electronic Health Record (EHR) Temporal Tagger for Spanish


##  Digital Object Identifier (DOI)



## Introduction
------------

This grammar is an adaptation to the medical domain of the cross-domain grammar available
in HeidelTime (https://github.com/HeidelTime/heideltime). This adapted grammar can be used 
to detect temporal expressions in real clinical data.

HeidelTime is a multilingual, domain-sensitive temporal tagger developed at the Database 
Systems Research Group at Heidelberg University. It extracts temporal expressions from 
documents and normalizes them according to the TIMEX3 annotation standard. HeidelTime is 
available as UIMA annotator and as standalone version. 

Covered languages: Spanish.


## Prerequisites
-------------

This software requires to HeidelTime.


## Directory structure
-------------------

<pre>
normalization/
This folder contains the files for normalized expressions.

repattern/
This folder contains the files for expression patterns.

rules/
This folder contains the rules for the temporal expressions.
</pre> 


## Usage
-----

Copy the "spanish_ehr/" directory into the "resources/" directory of HeidelTime.


## Contact
------

Aitor Gonzalez-Agirre (aitor.gonzalez@bsc.es)


## License
-------

See LICENSE file.
