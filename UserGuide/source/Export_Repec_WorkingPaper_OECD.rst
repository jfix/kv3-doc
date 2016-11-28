OECD Working Paper 
==================

RePEc files
-----------

Item templates hold information about the individual items, in this case, working papers. These templates are held in separate directories, one for each series.

Working Paper templates are in simple text files that have an .rdf extension. The rest of the file name is irrelevant to RePEc. Templates may be grouped or put one per file. Nevertheless, the files must be in the series’ directory.
 
Working Papers published during the current year will be exported in individual files, one per paper, with a filename <di>.rdf if DI exists, otherwise <expression-id>.rdf. 

Working Papers published before the current year will be grouped in a single file named <foldername>.rdf.  


Identification
--------------

Any Kappa item of catalogue type ``Working Paper`` (sub-model: 1504) may become candidate for export to RePEc

Eligibility
-----------

An identified Kappa item can only be exported if all of the following conditions are met:

* The item has a DOI 
* The IGO is OECD
* The item has at least one of the above manifestations with any of the following statuses:
	* ``Published`` (100)  or
	* ``Discontinued`` (200)
* The item is the child of an eligible working paper series 
* The item belongs to a series in the same language (stand-alone translations, or working papers belonging to a series in a different language, are not exported to RePEc)
* The item is not blocked for export 

Metadata
--------

+-----------------------+-----------------------+--------+-------------------------------------------------------------------------+
|                       |                       |        |                                                                         |
|   RePEc property      |   Kappa property |   FRBR |   Export Rules and comments                                             |
|                       |                       |        |                                                                         |
+-----------------------+-----------------------+--------+-------------------------------------------------------------------------+
|                       |                       |        |                                                                         |
|   Template-type:      |   N/A                 |   N/A  |   Hardcoded value in XSLT: ReDIF-Paper 1.0                              |
|                       |                       |        |                                                                         |
+-----------------------+-----------------------+--------+-------------------------------------------------------------------------+
|                       |                       |        |                                                                         |
|   Author-Name:        |   author              |   W    |   If physical author then:                                              |
|                       |                       |        |   givenName + familyName                                                |
|                       |                       |        |   else if organisation with accronym:                                   |
|                       |                       |        |   accronym                                                              |
|                       |                       |        |   else                                                                  |
|                       |                       |        |   organisation prefName                                                 |
|                       |                       |        |                                                                         |
|                       |                       |        |   If multiple authors, one per line                                     |
|                       |                       |        |                                                                         |
+-----------------------+-----------------------+--------+-------------------------------------------------------------------------+
|                       |                       |        |                                                                         |
|   Title:              |   title               |   E    |   title + " : " + subtitle                                              |
|                       |   subtitle            |        |                                                                         |
|                       |                       |        |                                                                         |
+-----------------------+-----------------------+--------+-------------------------------------------------------------------------+
|                       |                       |        |                                                                         |
|   Abstract:           |   abstract            |   E    |   Line breaks removed                                                   |
|                       |                       |        |                                                                         |
+-----------------------+-----------------------+--------+-------------------------------------------------------------------------+
|                       |                       |        |                                                                         |
|   Creation-Date:      |   dateOfPublication   |   M    |                                                                         |
|                       |                       |        |                                                                         |
+-----------------------+-----------------------+--------+-------------------------------------------------------------------------+
|                       |                       |        |                                                                         |
|   Number:             |   number              |   W    |   If it exists                                                          |
|                       |   volume              |   W    |   number                                                                |
|                       |   issue               |   W    |   else                                                                  |
|                       |                       |        |   volume + "/" +  issue                                                 |
|                       |                       |        |                                                                         |
+-----------------------+-----------------------+--------+-------------------------------------------------------------------------+
|                       |                       |        |                                                                         |
|   Classification-JEL: |   JEL                 |   W    |   List separated by semi-colon                                          |
|                       |                       |        |                                                                         |
+-----------------------+-----------------------+--------+-------------------------------------------------------------------------+
|                       |                       |        |                                                                         |
|   Keywords:           |   keyword             |   E    |   List separated by commas                                              |
|                       |                       |        |                                                                         |
+-----------------------+-----------------------+--------+-------------------------------------------------------------------------+
|                       |                       |        |                                                                         |
|   File-URL:           |   doiPrefix           |   E    |   "http://dx.doi.org/" + doiPrefix + "/" + doiSuffix                    |
|                       |   doiSuffix           |   E    |                                                                         |
|                       |                       |        |                                                                         |
+-----------------------+-----------------------+--------+-------------------------------------------------------------------------+
|                       |                       |        |                                                                         |
|   File-Format:        |   N/A                 |   N/A  |    Hardcoded in XSLT: type of URL                                       |
|                       |                       |        |                                                                         |
+-----------------------+-----------------------+--------+-------------------------------------------------------------------------+
|                       |                       |        |                                                                         |
|   Handle:             |   number              |   W    |   To find series: xlink type="haspaper"                                 |
|                       |   volume              |   W    |   reverse="true"                                                        |
|                       |   issue               |   W    |                                                                         |
|                       |   language            |   E    |   "RePEc:oec:" + WPS RePEC directory + ":" + WP Number + "-" + language |
|                       |   repecDirectorate    |   W    |                                                                         |
|                       |                       |        |                                                                         |
+-----------------------+-----------------------+--------+-------------------------------------------------------------------------+
