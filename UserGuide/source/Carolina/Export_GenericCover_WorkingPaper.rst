Working papers 
==============

Identification
--------------

A Kappa item of catalogue type ``Working Paper" (sub-model: 1504) is also of iLibrary item type ``Working Paper``.  

Eligibility
-----------

The cover generation process selects all working papers meeting the following criteria:

* The working paper is eligible for iLibrary export (see eligibility rules in the Kappa to iLibrary Export document)
* The item has at least one manifestation of the following medium:
	* ``PDF`` (e)
	* The item has at least one manifestation with any of the following availability status:
	* ``Published`` (100) AND has an FTI 
	* ``Published Online First`` (90) AND has an FTI 
* The generate cover flag is set to true

Placement of cover in the PDF
-----------------------------

The cover page generated for a given working paper is added at the beginning of the PDF file.

Stand-alone Working Paper covers
--------------------------------

Stand-alone working papers are defined as those which parent working paper series is in a different language. Stand-alone working paper covers are different to other generic covers (specified in sections 5.6.3.5 and 5.6.3.6) in 2 ways:

* They include an additional citation of the other expression of the working paper, as well as an introductory text to that second citation (see section 5.6.3.7)
* They exclude the serial title (as well as working paper number) since a series in the language of the working paper does not exist.

CELE and PEB imprint
--------------------

Working papers whose parent series has one of the ISSNs in the table below, also have an imprint which determines the additional logo to be added to their generic cover (as shown in sections 5.8.9 and 5.8.10): 

+------------------------------------+------------+-----------+
|                                    |            |           |
|   Working paper series             |   ISSN     |   Imprint |
|                                    |            |           |
+------------------------------------+------------+-----------+
|                                    |            |           |
|   CELE Exchange, Centre for        |   20727925 |   14      |
|   Effective Learning Environments  |   20727933 |           |
|                                    |            |           |
+------------------------------------+------------+-----------+
|                                    |            |           |
|   PEB Exchange, Programme          |   16097548 |   6       |
|   on Educational Building          |   16843584 |           |
|                                    |            |           |
+------------------------------------+------------+-----------+

Metadata
--------

