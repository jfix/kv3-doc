OECD RePEC metadata and directory
=================================

The metadata describing publications is given in "templates". There is a different type of template for each of the various types of items that must be described to RePEc, i.e. Archive, Serial, Item. Each template has several descriptive fields.

The metadata is made available as simple text files on an OECD FTP server. The RePEc services then retrieve files regularly for integration in their database. The directory holding the files is the RePEc archive. 

Each IGO should have its own archive with a unique identifier or 3 letter handle. 

Directory structure for OECD on the RePEc FTP server
----------------------------------------------------

The OECD files are available at http://repec.oecdcode.org/oec/  

The directory and file structure is as follows:

RePEc/ 
	oec/							(folder named after archive handle)
		oecarch.rdf					(archive description file)
		oecseri.rdf   				(series file)
		series directory/			(folder named after series handle) 
		rdf files					(item(s) file(s))

For the archive description file see :doc:`Export_Repec_Archive.rst` 
For the series description files see :doc:`Export_Repec_WorkingPaperSeries_OECD.rst` for Working Papers and :doc:`Export_Repec_Journal_OECD.rst` for Journals.

Data Model
----------

The complete RePEc data model is available at https://ideas.repec.org/stepbystep.html  
