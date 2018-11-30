# EHR-TTS: Electronic Health Record (EHR) Temporal Tagger for Spanish


##  Digital Object Identifier (DOI)



## Introduction
------------

This grammar is an adaptation to the medical domain of the cross-domain grammar available
in HeidelTime [1] (https://github.com/HeidelTime/heideltime). This adapted grammar can be used 
to detect temporal expressions in real clinical data.

HeidelTime is a multilingual, domain-sensitive temporal tagger developed at the Database 
Systems Research Group at Heidelberg University. It extracts temporal expressions from 
documents and normalizes them according to the TIMEX3 annotation standard. HeidelTime is 
available as UIMA annotator and as standalone version. 

Covered languages: Spanish.


## Prerequisites
-------------

This software requires to HeidelTime. The grammar has been tested with version 2.2.1 and it 
should work with recent versions. HeidelTIme is licensed  under the GNU General Public License 
(Version 3). You can download it from the following website: 

https://github.com/HeidelTime/heideltime


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

Install and test your HeidelTime installation following the instructions given by HeidelTime
developers. Copy the "spanish_ehr/" directory into the "resources/" directory of HeidelTime and
select "spanish_ehr" at runtime.


## Contact
------

Aitor Gonzalez-Agirre (aitor.gonzalez@bsc.es)


## License
-------

See LICENSE file.

## References

[1] Strötgen, Gertz: HeidelTime: High Qualitiy Rule-based Extraction and Normalization of Temporal Expressions. SemEval'10. [PDF](http://www.newdesign.aclweb.org/anthology/S/S10/S10-1071.pdf)  [Bibtex](http://dbs.ifi.uni-heidelberg.de/fileadmin/Team/jannik/publications/stroetgen_bib.html#SEMEVAL2010)
