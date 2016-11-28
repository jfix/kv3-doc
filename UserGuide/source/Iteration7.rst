Iteration 7 Release - January 21st 2016
=================================================

Since August 2015, we have been working on an important upgrade of Kappa (http://kappa.oecd.org/). This upgrade was focused on the acquisition of publications' content and metadata from our partner IGOs, and their dissemination to iLibrary.

Some of you using Kappa already know that this upgrade has been released in production last week. 
This new version now allows the IGO content team to load UN publications' PDF  files and XML metadata and into Kappa, and disseminate them to the upcoming live UN iLibrary.

From  `Kappa homepage <http://kappa.oecd.org/v3>`_ , you can already search and find both OECD and UN publications using facets.

There are currently into Kappa :

* 487 distinct UN publications in various languages, 
* 7598 associated chapters and 306 articles
* 231 serials
In the next weeks, the IGO content team will keep loading further UN content and metadata in view of the upcoming launch of the UN iLibrary.

In addition to this, as part of this new release Kappa is able to:

* Acquire, manage and disseminate data indicators for IGOs. The first ones will be data indicators for the Nordic Council of Ministers. They are being produced and will be rolled-out soon into Kappa and the NCM iLibrary.
* Acquire, manage and disseminate new articles of the Observer. The first online first articles of the Observer will be rolled-out soon into Kappa and the OECD iLibrary.

We are still fine-tuning a few issues introduced by these new developments, so apologies to those who are impacted. 

In a few weeks, we will make a demonstration of Kappa, to showcase in more details the new features, explain the scope of content currently covered and the next steps.
In the meantime if you have any questions or experience any issue using Kappa please let Claudia of myself know.


Pascale & Kappa team


**ITERATION 7: UN ILIBRARY PROTOTYPE**


Sprint 7.1
-----------

12 Nov 2015
19 issues   (19 closed - 0 open)

*  User story #10499: modele des chapitres
*  User story #10500: sections (component groups)
*  User story #10502: Mass create components from loading.xsd XML
*  User story #10503: chapter PDF loading
*  User story #10506: norden indicators and groups (management only)
*  User story #10508: incremental export to UN iLibrary Beta
*  Technical story #10233: Nettoyer la table Product de Kappa suite à la suppression des Datasets dans KappaV2
*  Technical story #10507: mise en production of Kv3
*  Task #9897: remove Start date end date
*  Task #9898: Move Direct link to read at manifestation level
*  Task #9899: Migrate Thumbnails from KV2 to KV3 model (for all item types)
*  Task #10216: Review of Xlinks
*  Task #10339: ``softEmbargoDate`` to be added
*  Task #10340: ``editor`` to be added
*  Support #10591: doublon serial titles
*  Support #10606: Extract of contentXML for all groups and indicators
*  Bug #10295: UNABLE to find theme taxonomy for 282 indicators
*  Bug #10558: Fix FeedBack *  Task to handle all IGo's
*  Bug #10601: [PROD] iLibrary - Dataset XML validation error


Sprint 7.2
------------

03 Dec 2015
13 issues   (13 closed - 0 open)


*  User story #10498: xlinks
*  User story #10501: Article model (no V2 Migration)
*  User story #10504: iLibrary export of Chapters
*  User story #10659: iLibrary export of Sections
*  Task #10643: Revue des specs Export Chapter
*  Task #10665: Person taxonomy : populate label type observer
*  Task #10666: Digital Product Factory (DPF) User
*  Task #10712: Loading of chapters: inheritance of publication date
*  Task #10727: Hotfolder pour charger les chapter PDF dans Sprintly
*  Bug #10561: book eisbn exported as print isbn when no print version is available
*  Bug #10668: Chapters Loading : component content type n'est pas mappé
*  Bug #10671: /content endpoint doesn't accept full rid
*  Bug #10673: Import KV2V3 : bug l'item type 'publ' génère un diff tous les soirs


Sprint 7.3
-----------

12 Jan 2016
42 issues   (42 closed - 0 open)


*  User story #10505: iLibrary export of articles
*  User story #10511: iLibrary export of Norden indicators and groups
*  User story #10642: Déployer l'exportly pour export iLibrary Beta
*  User story #10645: Keepeek Export
*  User story #10657: iLibrary export of multilingual metadata.
*  User story #10722: revisit xlinks and export of isReplacedBy/isContinuedBy
*  User story #10839: Management of language versions and multilingual objects (1/2)
*  Technical story #10646: mise en production of Kv3
*  Technical story #10647: Deploiement sur Exportly + Export iLibrary Beta
*  Technical story #10877: implement feedback call from Keepeek export to Kv3
*  Task #10011: DATA Objects Interface Show links to all parents
*  Task #10656: Igo taxonomy updates
*  Task #10672: Observer articles FTIs: creating or updating the manifestation and loading the files to Kappa via the API
*  Task #10687: iLibrary export of UN periodicals (p<1) as ``Outlook``
*  Task #10757: Igo specific coverimage for indicators
*  Task #10758: remove criteria for eligibility exception of statistical periodicals
*  Task #10785: Inheritance Parent book to Chapter and Article at loading
*  Task #10816: Observer articles must have a dateOfPublication
*  Task #10825: File name of (FTI) files loaded to Kappa
*  Task #10833: XMS file update (after next Kappa release in 01/16)
*  Task #10835: Page start - page end à ajouter pour pour paper et comp
*  Task #10840: Import of indicators should match on code AND IGO
*  Task #10865: Cannot remove ``Continues`` link from a Kappa record
*  Task #10904: Loading.xsd fichier enumerations et editor
*  Task #10918: generic Export
*  Feature #10709: Set Observer article Volume (at W level) on first export from editorial system
*  Feature #10902: publisher logo value missing full URL to //assets.oecdcode.org
*  Feature #10907: related incicators / related databases not filtered by igo
*  Scrum  Bug #10804: incorrect rdf type in chapter export
*  Scrum  Bug #10805: incorrect rdf type in issue export
*  Scrum  Bug #10806: chapters not included in book export
*  Scrum  Bug #10807: multilingual abstracts exported with invalid language tags
*  Scrum  Bug #10812: FTI des articles ne trouvent pas leur record
*  Scrum  Bug #10845: ``Continues`` bug on save (database continues a dataset)
*  Scrum  Bug #10851: ``Continues`` bug on save (dataset group continues a dataset group)
*  Scrum  Bug #10858: Exported article are missing their <isPartOf> link
*  Scrum  Bug #10895: No member indicator of link displayed on the indicator
*  Scrum  Bug #10897: keepeek export of observer articles missing parent references - R007
*  Scrum  Bug #10912: case sensitivity in <furtherReading> property value causing display issues for Norden indicator related titles
*  Scrum  Bug #10913: ilibrary section2.xml is empty resulting in missing sections titles
*  Bug #10454: DOI prefix of IGO translations
*  Bug #10764: Regression on Archive (csv zip) file naming convention


Sprint 7.4
----------

25 Feb 2016
45 issues   (45 closed - 0 open)



*  User story #10597: Articles metadata edition via the UI
*  User story #10641: Déployer la sprintly
*  User story #10648: Creation of Periodicals and collections via a form
*  User story #10762: xlinks kv2 reprise
*  User story #10824: Extractions du catalogue Kappa (UN pour le marketing)
*  User story #10965: API documentation rendering issue on Firefox
*  Technical story #10640: Reprise des Xlinks de Kappa V2
*  Technical story #10981: update MarkLogic version on integration server
*  Technical story #10978: search API - extension des informations renvoyees
*  Task #9895: Short title model changes
*  Task #10367: purge @target attribute from code
*  Task #10723: Editor : show on UI and update V2-V3 mapping
*  Task #10770: improve returned information for non-existing resource in UI
*  Task #10827: links: changes in labels and in taxonomy
*  Task #10894: DOiDashboard
*  Task #10954: Ordre de suppression objets UN with PDF
*  Task #10967: Update de la taxonomie xlinks
*  Task #10968: Replaces : Update de la taxonomie xlinks
*  Task #10969: Regeneration du fichier enumerations pour Amnet
*  Task #10973: Requetes de contrôle qualité pour équipe IGO
*  Task #10979: add a new app user to the static users
*  Task #10980: expose enumerations via API as an XSD enumeration
*  Task #10994: re-export of African Statistical Yearbook
*  Task #11013: Directorate facet
*  Task #11087: Remove link Functionalities from home page
*  Task #11088: Correction sur la page about
*  Task #11097: Taxonomie periodicity à la place de country
*  Task #11112: changement de libellé subtopic
*  Support #10943: Un Beta/KV3 errors detected 2016_01_13
*  Support #11047: Erreur à l'export du 04/02/2016
*  Support #11051: Changement de periodicité deux serials UN
*  Support #11059: Serial UN - periodicité à changer et reloader (24120898)
*  Support #11063: Problème avec caracteres spéciaux sur iLibrary
*  Scrum  Bug #10898: keepeek export eligiblity criteria issues
*  Scrum  Bug #10929: Le User Code au niveau expression des articles est le même pour tous les articles d'une même langue
*  Scrum  Bug #10938: Failure to load archive
*  Scrum  Bug #10955: Keepeek publisher logo missing for UN titles
*  Scrum  Bug #10964: Affichage des xlinks archives splitté dans l'interface
*  Scrum  Bug #10970: Hot folder gone cold!
*  Scrum  Bug #11048: Improve book content loading process
*  Scrum  Bug #11060: expanded tree cache full - error en production
*  Scrum  Bug #11065: Archive records do not inherit the parent database
*  Bug #10548: Export du lien Freepreview d'un Summary sur iLibrary alors qu'il n'ai pas éligible Freepreview
*  Bug #10705: Creating content in Kappa
*  Bug #10798: KappaV3 Daily - XML validation failure


