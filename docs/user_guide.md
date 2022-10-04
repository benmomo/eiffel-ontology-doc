# User guide 



---

## Architecture
<div align="justify">

The EIFF-O module is composed of two main blocks: a **front-end** and a **back-end**, as depicted in the Figure below.
The front-end is in charge of providing access to the **different actors** interacting with this subsystem:

- **Machines or software agents** might directly retrieve the different ontologies provided (EIFF-O, EO taxonomy, ECV taxonomy and SDG taxonomy)
- **Users** might employ the Access UI to perform a basic usage of all functionalities of the EIFF-O module as an independent block. This is probably not relevant in the whole EIFFEL architecture, as the Visualization Engine is supposed to be the main user's entry point; however, it makes sense for basic checks. 
- The **proxy module** is mainly responsible to provide access to backend services for external modules and actors. It might incorporate also some basic security mechanisms (e.g., authentication), but it can be omitted if the security is handled as a cross-layer within the overall EIFFEL architecture.


<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/eiffo_arch.png" alt="EIFF-O architecture" align="center" />
</p>

The back-end is responsible for providing the different visible services related to the supported ontologies:

- The **ontology viewer** allows to explore in a visual way the different entities of the ontology, as well as their properties and related instances (if any). It is a web-based implementation of the *Visual Notation for OWL ontologies (VOWL)*.
- The **SPARQL endpoint** allows to make SPARQL queries for the four different ontologies (EIFF-O, EO, ECV and SDG), which are previously uploaded in the SPARQL server. This is probably the most powerful way to exploit ontologies and reason among them. However, its usage within the EIFFEL project might be limited or restricted for some reasons:

    * Instances of services and datasets will not be stored in the ontology database, but as part of another database (Elasticsearch). In other words, it is most likely that the ontologies employed in EIFFEL will have read-only support, which also allows having them as static files available in the front-end without losing any data inconsistency.
    * SPARQL are typically used by machines or software agents, whereas in EIFFEL our primary targets are users (humans) assisted by a graphical interface (Visualization Engine). Anyway, the NLP module might probably make use of some functionality (e.g., usage of synonyms to link concepts).

- The **EIFF-O REST API** will serve for most of the functionalities needed from other modules within the EIFFEL architecture:

    * It should provide tagging support for the different entities, mainly for datasets but probably also for services and providers. By using ECV, SDG and EO taxonomies, terms from those vocabularies should be included somehow and as much as possible as metadata in the newly created items (datasets, services). Currently it is not clear whether this step will be performed automatically or manually, but in any case, assistance should be provided through this API.
    *	It could wrap some common requests to the ontology without the need of using SPARQL, in order to provide a full JSON interface. For example, one may request to get the list of SDG goals or targets as a JSON file without the need of requesting entities and properties via SPARQL.
    * It should provide any other needed functionality that might appear during development and is not part of the previously identified ones.        


The architecture of the EIFF-O module is envisioned to be highly modular and distributed in form of **Docker containers**. The Figure below shows the identification of the basic components according to a docker-compose structure.

<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/dockerisation.jpg" alt="EIFF-O Dockerisation" align="center" />
</p>


</div>
<br/><br/>


## EIFF-O Front-End
<div align="justify">

The front-end is basically a web server (Apache) acting as proxy with a set of web page that gives access to all services related to the EIFFEL ontology, as depicted in the Figure below:

-	By clicking on the **ontology** icon/link, the user will be redirected to the Ontology view, which has its own UI  
-	The **documentation** link provides access to an online documentation portal
-	The **code repository** icon links directly to the public GitHub repository.
-	The **API Swagger** provides access to the REST API with its own interface
-	The **test and examples** icon is meant to provide some usage examples

<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/eiffo_front_end_gui.jpg" alt="EIFF-O front-end UI" align="center" />
</p>

Technically, the front-end open ports **HTTP 80** and **HTTPS 443**. The non-secure access allows for retrieving the ontology files, which are also stored as OWL/TTL files, as some ontology-related programs currently in the community do not support HTTPS.
<br/><br/>

</div>


## Ontology viewer
<div align="justify">

 The ontology viewer is based on [WebOWL](http://vowl.visualdataweb.org/webvowl.html), which is a web application that allows to display ontologies in an interactive way. Basically, OWL files need to be **converted** first into JSON files, which are later **displayed** on the browser as a **force-directed graph**. This converter (OWL2VOWL) is also part of the released software.

<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/eiffo_ontology_viewer_1.jpg" alt="Ontology viewer UI" align="center" />
</p>

The user interface is depicted in the previous Figure, with three main parts:

-	Most of the screen is devoted to **visualizing** the different entities in form of a graph. This area supports zoom in/out functions to restrict the visualization to a certain concept, in case the ontology (and the resulting graph) is big. 
The graph also allows to move any of the concepts from one place to another with the mouse in order to better visualize the graph. 

-	On the **right side**, there is some **useful information about the loaded ontology**: (i) a basic description of the specific loaded ontology, (ii) some metadata about it, such as date, creator, rights, language, title, etc.

-	On the bottom, there are some **useful tools**:

	- Through the **Ontology item** one might select which ontology to load (currently we have 4 different ontologies: SDG, ECV, EO and EIFF-O). In general, it is possible to load any ontology as long as the IRI (URL for the ontology) is provided. For simplicity, we have already restricted the choice for the four ones. Besides, this is an example of ontology tools that does not support HTTPS when accessing the OWL file.
	- The **search text area** allows to automatically locate a particular concept in the graph with some **additional help** (the app indexes concepts and properties and suggests/displays the most likely ones as the user types some text). 
	- The **Export tool** allows to export the displayed ontology in various output formats (e.g., JSON, SVG) 
	- The **Filter item** is related to the way entities (concepts) and properties are displayed in the visualization area. The same applies for the **Options** item.

Note that this viewer is not intended for editing purposes. For such purpose, it is recommended to use some specific editor for ontology files, such as [Protege](https://protege.stanford.edu/). This is the one that has been used in this project.



<br/><br/>

</div>

  


<br/><br/>





## API
<div align="justify">
   
TBC 


<br/><br/>

</div>  


<br/><br/>





## SPARQL endpoint
<div align="justify">
   
TBC 


<br/><br/>

</div>  


<br/><br/>


