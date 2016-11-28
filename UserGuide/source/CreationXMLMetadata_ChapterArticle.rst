Creation of Chapters and articles with metadata XML
========================================================

Chapters and articles are contained in the parent book XML and will be extracted and created at the same time.

It is neertheless possible to load the book without chapters, and then add the chapters (or articles) at a later stage.

It is very important that when loaded via XML, all language versions have the same amount/ order of chapters, so the application can link together chapters which are different language versions (expressions)
of the same chapter work.

Business rules:
------------------

**RULE1** : The link between two chapters expression of the same work
will be done in the order of the xml. This means that is a publication
in EN has two chapters 1,2, and a French version is loaded, then chapter
1FR will be the French expression of chapter1, chapter 2FR will be the
French expression of chapter2. It is up to the user to verify that this
is actually true, because the application cannot determine it
automatically.

**RULE2** : The link between two sections expression of the same work
will be done in the order of the xml. This means that is a publication
in EN has two sections 1,2, and a French version is loaded, then section
1FR will be the French expression of section1, section 2FR will be the
French expression of section2. It is up to the user to verify that this
is actually true, because the application cannot determine it
automatically.

• The number of chapters and sections needs to be the same in all
language versions

• The ordered sequence of sections/chapters must be the same in all
language versions If it not the same, then a message appears at loading
and the object is not created (the sequence of components needs to be 
identical in all language versions and it is not, please revise the table
of contents comparing it to existing language version)

**RULE**: The order of chapters and sections will not be editable in
kappa, to avoid creating discrepancies in the table of contents of a
book. For the moment if a user wants to change the order of the
chapters, then he/she will need to reload the XML in all the languages.


Reloading an xml for existing records
-------------------------------------

The metadata needed for export as DOI and DOI title is preserved. All
the other metadata and links at the three levels are erased and
recreated (WARNING: All metadata for this book and its components will 
be recreated, and FTIs erased. are you sure you want to proceed?)

The control on chapter/section number and sequence is run again. If the
number/sequence does not correspond, then the loading stops (The sequence
of components needs to be identical in all language versions and it is not,
please revise the table of contents comparing it to existing language version)


Metadata mapping
-------------------


+--------------+--------------+-------+-------------------------------------------+
| KV3 Metadata | Xml field    | Level | Rules and Comments                        |
+==============+==============+=======+===========================================+
| Title        | Title        | W     | In the first language of the master       |
|              |              |       | version                                   |
+--------------+--------------+-------+-------------------------------------------+
| Subtitle     | Subtitle     | W     | In the first language of the master       |
|              |              |       | version                                   |
+--------------+--------------+-------+-------------------------------------------+
| Form         | naturefInfor | W     | Taxonmy Form                              |
|              | mation       |       |                                           |
+--------------+--------------+-------+-------------------------------------------+
| componentCon | componentCon | W     | componenttype                             |
| tentType     | tentType     |       |                                           |
+--------------+--------------+-------+-------------------------------------------+
| Author       | Author       | W     | RULE: In the absence of a chapter         |
|              |              |       | AuthorID, the chapter should inherit the  |
|              |              |       | book AuthorID                             |
+--------------+--------------+-------+-------------------------------------------+
| Maintheme,   | Theme        | W     | the chapter should inherit the book       |
| otherThemes  |              |       | Themes                                    |
+--------------+--------------+-------+-------------------------------------------+
| Country      | Country      | W     |                                           |
+--------------+--------------+-------+-------------------------------------------+
| Region       | Region       | W     |                                           |
+--------------+--------------+-------+-------------------------------------------+
| Time Range   | timeRange    | W     |                                           |
+--------------+--------------+-------+-------------------------------------------+
| Language     | language     | E     | List of languagesof the expression        |
+--------------+--------------+-------+-------------------------------------------+
| Abstract     | Abstract     | E     |                                           |
+--------------+--------------+-------+-------------------------------------------+
| Filename     | Filename     | M     |                                           |
+--------------+--------------+-------+-------------------------------------------+
| startPage    | startPage    | M     |                                           |
+--------------+--------------+-------+-------------------------------------------+
| endPage      | endPage      | M     |                                           |
+--------------+--------------+-------+-------------------------------------------+
| publisherID  | NA           | M     | RULE: The chapter should inherit the book |
|              |              |       | publisherID                               |
+--------------+--------------+-------+-------------------------------------------+
| publicationD | NA           | M     | RULE: The chapter should inherit the book |
| ate          |              |       | publicationDate                           |
+--------------+--------------+-------+-------------------------------------------+



+-------------+-----------+---------+---------------------------------------------+
| KV3         | Xml field | Level   | Rules and Comments                          |
| Metadata    |           |         |                                             |
+=============+===========+=========+=============================================+
| Title       | Title     | W-E     | The title in the language of the master     |
|             |           |         | version is used in the work.                |
+-------------+-----------+---------+---------------------------------------------+
| Language    | Language  | E       |                                             |
+-------------+-----------+---------+---------------------------------------------+



   

