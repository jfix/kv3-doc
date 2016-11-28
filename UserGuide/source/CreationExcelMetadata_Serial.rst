Serials (Excel)
===============

In this document we use the generic word ``serial`` to define
``collection`` and ``periodical`` work types in Kappa.

All the metadata necessary to create the serial pyramid is given by the
supplier in an excel file made of three tabs, each one corresponding to
one catalogue type (``book series``, ``periodical``, ``journal``).

The three types are:

+---------------+----------------------+-------------------+
| TAB           | WORK TYPE IN KAPPA   | CATALOGUE TYPE    |
+===============+======================+===================+
| Book series   | Collection           | Book series       |
+---------------+----------------------+-------------------+
| Periodicals   | Periodical           | Book periodical   |
+---------------+----------------------+-------------------+
| Journal       | Periodical           | Journal           |
+---------------+----------------------+-------------------+

Each line of the excel file contains the metadata of one serial in one
language, i.e. each line corresponds to one expression of the serial.

Master Language
---------------

For OECD publications the convention is to use metadata in English to
create the work. Some UN publications do not exist in English, so we
need to introduce the concept of ``Master Language`` (=language of the
metadata which generates the work).

*Cataloguing guideline* : Whenever English exists, it is the
``Master Language``

Rules on how to identify Work, Expression and Manifestation
-----------------------------------------------------------

1. The metadata of the master language version is used for the creation
   of the work. We identify the master version of the publication
   because the column ``is translation of`` is empty. Therefore:

-  if a line does not have ``is translation of``, it will generate the
   work, expression and manifestation.
-  Otherwise the line will generate an expression (+ manifestation).

2. If the master version is multilingual, then the title chosen for the
   work is the title in the first language declared.

3. The link between expressions of the same work is made in the column
   ``Is translation of`` through the ISSN of the ``master language``.

4. The link between manifestations of the same expression is made in the
   column ``other media`` through the ISSN of PDF version in the
   ``master language``.

Metadata Mapping
----------------

Work
~~~~

This table indicates how to map the columns in the Excel file to the
work metadata fields in kappa and the default values to be applied.

+-------------+-------+-----------------------+-----------------------------------+
| Kappa       | Manda | Excel column          | Rules, Default values and         |
| metadata    | tory  |                       | comments                          |
+=============+=======+=======================+===================================+
| Author      | Y     | AuthorID 1, AuthorID  |                                   |
|             |       | 2… AuthorID n         |                                   |
+-------------+-------+-----------------------+-----------------------------------+
| otherTheme  | N     | IGO Main theme 2, …   |                                   |
|             |       | IGO Main theme n      |                                   |
+-------------+-------+-----------------------+-----------------------------------+
| Country     | N     | Country               |                                   |
+-------------+-------+-----------------------+-----------------------------------+
| Igo         | Y     | IGO                   |                                   |
+-------------+-------+-----------------------+-----------------------------------+
| Form        | N     | Nature of Information |                                   |
+-------------+-------+-----------------------+-----------------------------------+
| mainTheme   | Y     | IGO Main theme 1      |                                   |
+-------------+-------+-----------------------+-----------------------------------+
| objectType  | Y     | tab name              | Depending on the TAB: Collection  |
|             |       |                       | or periodical                     |
+-------------+-------+-----------------------+-----------------------------------+
| catalogueTy | Y     | tab name              | Depending on the TAB: Book        |
| pe          |       |                       | series, Periodical Books or       |
|             |       |                       | Journals                          |
+-------------+-------+-----------------------+-----------------------------------+
| Region      | N     | Region                |                                   |
+-------------+-------+-----------------------+-----------------------------------+
| Title       | Y     | Master Main Title 1   |                                   |
+-------------+-------+-----------------------+-----------------------------------+
| Periodicity | Y     | Periodicity           | For periodicals and journal only  |
+-------------+-------+-----------------------+-----------------------------------+

Hard coded values: \* Directorate = NA

Expression
~~~~~~~~~~

This table indicates how to map the columns in the Excel file to the
expression metadata fields in kappa.

+-------------+-------+----------------------+------------------------------------+
| Kappa       | Manda | Excel column         | Rules and comments                 |
| metadata    | tory  |                      |                                    |
+=============+=======+======================+====================================+
| workId      | N     | workId               | Use to specify a partial language  |
|             |       |                      | loading (when the Work already     |
|             |       |                      | exists)                            |
+-------------+-------+----------------------+------------------------------------+
| doiSuffix   | N     | DOI                  | The prefix should NOT be included  |
|             |       |                      | in this column                     |
+-------------+-------+----------------------+------------------------------------+
| Language    | Y     | Master Language 1    | Can be multiple                    |
|             |       | Language n           |                                    |
+-------------+-------+----------------------+------------------------------------+
| Title       | Y     | Master Main Title 1  | Each title should be associated    |
|             |       | ... Main Title n     | with its language                  |
+-------------+-------+----------------------+------------------------------------+
| Abstract    | N     | Master Marketing     | Each abstract should be associated |
|             |       | blurb 1              | with its language attribute        |
+-------------+-------+----------------------+------------------------------------+
| Issnl       | Y     | ISSN-L               | Copy value of ISSN by default      |
+-------------+-------+----------------------+------------------------------------+

Hard coded values: \* iLibraryAccessType = 3 (Under access control) \*
user = fordec to "Automate" (mais pourquoiiiiii ???) \* usercode = uc-
\* NOTE on doiPrefix: the value of this is NOT the result of the
extraction, but a business logic rule implemented in KV3, which compute
the prefix based on the work's IGO

Manifestation
~~~~~~~~~~~~~

This table indicates how to map the columns in the Excel file to the
manifestation metadata fields in kappa.

+------------------+-------------+-------------------------+----------------------+
| Kappa metadata   | Mandatory   | Excel column            | Rules and comments   |
+==================+=============+=========================+======================+
| Title            | Y           | Master Main Title 1     |                      |
+------------------+-------------+-------------------------+----------------------+
| Availability     | Y           | availability            |                      |
+------------------+-------------+-------------------------+----------------------+
| Medium           | Y           | Medium (ou ID Medium)   |                      |
+------------------+-------------+-------------------------+----------------------+
| Issn             | Y           | ISSN                    |                      |
+------------------+-------------+-------------------------+----------------------+

Hard coded values: \* isISSNL = set to YES if ISSN = ISSN-L, NO
otherwise \* Publisher: forced to "organization:5595" (ITU) at the
moment
