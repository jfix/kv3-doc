OECD Journal
============

RePEc files
-----------

Series templates hold information that is common to all elements of a series. An archive might have more than one series. Journals are listed in one simple text file with an .rdf extension called oecseri.rdf.  

Identification
--------------

Any Kappa item of catalogue type ``Journal`` (sub-model: 1201) may become a candidate for export to RePEc

Eligibility
-----------

An identified Kappa item can only be exported if all of the following conditions are met:

* The item has at least one manifestations with any of the following availability statuses:
	* ``Published`` (100) OR
	* ``Discontinued`` (200)
* The item has a handle (repecDirectorate)
* The item has at least one eligible child 
* The IGO is OECD
* The item is not blocked for export

Metadata
--------

+-------------------------+-----------------------------+--------+-----------------------------------------------------------------------+
|                         |                             |        |                                                                       |
|   RePEc property        |   Kappa property       |   FRBR |   Export Rules and comments                                           |
|                         |                             |        |                                                                       |
+-------------------------+-----------------------------+--------+-----------------------------------------------------------------------+
|                         |                             |        |                                                                       |
|   Template-type:        |   N/A                       |   N/A  |   Hardcoded value in XSLT: ReDIF-Series 1.0                           |
|                         |                             |        |                                                                       |
+-------------------------+-----------------------------+--------+-----------------------------------------------------------------------+
|                         |                             |        |                                                                       |
|   Name:                 |   title                     |   E    |   If titles in multiple languages exist, only the                     |
|                         |                             |        |   title in the language of the journal is exported                    |
|                         |                             |        |                                                                       |
+-------------------------+-----------------------------+--------+-----------------------------------------------------------------------+
|                         |                             |        |                                                                       |
|   Type :                |   N/A                       |   N/A  |   Hardcoded value in XSLT: ReDIF-Article                              |
|                         |                             |        |                                                                       |
+-------------------------+-----------------------------+--------+-----------------------------------------------------------------------+
|                         |                             |        |                                                                       |
|   ISSN:                 |   ISSN                      |   M    |   eISSN is exported (add a hash after 4th character                   |
|                         |                             |        |   of ISSN)                                                            |
|                         |                             |        |                                                                       |
+-------------------------+-----------------------------+--------+-----------------------------------------------------------------------+
|                         |                             |        |                                                                       |
|   Provider-Name:        |   publisher                 |   W    |   Comma separated list.                                               |
|                         |                             |        |   If more than one publisher, OECD is to be listed first              |
|                         |                             |        |                                                                       |
+-------------------------+-----------------------------+--------+-----------------------------------------------------------------------+
|                         |                             |        |                                                                       |
|   Provider-Homepage:    |   N/A                       |   N/A  |   Hardcoded value in XSLT: http://www.oecd.org                        |
|                         |                             |        |                                                                       |
+-------------------------+-----------------------------+--------+-----------------------------------------------------------------------+
|                         |                             |        |                                                                       |
|   Provider-Institution: |   N/A                       |   N/A  |   Hardcoded [TC1] value in                                            |
|                         |                             |        |   XSLT: RePEc:edi:enoecfr                                             |
|                         |                             |        |                                                                       |
+-------------------------+-----------------------------+--------+-----------------------------------------------------------------------+
|                         |                             |        |                                                                       |
|   Maintainer-Email:     |   repecContact              |   W    |                                                                       |
|                         |                             |        |                                                                       |
+-------------------------+-----------------------------+--------+-----------------------------------------------------------------------+
|                         |                             |        |                                                                       |
|   Handle:               |   repecDirectorate          |   W    |   RePEc:oec: + repecDirectorate                                       |
|                         |                             |        |                                                                       |
+-------------------------+-----------------------------+--------+-----------------------------------------------------------------------+
|                         |                             |        |                                                                       |
|   Order-Homepage:       |   xlink bookShop            |   M    |                                                                       |
|                         |                             |        |                                                                       |
+-------------------------+-----------------------------+--------+-----------------------------------------------------------------------+
|                         |                             |        |                                                                       |
|   Restriction:          |   ilibraryaccesstype        |   E    |   If ilibraryaccesstype = 3 then                                      |
|                         |                             |        |   "Full text available to READ online. PDF download available to OECD |
|                         |                             |        |   iLibrary subscribers."                                              |
|                         |                             |        |                                                                       |
+-------------------------+-----------------------------+--------+-----------------------------------------------------------------------+
|                         |                             |        |                                                                       |
|   Followup:             |   xlink continues (reverse) |   E    |   RePEc handle of continuing journal                                  |
|                         |   repecDirectorate          |   W    |                                                                       |
|                         |                             |        |                                                                       |
+-------------------------+-----------------------------+--------+-----------------------------------------------------------------------+
|                         |                             |        |                                                                       |
|   Predecessor:          |   xlink continues           |   E    |   RePEc handle of continued journal                                   |
|                         |   repecDirectorate          |   W    |                                                                       |
|                         |                             |        |                                                                       |
+-------------------------+-----------------------------+--------+-----------------------------------------------------------------------+
