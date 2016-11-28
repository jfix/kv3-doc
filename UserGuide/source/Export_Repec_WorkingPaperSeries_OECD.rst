OECD Working Paper Series
=========================

RePEc files
-----------

Series templates hold information that is common to all elements of a series. An archive might have more than one series. The series templates are all listed in one simple text file with an .rdf extension called oecseri.rdf. Journals are also listed in this file (:doc:`Export_Repec_Journal_OECD.rst`).  

Identification
--------------

Any Kappa item of catalogue type ``Working Paper Series`` (sub-model: 1104) may become a candidate for export to RePEc

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

+-------------------------+------------------------------------------+--------+---------------------------------------------------+
|                         |                                          |        |                                                   |
|   RePEc property        |   Kappa property                    |   FRBR |   Export Rules and comments                       |
|                         |                                          |        |                                                   |
+-------------------------+------------------------------------------+--------+---------------------------------------------------+
|                         |                                          |        |                                                   |
|   Template-type:        |   N/A                                    |   N/A  |   Hardcoded value in XSLT: ReDIF-Series 1.0       |
|                         |                                          |        |                                                   |
+-------------------------+------------------------------------------+--------+---------------------------------------------------+
|                         |                                          |        |                                                   |
|   Name:                 |   title                                  |   E    |   If series is in FR, take FR title, otherwise EN |
|                         |                                          |        |   title                                           |
|                         |                                          |        |                                                   |
+-------------------------+------------------------------------------+--------+---------------------------------------------------+
|                         |                                          |        |                                                   |
|   Type:                 |   N/A                                    |   N/A  |   Hardcoded value in XSLT: ReDIF-Paper            |
|                         |                                          |        |                                                   |
+-------------------------+------------------------------------------+--------+---------------------------------------------------+
|                         |                                          |        |                                                   |
|   Provider-Name:        |   N/A                                    |   N/A  |    Hardcoded value in XSLT: OECD Publishing       |
|                         |                                          |        |                                                   |
+-------------------------+------------------------------------------+--------+---------------------------------------------------+
|                         |                                          |        |                                                   |
|   Provider-Homepage:    |   directorate                            |   W    |   If                                              |
|                         |                                          |        |   directorate is DEV then                         |
|                         |                                          |        |   "http://www.oecd.org/dev"                       |
|                         |                                          |        |   else                                            |
|                         |                                          |        |   "http://www.oecd.org"                           |
|                         |                                          |        |                                                   |
+-------------------------+------------------------------------------+--------+---------------------------------------------------+
|                         |                                          |        |                                                   |
|   Provider-Institution: |   directorate (repecProviderInstitution) |   W    |   "RePEc:edi:" + repecProviderInstitution         |
|                         |                                          |        |                                                   |
+-------------------------+------------------------------------------+--------+---------------------------------------------------+
|                         |                                          |        |                                                   |
|   Maintainer-Email:     |   repecContact                           |   W    |                                                   |
|                         |                                          |        |                                                   |
+-------------------------+------------------------------------------+--------+---------------------------------------------------+
|                         |                                          |        |                                                   |
|   Handle:               |   repecDirectorate                       |   W    |   "RePEc:oec:" + repecDirectorate                 |
|                         |                                          |        |                                                   |
+-------------------------+------------------------------------------+--------+---------------------------------------------------+