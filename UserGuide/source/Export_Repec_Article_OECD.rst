OECD Article
============

RePEc files
-----------

Item templates hold information about the individual items, in this case, journal articles. These templates are held in separate directories, one for each series. Note Observer Articles are not exported to RePEc.

Article templates are in simple text files that have an .rdf extension. The rest of the file name is irrelevant to RePEc. Templates may be grouped or put one per file. Nevertheless, the files must be in the series’ directory.

Articles published during the current year will be exported in individual files, one per paper, with a filename <di>.rdf if DI exists, otherwise <expression-id>.rdf. 

Articles published before the current year will be grouped in a single file named <foldername>.rdf.  

Identification
--------------

Any Kappa item of catalogue type ``Journal Article`` (sub-model: 1505) may become a candidate for export to RePEc

Eligibility
-----------

An identified Kappa item can only be exported if all of the following conditions are met:

* The item has a DOI 
* The IGO is OECD
* At least one manifestation available
* The item has at least one of the above manifestations with any of the following statuses:
	* ``Published`` (100)  or
	* ``Published Online first`` (90)  or
	* ``Forthcoming`` (50)  or
	* ``Discontinued`` (200)
* The item is not blocked for export 
 
Metadata
--------

+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   RePEc property         |   Kappa property |   FRBR |   Export Rules and comments                                           |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   Template-type:         |   N/A                 |   N/A  |   Hardcoded value in the XSLT: ReDIF-Article 1.0                      |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   Author Cluster         |   from author         |   W    |   Repeat each cluster of author metadata as there                     |
|                          |                       |        |   are authors                                                         |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   Author-Name:           |   givenName           |        |                                                                       |
|                          |   familyName          |        |                                                                       |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   Author-Email:          |   email               |        |   optional                                                            |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   Author-Workplace-Name: |   affiliation         |        |   optional                                                            |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   Title:                 |   title               |   E    |   title + ":" + subtitle                                              |
|                          |   subtitle            |        |                                                                       |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   Abstract:              |   abstract            |   E    |                                                                       |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   Classification-JEL:    |   jel                 |   W    |   Comma separated list                                                |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   Keywords:              |   keyword             |   E    |   Comma separated list                                                |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   Journal:               |   xlink               |   W    |   xlink type="hasarticle"                                             |
|                          |                       |        |   reverse="true"                                                      |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   Year:                  |   dateOfPublication   |   M    |   year portion only                                                   |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   Pages:                 |   startPage           |   M    |   startPage + "-" + endPage                                           |
|                          |   endPage             |   M    |                                                                       |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   Volume:                |   volume              |   W    |   xlink type="hasarticle"                                             |
|                          |                       |        |   reverse="true"                                                      |
|                          |                       |        |   volume of parent issue                                              |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   Issue:                 |   issue               |   W    |   xlink type="hasarticle"                                             |
|                          |                       |        |   reverse="true"                                                      |
|                          |                       |        |   issue of parent issue                                               |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   File-URL:              |   doiPrefix           |   E    |   doiPrefix + "/" + doiSuffix                                         |
|                          |   doiSuffix           |        |                                                                       |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   File-Format:           |   N/A                 |   N/A  |   Harcoded value in XSLT: text/html                                   |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+
|                          |                       |        |                                                                       |
|   Handle:                |   DI                  |   M    |   xlink type="hasarticle"                                             |
|                          |   xlink               |   W    |   reverse="true"                                                      |
|                          |   repecDirectorate    |   W    |                                                                       |
|                          |                       |        |   Handle: RePEc:oec: + repecDirectorate (of parent) + ":" + DI (if it |
|                          |                       |        |   exists, otherwise expression-id + language)                         |
|                          |                       |        |                                                                       |
+--------------------------+-----------------------+--------+-----------------------------------------------------------------------+