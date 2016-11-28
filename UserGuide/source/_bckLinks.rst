Links guidelines and specification 
===================================

Links provide access from one resource to another, and define the relationship between the two. 
They can be internal (links between OECD publications having a record in Kappa) or external (links from OECD publications to websites or resources located outside of Kappa).
Links can be created in different ways:
•	Automatically when an object is created (pyramid links for example)
•	Via the loading of a content XML if de schema allows the definition of the link (member indicators in the XML of an indicator group for example)
•	Manually via the interface (default child of a database for example)
•	Via a functionality of the Kappa application (when archiving a dataset for example)

Most of the links managed in Kappa are bidirectional: if a link is created from object A to object B, the reciprocal link from B to A will be created too (always automatically). 
This automation also applies to the deletion of bidirectional links (if a link from A to B is deleted, the reciprocal link from B to A is deleted).
In kappa V3 all the direct links go from the parent to the child, the reverse links are calculated in the base but will not be created manually by the user.
We have identified six different families of links between objects:
•	Pyramid links
•	Include links 
•	Coproduct links
•	Highlight links
•	Lifecycle links
•	Related links


Pyramid links
--------------

.. image:: images/PyramidLinks.PNG

Other languages and Other versions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

These links were explicited via cross references in Kappa V2 because the model of the old base needed them, but Kappa V3 uses the FRBR model and all these pyramid links become 
implicit for the user. We can can visualise a Kappa V3 object as a pyramid.

* The link between different expressions of the same work gives the ``other languages``. In iLibrary they are displayed after the label ``Also available in``
* The link Link between different manifestations of the same expression gives us the ``other versions``Links to all electronic versions of a publication 
are included on the iLibrary homepage of that publication.

Feepreview and Active chart
~~~~~~~~~~~~~~~~~~~~~~~~~~~
 
Other links which existed in Kappa V2 re now considered as manifestation formats and they also become pyramid links 

* Feepreview Manifestation: 
* Active chart (a JSON manifestation of this table)


Online Bookshop URL
~~~~~~~~~~~~~~~~~~~~

``Online Bookshop URL`` becomes a metadata at manifestation level,used to link to the page of an item on the Online Bookshop. It is visible on iLibrary
via the toolkit on publication / serial homepages: buy this book OR “yearly subscription”



Include links
--------------

Include links establish the relationship between an object and its components, from serial to publication level, but also from book to chapter and chapter to graph.
They are all at Work level.
All the targets of these links are ``included in`` the source so their reverse link is ``is included in`` 
The exception is a link specific for thematic groupings which is ``has member``. Its corresponding reverse link is ``is member of``.

hasIssue
~~~~~~~~~~

Ordered link with the following source

+------------------------+------------+
| Source                 | Souce Type |
+========================+============+
| Journal                | 1201       |
+------------------------+------------+
| Collection             | coll       |
+------------------------+------------+
| Statistical periodical | 1202       |
+------------------------+------------+
| Outlook periodical     | 1203       |
+------------------------+------------+
| Book Periodical        | 1204       |
+------------------------+------------+
| Book Periodical        | 1205       |
+------------------------+------------+

And the following targets

+------------------------+-------------+
| Target                 | Target Type |
+========================+=============+
| Journal                |  1201       |
+------------------------+-------------+

*How this link is shwon in the user interface*

*Label*
Books/ Issues

*Shown on interface*
modal if > 3

*Migration from Kappa V2 or Working Papers database*
using ProductSubscription (Xref = 250) 
using ProductSubscription (Xref = 350)


hasChapter
~~~~~~~~~~~

*Ordered*

*Source*
book

*Source Type*
publ

*Target*
Chapter

*Target Type*
1401

*How this link is shwon in the user interface*

Chapters


*Migration from Kappa V2 or Working Papers database*
Xref Chapter (11)


hasArticle
~~~~~~~~~~~~
*Ordered*

*Source*
Journal and Journal Issue

*Source Type*
1201, 1304

*Target*
article

*Target Type*
1505

*How this link is shwon in the user interface*


Articles

*Migration from Kappa V2 or Working Papers database*

hasPaper
~~~~~~~~~~

*Ordered*

*Source*
Working Paper Series


*Source Type*

*Target*

*Target Type*

*How this link is shwon in the user interface*

*Migration from Kappa V2 or Working Papers database*


