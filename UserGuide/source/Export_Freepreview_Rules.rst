Export Rules
============

R002- Exported titles for chapters, tables, graphs, summaries and articles
--------------------------------------------------------------------------

Chapters, articles, tables, graphs, summaries and working papers are exported to the Free Preview with their parent publication´s main title and subtitle. The parent publication is defined by R007.

R004 - Exported embargo date and publication date for components
----------------------------------------------------------------

If their parent is available (see R007), chapters, articles, tables and graphs are exported to FreePreview with a publication date and an embargo date equal to their parent´s publication/embargo date as calculated following R005. 

Otherwise, these components are exportted with their own publication date and an embargo date as calculated following R005.

.. note::  his rule is based on the R40 iLibrary export rule.

R005 - Embargo Date / Publication Date
--------------------------------------

The iLibrary Publication date should be exported with the values corresponding to the latest (i.e. most restrictive) of the following dates in Kappa: publication date and embargo date.

The embargo date in the table below is the latest (i.e. most restrictive) of the embargo dates:

+--------------------------------------------+-----------------------------------+-----------------------------------+
|    KAPPA                                   |    iLibrary                       |                                   |
|                                            |    *prism:publicationDate*        |    *oecd:embargoDate*             |
+============================================+===================================+===================================+
|    No Embargo Date   A Publication Date    |    Publication Date of Kappa    |    Not exported                   |
+--------------------------------------------+-----------------------------------+-----------------------------------+
|    Embargo Date =   Publication Date       |    Publication Date of Kappa    |    Publication Date of Kappa    |
+--------------------------------------------+-----------------------------------+-----------------------------------+
|    Publication Date   < Embargo Date       |    Embargo Date of Kappa        |    Embargo Date of Kappa        |
+--------------------------------------------+-----------------------------------+-----------------------------------+
|    A Embargo Date   No Publication Date    |    items not exported             |    items not exported             |
+--------------------------------------------+-----------------------------------+-----------------------------------+

.. note:: Rule applied only to those cases where 'Publication Date' / 'Embargo Date' / 'Soft Embargo Date' (the later date in the future) is greater than 1 June 2015. - (Feature #9769)

R006 - Metadata preference for electronic products
--------------------------------------------------

One Free Preview is created per item, regardless of how many formats it exists in. If both the PDF and Excel records are eligible for Free Preview export, the metadata export preference should be:
* The PDF version should overrun the metadata of the XLS version.
* If no PDF version exists, then the metadata for the XLS version should be exported.

R007 Identification of Parent Publication
-----------------------------------------

Keepeek items of type ``Chapter`` and ``Article`` are exported with a parent relationship defined in their <isPartOf> property and parent Title/Subtitle metadata
To determine the parent of the item the following rules apply:
* If the item has a xlink:hasChapter with a book as the source, then the source book of the xlink:hasChapter link is the parent
* If the item has a xlink:hasChapter with a Component group as the source, then the source book of the xlink:hasGrouping of that Component group is the parent 
* If the item has a xlink:hasArticle with an issue as the source, then the source issue of the xlink:hasArticle is the parent 
* If the item has a xlink:hasArticle with a serial as the source, then the source serial of the xlink:hasArticle is the parent 

Keepeek items of type ``Working Paper`` are exported with the title of their parent in their <parentTitle> property. To determine the parent of the item the following rules apply:
* The xlink:hasPaper (reverse link) in Kappa points to the Working Paper Series parent. If the Working Paper is stand-alone, meaning that the series is in a different language, the English series title is exported.

R009 DOI rdf:about 
------------------

DOI rdf:about corresponds to the concatenation of prefix identifier as follows :

+-----------------------+---------------+-------------------------+
|    ItemType           |    Element    |    prefix identifier    |
+=======================+===============+=========================+
|    Book               |               |    book                 |
+-----------------------+---------------+-------------------------+
|    Chapter            |               |    chapter              |
+-----------------------+---------------+-------------------------+
|    Table              |    G          |    graph                |
+-----------------------+---------------+-------------------------+
|                       |    T          |    table                |
+-----------------------+---------------+-------------------------+                         
|    Issue              |               |    issue                |
+-----------------------+---------------+-------------------------+
|    Article            |               |    article              |
+-----------------------+---------------+-------------------------+
|    KeyTableEdition    |    T          |    keytableedition      |
+-----------------------+---------------+-------------------------+
|    Summary            |               |    summary              |
+-----------------------+---------------+-------------------------+
|    WorkingPaper       |               |    workingpaper         |
+-----------------------+---------------+-------------------------+

R010 FTI table/graph export
----------------------------

If a table/graph object (defined as element of a iLibrary Table of contents) in KAPPA in a given format (e.g. XLS) is candidate for export to Free Preview, the same table/graph in all available formats (e.g PDF) must be candidate for export systematically even though it does not meet export criteria, except the export criteria ``Don't send it to iLibrary`` (i.e. systematic candidate for export does not apply when iLibrary export has been expressly blocked for this table/graph (i.e. if it has been flagged ``Don't send it to iLibrary``)). But finally only one FTI is exported: the ebook or the Excel file if no e-book exists for the table/graph object.

