Export Rules
============

As catalogue types are fully migrated to Kappa and export rules implemented and validated in that system, further rules
will be added to this page.
For other rules and exports currently made from Kappa V2, please also see the corresponding `iLibrary export
documentation <https://pacps01.oecd.org/redmine/projects/ilibraryexportdoc/documents>`_

R1 FTI and Metadata Export
--------------------------

All full-text items (``PDF``, ``ePUB``, ``XLS``, etc.) and its metadata belonging to a Kappa item must be exported at the same time
to ensure the full-text items file-sizes are created.

R006 Short Title
----------------

The following catalogue types are exported with a short title:
* ``Indicator Group``
* ``Indicator``
* ``Database``
* ``Book Periodical``
* ``Economic Survey Periodical``
* ``Journal``
* ``Outlook Periodical``
* ``Statistical Periodical``
* ``Book series``
* ``Country studies series``
* ``Working paper series``

If no value has been entered in the shortTitle field, the serial will be exported with a short title equal to its main title.

R007 Translations
-----------------

A published item may exist in several language versions (expressions). Each language version is exported with references to any
other language versions that is eligible for export

R9.1 Working paper - Paper number
---------------------------------

When a working paper has a [number] in Kappa, the exported metadata ``paper number`` corresponds to the ``number``.

R9.2 Working paper - Year number
--------------------------------

When a working paper has no [number], the exported metadata ``Year number`` corresponds to the concatenation of ``volume`` and ``issue``,
as follows: ``volume``/``issue``, e.g. 2009/02.

R10 Cover thumbnails of published items
---------------------------------------

For the following items a cover thumbnail must be sent according to the defined rules:
* Working Paper:  The cover thumbnail should correspond to that of the Working Paper series. Stand-alone working papers are exported with
the generic cover thumbnail for stand-alone working papers.

R11 Year of Publication
-----------------------

For any published item, the year of publication property (``oecd:yearOfPublication``) should correspond to the year portion of
the ``dateOfPublication`` metadata.

R22 Short Description
---------------------

A Short Description should always be supplied for the iLibrary. If a ``shortAbstract`` is not available, then it should be supplied to
the iLibrary based on the first 255 characters of the ``description``.

R24 Affiliations
----------------

Author and Editor affiliations are not exported to the iLibrary, with the exception of Working Papers where author affiliation is indeed exported.

R34 Publisher and publisher city
--------------------------------

The Publisher property in the iLibrary export includes two metadata, a title and an acronym (in English and French) which are mandatory for export.
The ``title`` to be exported corresponds to the organisation long name ([prefLabel] in the organisation taxonomy) in English and French.
The ``acronym`` to be exported should correspond to the organisation short name ([label type="acronym"] in the organisation taxonomy)
in English and French, when it exists. Otherwise it should repeat the publisher long name.
The following catalogue types are exported with this property:

* Indicator Group
* Indicator
* Database
* Book Periodical
* Economic Survey Periodical
* Journal
* Outlook Periodical
* Statistical Periodical
* Book series
* Country studies series
* Working Paper Series
* Working Paper

Kappa items having for publisher: "OECD Publishing / �ditions OCDE" are currently exported with the value 'Paris' as publisher city (oecd:city).

R43 Embargo Date / Publication Date
-----------------------------------

The embargo and publication dates to be exported to iLibrary depend on the value date which is further in the future, i.e. most restrictive)
according to the following rules:

+----------------------------------+----------------------------------+-------------------------+--------------------+
| Kappa fields and values     |                                  | iLibrary export values  |                    |
+==================================+==================================+=========================+====================+
| ``embargoDate``                  | ``dateOfPublication``            |``prism:publicationDate``|``oecd:embargoDate``|
+----------------------------------+----------------------------------+-------------------------+--------------------+
| No Embargo Date                  | Publication Date                 | Publication Date        | Not exported       |
+----------------------------------+----------------------------------+-------------------------+--------------------+
| Embargo Date<=Publication Date   | Embargo Date<= Publication Date  | Publication Date        | Publication Date   |
+----------------------------------+----------------------------------+-------------------------+--------------------+
| Embargo Date > Publication Date  | Publication Date < Embargo Date  | Embargo Date            | Embargo Date       |
+----------------------------------+----------------------------------+-------------------------+--------------------+
| Embargo Date                     | No Publication Date              | Item not exported       | Item not exported  |
+----------------------------------+----------------------------------+-------------------------+--------------------+



R45 Parent identification for Stand-alone Working paper
---------------------------------------------------------------------------

A Kappa item of catalogue type ``Working Paper`` whose parent is a ``Working paper series`` in a different language is considered to
be a stand-alone working paper. Stand-alone working papers must not be exported with serial information (no ``isPartOf`` relationship
is to be included in the export to iLibrary).

R47 Serial start year / end year
--------------------------------

Kappa items of the following catalogue types are exported with an oecd:startYear and oecd:endYear:

* Indicator Group
* Indicator
* Database
* Book Periodical
* Economic Survey Periodical
* Journal
* Outlook Periodical
* Statistical Periodical
* Book series
* Country studies series
* Working Paper series

*Start year*

For Kappa items of catalogue type Working Paper series:
* the lowest ``dateOfPublication`` (year portion only) among Working Papers of the series

*End year*

The end year is sent for discontinued serials only, and it corresponds to:

* for Kappa items of catalogue type �Working Paper series�:
	* the highest [dateOfPublication] (year portion only) among Working Papers of the series


R53 View URL
============

``viewURL`` is exported to iLibrary for all Kappa items which are exported to the iLibrary viewer. The property has 2 values, one
for each interface:

* for the English interface, ``viewURL`` will be the URL alias stored in Kappa for this item, preceded by a forward slash "/"; e.g.
"/education/human-capital_9789264029095-en"
* for the French interface, ``viewURL`` will be the URL alias stored in Kappa for this item, preceded by a forward slash "/" and the
character string "fr/"; e.g. "/fr/education/human-capital_9789264029095-en"

R55 Dimensions
--------------

The file format (dimensions of the document) is exported to iLibrary for all'Kappa items where a value has been entered in the ``pagesize`` field.

R70 Free Preview full-text item
-------------------------------

A preview full-text item is exported to iLibrary for all Kappa items which are exported to the iLibrary viewer. The value of this full-text
item will be a link to the Keepeek page where the object�s Free Preview is available.
This property is set only if item is eligible for the freepreview channel.

R107 IGO Themes
---------------

Themes should apply to all item types and are exported for the following IGOs only:

*	OECD
*	UNP

IGOs are identified by the IGO property.


R109 ISSN/eISSN
---------------

The ``prism:issn`` property is set to the item�s issn from the manifestation of the print format:

* PDF manifestation first
* If no PDF format exist, use EPUB
* If no EPUB format exist, use Webbook

R110 Imprint for IGO
--------------------

For the following IGO the imprint property should always be exported corresponding to the imprints.xml (id�s below).


+-----------------------------+------------------------------------+
| IGO                         | Imprint                            |
+=============================+====================================+
| Commonwealth                | <imprint rdf:about ="imprint/15"/> |
+-----------------------------+------------------------------------+
| Nordic Council of Ministers | <imprint rdf:about="imprint/16">   |
+-----------------------------+------------------------------------+
| UNP                         | <imprint rdf:about="imprint/17">   |
+-----------------------------+------------------------------------+
| ITU                         | <imprint rdf:about="imprint/18">   |
+-----------------------------+------------------------------------+

R117 Metadata in multiple languages
-----------------------------------

Metadata can exist at the expression level in Kappa one or several languages. If so, metadata in all the languages should be exported.