hasTable
~~~~~~~~~~~~

*Ordered*

*Source*
Working Paper Series


*Source Type*

*Target*

*Target Type*

*How this link is shwon in the user interface*

*Migration from Kappa V2 or Working Papers database*



hasGraph
~~~~~~~~~~~~

*Ordered*

*Source*
Working Paper Series


*Source Type*

*Target*

*Target Type*

*How this link is shwon in the user interface*

*Migration from Kappa V2 or Working Papers database*


hasData
~~~~~~~~~~~~
*Ordered*

*Source*
Working Paper Series


*Source Type*

*Target*

*Target Type*

*How this link is shwon in the user interface*

*Migration from Kappa V2 or Working Papers database*


hasGrouping
~~~~~~~~~~~~
*Ordered*

*Source*
Working Paper Series


*Source Type*

*Target*

*Target Type*

*How this link is shwon in the user interface*

*Migration from Kappa V2 or Working Papers database*


hasMember
~~~~~~~~~~~~
*Ordered*

*Source*
Working Paper Series


*Source Type*

*Target*

*Target Type*

*How this link is shwon in the user interface*

*Migration from Kappa V2 or Working Papers database*


+-------------+---------+-----------------------------+-------------+--------------------+-------------+---------------+---------------+-------------+------------------------------------+
| Link        | Ordered | Source                      | Source Type | Target             | Target Type | Label         | Reverse Label | Shown on    | V2 or WP Migration                 |
|             |         |                             |             |                    |             |               |               |   interface |                                    |
+=============+=========+=============================+=============+====================+=============+===============+===============+=============+====================================+
| hasIssue    | yes     | Journal                     | 1201        | Book               | publ        | Issue/Book    | included in   | modal       |                                    |
|             |         | Collection                  | coll        |                    |             |               |               |   if > 3    | ProductSubscription (Xref = 250)   |
|             |         | Statistical periodical      | 1202        |                    |             |               |               |             | ProductSubscription (Xref = 350)   |
|             |         | Outlook periodical          | 1203        |                    |             |               |               |             |                                    |
|             |         | Book Periodical             | 1204        |                    |             |               |               |             |                                    |
|             |         | Economic Surveys Periodical | 1205        |                    |             |               |               |             |                                    |
+-------------+---------+-----------------------------+-------------+--------------------+-------------+---------------+---------------+-------------+------------------------------------+
| hasChapter  | yes     | Book                        | publ        | Chapter            | 1401        | Chapters      | included in   | yes         | Xref Chapter (11)                  |
|             |         |                             |             |                    |             |               |               |             |                                    |
+-------------+---------+-----------------------------+-------------+--------------------+-------------+---------------+---------------+-------------+------------------------------------+
| hasArticle  | yes     | Journal                     | 1201        | Article            | 1505        | Articles      | included in   | yes         | ProductSubscription (Xref= 150)    |
|             |         | Journal Issue               | 1304        |                    |             |               |               |             |                              |
+-------------+---------+-----------------------------+-------------+--------------------+-------------+---------------+---------------+-------------+------------------------------------+
| hasPaper    | yes     | Working Paper Series        | 1104        | Working paper      | 1502        | Working Papers| included in   | yes         | document to series via seriesId    |
+-------------+---------+-----------------------------+-------------+--------------------+-------------+---------------+---------------+-------------+------------------------------------+
| hasTable    | yes     | Key table                   |             | Table,             |             | Table         | included in   | yes         | Xref Table (17)                    |
|             |         | Book                        |             | Keytable edition   |             |               |               |             |                                    |
|             |         | Component                   |             |                    |             |               |               |             |                                    |
|             |         | Paper                       |             |                    |             |               |               |             |                                    |
|             |         | Brief                       |             |                    |             |               |               |             |                                    |
+-------------+---------+-----------------------------+-------------+--------------------+-------------+---------------+---------------+-------------+------------------------------------+
| hasGraph    | yes     | Book                        |             | Graph              |             | Graph         | included in   | yes         | Xref Graph (18)                    |
|             |         | Component                   |             |                    |             |               |               |             |                                    |
|             |         | Paper                       |             |                    |             |               |               |             |                                    |
|             |         | Brief                       |             |                    |             |               |               |             |                                    |
+-------------+---------+-----------------------------+-------------+--------------------+-------------+---------------+---------------+-------------+------------------------------------+
| hasData     | yes     | Database                    | 1105        | Dataset            | 1601,       | Data          | included in   | yes         | Already migrated                   |
|             |         | Dataset group               | 1004        |                    | 1604        |               |               |             |                                    |
+-------------+---------+-----------------------------+-------------+--------------------+-------------+---------------+---------------+-------------+------------------------------------+
| hasGrouping | yes     | Any object                  |             | thematic grouping  | thgr        | Grouping      | included in   | yes         | Already migrated                   |
|             |         |                             |             |                    |             |               |               |             |                                    |
+-------------+---------+-----------------------------+-------------+--------------------+-------------+---------------+---------------+-------------+------------------------------------+
| hasMember   | yes     | Thematic grouping           | thgr        | any object         |             | Members       | member of     | yes         | Only in V3                         |
|             |         |                             |             |                    |             |               |               |             |                                    |
+-------------+---------+-----------------------------+-------------+--------------------+-------------+---------------+---------------+-------------+------------------------------------+


