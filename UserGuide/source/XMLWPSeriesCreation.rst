How to create a Working paper series using a metadata XML
==========================================================

To create a working paper with an XML file you can proceed as follows :

From the Home page via the ``Create using files button``

.. image:: images/CreatUsingFiles.JPG

then select and batch load the metadata XMLs

.. image:: images/XMLWPSelect.JPG


You will see a confirmation message with the links to the records you have created

Click on the link and go to the series detailed page :

.. image:: images/missingISSN.JPG

If you need to add a thumbnail for this series, you will see a button at expression level which allows you to load the image

.. image:: images/addThumbnail.JPG


When you attach the first working paper to the series, go to the same place (Action -->Edit at manifestation level) change the status to ``published`` and add a publication date


XML Schema and mapping
------------------------

The Working paper series XML must follow the rules of the loading.xsd schema (see :doc:`CreateUsingFiles`)

Here are the main metadata present in the schema and the mapping towards Kappa levels of the pyramid.

+-------------------------+-------+------+-----------------------+
| XML element             | Level | Card | Kappa XML metadata    |
+=========================+=======+======+=======================+
| author                  | W     | 1-n  | author                |
+-------------------------+-------+------+-----------------------+
| country                 | W     | 0-n  | country               |
+-------------------------+-------+------+-----------------------+
| editor                  | W     | 0-n  | editor                |
+-------------------------+-------+------+-----------------------+
| igo                     | W     | 1    | igo                   |
+-------------------------+-------+------+-----------------------+
| isTranslationOf         | W     | 1    | link to existing work |     
+-------------------------+-------+------+-----------------------+
| nature of information   | W     | 0-n  | nature of information |
+-------------------------+-------+------+-----------------------+
| periodicity             | W     | 0-1  | periodicity           |
+-------------------------+-------+------+-----------------------+
| region                  | W     | 0-n  | region                |
+-------------------------+-------+------+-----------------------+
| theme                   | W     | 1-n  | theme                 |
+-------------------------+-------+------+-----------------------+
| abstract                | E     | 0-1  | abstract              |
+-------------------------+-------+------+-----------------------+
| issn-l                  | E     | 0-1  | issn-l                |
+-------------------------+-------+------+-----------------------+
| language                | E     | 1-n  | language              |
+-------------------------+-------+------+-----------------------+
| repecContact            | E     | 0-1  | repecContact          |
+-------------------------+-------+------+-----------------------+
| repecHandle             | E     | 0-1  | repecHandle           |
+-------------------------+-------+------+-----------------------+
| subtitle                | E     | 0-1  | subtitle              |
+-------------------------+-------+------+-----------------------+
| title                   | E     | 1    | title                 |
+-------------------------+-------+------+-----------------------+
| bookshopUrl             | M     | 0-1  | bookshopUrl           |
+-------------------------+-------+------+-----------------------+
| format                  | M     | 1-n  | format                |
+-------------------------+-------+------+-----------------------+
| issn                    | M     | 1    | issn                  |
+-------------------------+-------+------+-----------------------+