+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|   Wireframe  element    |   Kappa    |   Level |   Rule  for content                                              |   Rule for display                                                                   |   Example                                            |
|                         |   field         |         |                                                                  |                                                                                      |                                                      |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|   WP introduction       |   NA            |   NA    |   EN: "Please cite this paper as:"                               |   Text in the WP language                                                            |                                                      |
|                         |                 |         |   FR: "Merci                                                     |                                                                                      |                                                      |
|                         |                 |         |   d'utiliser le titre suivant lorsque vous citez ce document :"  |                                                                                      |                                                      |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|   WP introduction 2     |   NA            |   NA    |   EN :                                                           |   Text in the WP language.                                                           |                                                      |
|                         |                 |         |   "The original version of this paper was published as:"         |   NB. Only added to stand-alone generic covers                                       |                                                      |
|                         |                 |         |   FR: "La version                                                |                                                                                      |                                                      |
|                         |                 |         |   original de ce document a été publiée comme suit :"            |                                                                                      |                                                      |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|   Citation              |   NA            |   NA    |   See Citation Specification document                            |                                                                                      |                                                      |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|   Citation 2            |   NA            |   NA    |   See                                                            |   Contains the citation for the other expression of                                  |                                                      |
|                         |                 |         |   Citation Specification document                                |   the WP (usually the EN version).                                                   |                                                      |
|                         |                 |         |                                                                  |   NB. Only added to stand-alone generic covers                                       |                                                      |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+
|                         |                 |         |                                                                  |                                                                                      |     :doc:`WP_cover_Title1.jpg`                       |
|   WPS title             |   title         |   E     |   To find the WP parent series:                                  |   White text inside black box (see layout                                            |     :doc:`WP_cover_Title2.jpg`                       |
|                         |                 |         |   xlink:hasPaper                                                 |   documentation)                                                                     |                                                      |
|                         |                 |         |   (reverse link)                                                 |   NB. Not added to stand-alone generic covers                                        |                                                      |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|   WP edition            |   contentNumber |   W     |   If                                                             |   White text inside the black box containing the                                     |    "No. 1304"                                        |
|                         |   issueNumber   |   W     |   WP has a contentNumber:                                        |   series title (see layout documentation)                                            |                                                      |
|                         |   volume        |   W     |   "No. " +                                                       |   No break space                                                                     |   "2009/02"                                          |
|                         |                 |         |   contentNumber                                                  |   between "No." and contentNumber                                                    |                                                      |
|                         |                 |         |   If                                                             |   NB.                                                                                |                                                      |
|                         |                 |         |   WP has no contentNumber:                                       |   Not added to stand-alone generic covers                                            |                                                      |
|                         |                 |         |   volume                                                         |                                                                                      |                                                      |
|                         |                 |         |   + "/" +  issueNumber                                           |                                                                                      |                                                      |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|   WP title              |   title         |   E     |                                                                  |                                                                                      |                                                      |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|   WP subtitle           |   subTitle      |   E     |                                                                  |   In capital letters                                                                 |                                                      |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|   WP authors            |   author        |   W     |   If                                                             |   If                                                                                 |   One physical author:                               |
|                         |                 |         |   author is a person:                                            |   one physical author exists:                                                        |   Ken Davies                                         |
|                         |                 |         |   givenName                                                      |   givenName + familyName                                                             |   Multiple physical authors, no affiliation:         |
|                         |                 |         |   familyName                                                     |   If                                                                                 |   Anthony J. Kleitz, Charles A.                      |
|                         |                 |         |                                                                  |   multiple physical authors exist:                                                   |   Tsai, John Doe                                     |
|                         |                 |         |   If                                                             |   givenName + familyName                                                             |   Multiple physical authors, first with affiliation: |
|                         |                 |         |   author is an organization:                                     |   Authors are displayed in the same order as they are                                |   Anthony J. Kleitz*, Charles A. Tsai, James         |
|                         |                 |         |   label type="acronym"                                           |   stored in the working paper bibliographic record. The list of authors is separated |   Henson, John Doe                                   |
|                         |                 |         |   if metadata exists otherwise:                                  |   by commas (followed by a space). No carriage return added between authors or       |   If author is                                       |
|                         |                 |         |   prefLabel                                                      |   between first and last name.                                                       |   an organisation:                                   |
|                         |                 |         |                                                                  |   If first physical author in the list has an                                        |   OECD                                               |
|                         |                 |         |                                                                  |   affiliation:[TC1]                                                                  |                                                      |
|                         |                 |         |                                                                  |   The                                                                                |                                                      |
|                         |                 |         |                                                                  |   author’s name is followed by an asterisk (in superscript). There’s no space        |                                                      |
|                         |                 |         |                                                                  |   between name and asterisk.                                                         |                                                      |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|   WP IGO publisher logo |   NA            |         |   Hardcoded in the xslt                                          |   Logo in the language of WP                                                         |  :doc:`WP_cover_OECD_publishing_EN.jpg`              |
|                         |                 |         |                                                                  |                                                                                      |  :doc:`WP_cover_OECD_publishing_FR.jpg`              |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|   WP logo 1             |   NA            |         |   Hardcoded in the xslt                                          |   Same logo for all WP languages                                                     |  :doc:`WP_cover_Logo1.jpg`                           |
|                         |                 |         |                                                                  |   NB. NOT added to PEB and CELE generic covers                                       |                                                      |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|   WP logo 2             |   NA            |         |   Hardcoded in the xslt                                          |   Logo in the language of WP                                                         |  :doc:`WP_cover_Logo2_EN.jpg`                        |
|                         |                 |         |                                                                  |                                                                                      |  :doc:`WP_cover_Logo2_FR.jpg`                        |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|   WP logo 3             |   NA            |         |   Hardcoded in the xslt                                          |   Same logo for all WP languages                                                     |  :doc:`WP_cover_Logo3.jpg`                           |
|                         |                 |         |                                                                  |   NB. Only added to PEB and CELE generic covers                                      |                                                      |
+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+
|                         |                 |         |                                                                  |                                                                                      |   :doc:`WP_cover_CELE_EN.jpg`                        |
|   WP logo 4             |   NA            |         |   Logo depends on imprint                                        |   Logo in the language of WP                                                         |   :doc:`WP_cover_CELE_FR.jpg`                        |
|                         |                 |         |                                                                  |                                                                                      |   :doc:`WP_cover_PEB_EN.jpg`                         |
|                         |                 |         |                                                                  |   NB. Only added to PEB and CELE generic covers                                      |   :doc:`WP_cover_PEB_FR.jpg`                         |
+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|   Jel classification    |   jel           |   W     |   EN : "JEL classification"                                      |   Text in the WP language                                                            |                                                      |
|                         |                 |         |   FR : "Classification JEL : "                                   |                                                                                      |                                                      |
|                         |                 |         |   jel code(s)                                                    |                                                                                      |                                                      |
|                         |                 |         |                                                                  |   List of Jel codes separated by                                                     |                                                      |
|                         |                 |         |                                                                  |   commas (followed by a space).                                                      |                                                      |
|                         |                 |         |                                                                  |   Jel’s section is vertically aligned to the top of the (WP IGO logo 2) logo         |                                                      |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+
|                         |                 |         |                                                                  |                                                                                      |                                                      |
|   Author Affiliation    |   author        |   W     |   affiliation (of author)                                        |   In the WP language.                                                                |                                                      |
|                         |   IGO           |   W     |   city (of IGO)                                                  |                                                                                      |                                                      |
|                         |                 |         |                                                                  |   An asterisk (in superscript, followed by a space), then the organisation           |                                                      |
|                         |                 |         |                                                                  |   acronym followed by a comma and its country.                                       |                                                      |
|                         |                 |         |                                                                  |   Affiliation                                                                        |                                                      |
|                         |                 |         |                                                                  |   section is vertically aligned to the bottom of the (WP IGO logo 2) logo[TC2]       |                                                      |
|                         |                 |         |                                                                  |                                                                                      |                                                      |
+-------------------------+-----------------+---------+------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------------+

Wireframe
---------

:doc:`WP_cover_wireframe.jpg`

Stand-alone Working Paper Wireframe
-----------------------------------

:doc:`WP_cover_wireframe_standalone.jpg`

CELE Wireframe
--------------

:doc:`WP_cover_wireframe_CELE.jpg`

PEB Wireframe
-------------

:doc:`WP_cover_wireframe_PEB.jpg`