Coproduct links
---------------------

The coproduct links connect Kappa Objects to products which use the same or similar content. They are not included, but have their own existence.
For the moment we have identified three different coproducts:
* Briefs: like Policy Briefs or statistical briefs. They take the content from one or several publication and condensate it with a short analysis
* Multilingual summaries: translations in several languages of the executive summary of a publication (sometimes this contet may have been revised and will not correspond exactly to the executive summary)
* Dataset Archives : frozen csv versions of a dataset or a previous online version of a current edition dataset

+------------+---------+------------------+-------------+-----------------+-------------+-----------+---------------+--------------+------------------------+
| Link       | Ordered | Source           | Source Type | Target          | Target Type | Label     | Reverse Label | Shown on     | V2 or WP Migration     |
|            |         |                  |             |                 |             |           |               |   interface  |                        |
+============+=========+==================+=============+=================+=============+===========+===============+==============+========================+
| hasArchive | yes     | Dataset updating | 1601        | dataset archive | 1605        | Archives  | is archive of | modal if > 3 | Only in V3             |
|            |         | Dataset edition  | 1604        |                 |             |           |               |              |                        |
+------------+---------+------------------+-------------+-----------------+-------------+-----------+---------------+--------------+------------------------+
| hasBrief   | yes     | Book             | publ        | brief           | 1503        | Briefs    | is brief of   | yes          | Xref ``Policy Brief`` (4)|
|            |         | Component        | comp        |                 |             |           |               |              |                        |
|            |         | Paper            | pape        |                 |             |           |               |              |                        |
+------------+---------+------------------+-------------+-----------------+-------------+-----------+---------------+--------------+------------------------+
| hasSummary | no      | Book             | publ        | Summary         | 1402        | Summaries | is summary of | yes          | No longer in V2        |
|            |         | Component        | comp        |                 |             |           |               |              |                        |
|            |         | Paper            | pape        |                 |             |           |               |              |                        |
|            |         | Brief            |             |                 |             |           |               |              |                        |
+------------+---------+------------------+-------------+-----------------+-------------+-----------+---------------+--------------+------------------------+

Highlight links
-------------------

Default child: Some databases and dataset groups have multiple children (datasets or dataset groups). This link is used to indicate which of these children is the default one, and should be displayed by default.
A default child link can only be created towards a dataset or dataset group which is already included in the database/dataset group.

Main Parent
Some datasets can have multiple parent databases or dataset groups, and similarly, some dataset groups may have multiple parent databases.  

This link is used to indicate which of these parents is the main one, and should be given priority for iLibrary display. 
A link from a dataset to a database can only be made if the dataset is included in the database.
A link from a dataset to a dataset group can only be made if the dataset is a member of the dataset group


+--------------+---------+-----------------+-------------+-----------------+-------------+---------------+---------------+-------------+--------------------+
| Link         | Ordered | Source          | Source Type | Target          | Target Type | Label         | Reverse Label | Shown on    | V2 or WP Migration |
|              |         |                 |             |                 |             |               |               |   interface |                    |
+==============+=========+=================+=============+=================+=============+===============+===============+=============+====================+
| defaultChild | no      | Database        | 1105        | dataset         | 1601        | Default Child |    NA         | no          | Already migrated   |
|              |         | Dataset group   | 1004        | dataset group   | 1604        |               |               |             |                    |
|              |         |                 |             |                 | 1004        |               |               |             |                    |
+--------------+---------+-----------------+-------------+-----------------+-------------+---------------+---------------+-------------+--------------------+
| mainParent   | no      | Dataset         | 1601        | database        | 1105        | Main Parent   |    NA         | no          | Already migrated   |
|              |         | Dataset group   | 1604        | dataset group   | 1004        |               |               |             |                    |
|              |         | Dataset archive | 1004        |                 |             |               |               |             |                    |
|              |         |                 | 1605        |                 |             |               |               |             |                    |
+--------------+---------+-----------------+-------------+-----------------+-------------+---------------+---------------+-------------+--------------------+