.. note:: this rule is based on the R27 iLibrary export rule.

R011 CoverImage
---------------

On Free Preview, the coverImage metadata corresponds to:

+-------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------+
|    item                                                                             |    coverfilename selection rule                                                            |
+=====================================================================================+============================================================================================+
|    book, issue                                                                      |    same as cover filename exported to   iLibrary                                           |
+-------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------+
|    chapter, table, graph, summary                                                   |    cover filename exported to iLibrary for   its parent book/issue                         |
+-------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------+
|    article                                                                          |    cover   filename exported to iLibrary, as defined in the iLibrary export rule R10[m1]   |
+-------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------+
|    book or issue without a cover                                                    |    Igo. coverGeneric                                                                       |
+-------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------+
|    chapter, table, graph, summary belonging   to a book or issue without a cover    |    Igo. coverGeneric                                                                       |
+-------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------+
|    key table edition                                                                |    default cover image (key_tablesm.jpg)                                                   |
+-------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------+
|    working paper                                                                    |    cover image of the parent series                                                        |
+-------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------+


R012 Short description
----------------------

Working papers are exported with a short description corresponding to the first 300 characters of the ``Long description`` field, or less if it is not 300 characters long.


R013 Link to the Online Bookshop
--------------------------------

Component item are exported with the online bookshop link of their full parent, according to the following rule:

+---------------------+--------------------------------------+-----------------------------------------------------------------+
|    Parent   item    |    Child   Item                      |    Online   Bookshop links to                                   |
+=====================+======================================+=================================================================+
|    Book             |    chapter, table, graph, summary    |    Online Bookshop URL of the parent   publication              |
+---------------------+--------------------------------------+-----------------------------------------------------------------+
|    Issue            |    Article, Table                    |    Online Bookshop URL of the parent serial   of type journal   |
+---------------------+--------------------------------------+-----------------------------------------------------------------+

* If the item is a stand-alone chapter and is not linked to any parent, no bookshop link is exported. 
* If the item has a print version with the status ``Published`` and which is exported to the Online Bookshop, the child item is exported to Keepeek with the ``Online Bookshop`` external link of the print version of the published item as defined in the table above
* If the item has no ``Published`` print version exported to the Online Bookshop but has an ebook version which is exported to the Online Bookshop, the child item is exported to iLibrary with the ``Online Bookshop`` external link of ebook version of the published item as defined in the table above
* Otherwise the Online bookshop link is left empty.


R014. Full-text format
-----------------------


+----------------------------------------------------------+------------------------------------+
|    Value   of Free Preview's fulltext.format Property    |    Kappa   property           |
+==========================================================+====================================+
|    application/pdf                                       |    mimetype = 'application/pdf'    |
+----------------------------------------------------------+------------------------------------+
|    Value of file.mimetype                                |    mimetype                        |
+----------------------------------------------------------+------------------------------------+


Appendix
========

Keepeek management rules
------------------------

**1. Loading rules and back office**

* The loading process is triggered daily at 1am, from Tuesday to Saturday.
* If a given metadata is supplied in more than one language, the English version will be used.
* Each item loaded into the back office is deposited in two different folders:
	* a folder corresponding to the theme this item is indexed by, e.g. ``Environment``.
	* a folder named according to the date of import, e.g. ``/2011/04/14``.

**2. Display and access rules**

* The ``alias`` field can be used to access a publication by building its URL.
* Embargo management: if the GMT date and time of display are smaller than the GMT date and time of embargo, the Free Preview of the publication is not publicly accessible.
* if no cover image has been provided, the default ``OECD Publications`` `thumbnail <http://www.oecd-ilibrary.org/content/images/publications_oecdm.jpg>`_ is used.