Lifecycle links
----------------

They are at expression Level because they might be different for two language versions of the same work.

Continues: Used when a serial has been discontinued because of a change in title, and is continued by another serial under a new title.
A serial can be continued by one or more serials. A serial can continue one or more serials.
If a serial is continued by more than one title, this case is referred to as a split. If a serial continues more than one title, this case is referred to as a merge.
For datasets, a link to the old dataset is shown on iLibrary EXPORT RULE AND TEMPLATE RULE	Continues	Discontinued Continued by
continues

Replaces: Identifies the new edition of a publication which has been replaced by a more recent edition in the same language and format.  It is used with the reciprocal link Replaces.
Used to identify the previous edition of a publication which is replacing all earlier editions in the same language. It is used with the reciprocal link Replaced by
For datasets, no link to the replaced dataset is shown. EXPORT RULE AND TEMPLATE RULE	Replaced by/ Replaces	Items having a *replaced by* link to another publication have 
no full-text item on their iLibrary homepage. This full-text item may exists in KAPPA but it won’t be displayed on iLibrary: A Replaced by link brings the user to the current edition’s 
homepage, for which a full text item is available

+-----------+---------+-------------------+------------------+--------------------+------------------+-----------+----------------+-------------+-----------------------+
| Link      | Ordered | Source            | Source Type      | Target             | Target Type      | Label     | Reverse Label  | Shown on    | V2 or WP Migration    |
|           |         |                   |                  |                    |                  |           |                |   interface |                       |
+===========+=========+===================+==================+====================+==================+===========+================+=============+=======================+
| replaces  | no      | Collection        | coll             | Collection         | coll             | Replaces  | is replaced by | yes         | Xref ``Replaces`` (51)  |
|           |         | Periodical        | peri             | Periodical         | peri             |           |                |             |                       |
|           |         | Thematic grouping | thgr             | Thematic grouping  | thgr             |           |                |             |                       |
|           |         | Book              | publ             | Book               | publ             |           |                |             |                       |
|           |         | Dataset           | 1601, 1604, 1605 | Dataset            | 1601, 1604, 1605 |           |                |             |                       |
+-----------+---------+-------------------+------------------+--------------------+------------------+-----------+----------------+-------------+-----------------------+
| continues | no      | Collection        | coll             | Collection         | coll             | Continues | is continued by| yes         | Xref ``Continues`` (16) |
|           |         | Periodical        | peri             | Periodical         | peri             |           |                |             |                       |
|           |         | Thematic grouping | 1601, 1604, 1605 | Thematic grouping  | 1601, 1604, 1605 |           |                |             |                       |
|           |         | Dataset           |                  | Dataset            |                  |           |                |             |                       |
+-----------+---------+-------------------+------------------+--------------------+------------------+-----------+----------------+-------------+-----------------------+


Related links 
---------------

Related Database	Used to link a statistical periodical to its corresponding database (i.e. statistical collection or stand-alone dataset).
It is the reciprocal link of *related database*. It is generated automatically from item B to item A if a *related database* link has been created from item A to item B.
	Related Database Related Periodical
	Other versions: database
Related Titles
Related Websites	A type of *further reading* link from items in the OECD publications catalogue to external sources (i.e. outside of KAPPA) of related content.
It should be used to link to working papers on a related theme, or to external websites of interest.	Related Websites	For display purposes on the iLibrary, both internal (Further reading) and external (Related websites) related links are presented by clicking on the drop down arrow for Related titles. Further reading links are displayed first in alphabetical order and are followed by Related websites links also displayed in alphabetical order:

relatedPeriodical
relatedPublication
relatedIndicator
	The Further Reading link should be assigned based on the content of the publication. It should be used to link to other material covering the same topic and allow the iLibrary user to discover by navigating titles in his area of interest which he might not have found through his initial search query.This link should in priority be used to link items of the same language and in the same medium version. However, if this is not possible in a given case, the link can be used in more flexible ways. Note that the Further reading link should not be applied in the following cases:
The Further reading link should not be used between two publications which have already been linked by an automatic link. 
The Further Reading link should not be used to link two items which are already linked by one of the following intellectual links:
- has source or method
- is source or method of
- related database
- related periodical

For statistical serials (statistical collections and key table collections), the Further reading links should not be used to link to other statistical serials sharing the same theme. 

For instance, links from Statistical collection to Key Tables in the same theme are dynamically generated on iLibrary and appear under the label *Key Tables on*.  Similarly, Key Table Collections linking to a Statistical Collection sharing the same theme are dynamically generated and displayed under the lable *Interactive databases*.

The Further Reading link should only be used to link to an internal resource (ie an item within KAPPA). The equivalent external link is *Related Website*.	Further Reading	

+--------------------+-------+---------+----------------+-------------+-------------------------------+-------------+------------+-----------------+-------------------------+-------------+-----------------------------------------+
| Link               | Level | Ordered | Source         | Source Type | Target                        | Target Type | resolution | Label           | Reverse Label           | Shown on    | V2 or WP Migration                      |
|                    |       |         |                |             |                               |             |   method   |                 |                         |   interface |                                         |
+====================+=======+=========+================+=============+===============================+=============+============+=================+=========================+=============+=========================================+
| relatedIndicator   | W     | yes     | any            |             | Indicator                     | 1603        | code       | Related         | is Related              | yes         | Only in V3                              |
|                    |       |         |                |             |                               |             |            |   Indicators    |   indicator Of          |             |                                         |
+--------------------+-------+---------+----------------+-------------+-------------------------------+-------------+------------+-----------------+-------------------------+-------------+-----------------------------------------+
| relatedWebsite     | E     | yes     | any            |             | url (not mandatory) and label |             | external   | Related Website |                         | no          | RelationInternal ``Related               |
|                    |       |         |                |             |                               |             |            |                 |                         |             |   Website`` (20)                         |
+--------------------+-------+---------+----------------+-------------+-------------------------------+-------------+------------+-----------------+-------------------------+-------------+-----------------------------------------+
| relatedPeriodical  | E     | yes     | Database       | 1105        | Collection                    | coll        |            | Related         | Related                 | yes         | Xref ``Related                           |
|                    |       |         |                |             | Periodical                    | peri        |            |   Periodical    |   database              |             |   Periodical`` (22)                      |
|                    |       |         |                |             | Thematic grouping             | thgr        |            |                 |                         |             |                                         |
+--------------------+-------+---------+----------------+-------------+-------------------------------+-------------+------------+-----------------+-------------------------+-------------+-----------------------------------------+
| relatedPublication | E     | yes     | any            |             | any KV3 object                |             |            | Related         | is                      | yes         | Further reading Xref                    |
|                    |       |         |                |             |                               |             |            |   Publications  |   Related to            |             |                                         |
+--------------------+-------+---------+----------------+-------------+-------------------------------+-------------+------------+-----------------+-------------------------+-------------+-----------------------------------------+
| dataSource         | E     | yes     | any            |             | Dataset                       | 1601, 1604  | external,  | Data            | is                      | yes         | Xref ``Data source`` (19)                 |
|                    |       |         |                |             | Datset group                  | 1001        | doi        |   Source        |   data Source Of        |             | RelationInternal ``Data Source`` (10)     |
|                    |       |         |                |             | Database                      | 1105        |            |                 |                         |             |                                         |
+--------------------+-------+---------+----------------+-------------+-------------------------------+-------------+------------+-----------------+-------------------------+-------------+-----------------------------------------+
| latestPublication  | E     | no      | Indicator Group| 1001        | Collection                    | coll        | doi        | Latest          | is                      | yes         | Indicator specific, not in V2           |
|                    |       |         |                |             | Periodical                    | peri        |            |   Publication   |   latest publication of |             |                                         |
|                    |       |         |                |             | Thematic grouping             | thgr        |            |                 |                         |             |                                         |
+--------------------+-------+---------+----------------+-------------+-------------------------------+-------------+------------+-----------------+-------------------------+-------------+-----------------------------------------+