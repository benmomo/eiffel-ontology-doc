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

-	On the **right side**, there is some **useful information about the loaded ontology**: (i) a basic description of the specific loaded ontology, (ii) some metadata about it, such as date, creator, rights, language, title, etc., and (iii) some statistics about the graph/ontology.

-	On the bottom, there are some **useful tools**:

	- Through the **Ontology item** one might select which ontology to load (currently we have 4 different ontologies: SDG, ECV, EO and EIFF-O). In general, it is possible to load any ontology as long as the IRI (URL for the ontology) is provided. For simplicity, we have already restricted the choice for the four ones. Besides, this is an example of ontology tools that does not support HTTPS when accessing the OWL file.
	- The **search text area** allows to automatically locate a particular concept in the graph with some **additional help** (the app indexes concepts and properties and suggests/displays the most likely ones as the user types some text). 
	- The **Export tool** allows to export the displayed ontology in various output formats (e.g., JSON, SVG) 
	- The **Filter item** is related to the way entities (concepts) and properties are displayed in the visualization area. The same applies for the **Options** item.

Note that this viewer is not intended for editing purposes. For such purpose, it is recommended to use some specific editor for ontology files, such as [Protege](https://protege.stanford.edu/). This is the one that has been used in this project.



<br/><br/>

</div>

  


<br/><br/>





## REST API
<div align="justify">
   
The REST API provided as a backend service allows to retrieve information about the different ontologies included in the project. There are three main aspects to consider here:

- Through the SPARQL interface (see next section) it is possible to obtain all information from the ontologies, as basically all information is included in the OWL/TTL files. The usage of REST APIs allows a **simpler way** of retrieving information for users and developers who are not familiar with SPARQL interfaces and do not intend to perform any semantic reasoning operation
- The REST API is basically intended to provide information about the **instances** available in the developed ontologies. This implies that ontologies without elements/instances are not currently accessible through the REST API. Currently **ECV, SDG and EO** ontologies do include instances, whereas the EIFF-O ontology does not. For example, datasets that are harvested from the GEO DAB are stored in an independent repository and are not instantiated as instances within the EIFF-O ontology. Therefore, no REST interface is currently available for the EIFF-O ontology.
- The main link between the ontology and other EIFFEL tasks is expected to be through some **tagging functionality** that allows to include additional metadata related to the ontologies (specific terms from their vocabularies). Here, the REST API is expected to provide **support** in this way. This support might evolve through the project depending on: (i) the evolution of tasks T3.3 and T3.4, which last longer than task T3.2, and (ii) the evolution of the pilots and the best way to include semantic tags. 	 

The developed REST API includes a **Swagger interface** where a user/developer is able to see and test the different functions. The Swagger API supports **HTTPS** and **authorization** to provide the highest level of security. The front-end acts as secure proxy to access it.

<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/rest_api_ecv.jpg" alt="REST API - ECV" align="center" />
</p>

The **ECV REST API** (see previous Figure) allows to retrieve a list of all instances from the various concepts in the ontology (data sources, domains, ECVs, products, product requirements, scientific areas and stewards). The API can be either requested via the Swagger interface or through another similar API tool such as [Postman](https://www.postman.com/). The Table below shows the result for one *ECV* and its related information, from the whole array of ECVs. You can see the different fields and, at the same time, the corresponding **class** and the **individual/instance** from the ontology is provided, which might help in further queries using SPARQL.

```
 {
        "dataSource": [
            {
                "dsLink": "http://www.globbiomass.org/",
                "dsName": "ESA-Globbiomass",
                "oClass": "http://purl.org/eiffo/ecv#DataSource",
                "oInstance": "http://purl.org/eiffo/ecv#DS_081"
            },
            {
                "dsLink": "lucid.wur.nl",
                "dsName": "GEOCARBON",
                "oClass": "http://purl.org/eiffo/ecv#DataSource",
                "oInstance": "http://purl.org/eiffo/ecv#DS_082"
            },
            {
                "dsLink": "https://www.globalforestwatch.org/",
                "dsName": "WRI Global Forest Watch",
                "oClass": "http://purl.org/eiffo/ecv#DataSource",
                "oInstance": "http://purl.org/eiffo/ecv#DS_083"
            },
            {
                "dsLink": "https://fluxnet.ornl.gov/fluxnetdb",
                "dsName": "FLUXNET",
                "oClass": "http://purl.org/eiffo/ecv#DataSource",
                "oInstance": "http://purl.org/eiffo/ecv#DS_084"
            }
        ],
        "domain": {
            "domainLevel": 2,
            "domainName": "Biosphere",
            "oClass": "http://purl.org/eiffo/ecv#Domain",
            "oInstance": "http://purl.org/eiffo/ecv#BiosphereDomain1"
        },
        "ecvDescription": "Land cover is the observed (bio)-physical cover on the Earth surface. It influences climate by modifying water and energy exchanges with the atmosphere and by changing greenhouse gas and aerosol sources and sinks. Land-cover conditions are inherently dynamic (i.e. seasonality) and distributions are linked to regional climatic conditions, so changes in cover can be due to climate change on a regional scale as well as directly due to human activities",
        "ecvFactSheetLink": "https://ane4bf-datap1.s3.eu-west-1.amazonaws.com/wmod8_climatedata/s3fs-public/biomass_ecv_factsheet_201905.pdf?UIj2pnLviZJQEYAmaNuHOB3_fWsMjQoS",
        "ecvIconLink": "https://ane4bf-datat.s3.eu-west-1.amazonaws.com/wmod8_climatedata/s3fs-public/ico-bio-above-ground-biomass_hover.png?9_9apKhjAgL8jiCQ0E29_w1uo_u7tE1V=",
        "ecvName": "Above-ground Biomass",
        "ecvSteward": [
            {
                "oClass": "http://purl.org/eiffo/ecv#ECVSteward",
                "oInstance": "http://purl.org/eiffo/ecv#ECVSteward_21",
                "stewardAffiliation": "GOFC-GOLD, Wageningen University, Netherlands",
                "stewardName": "Martin Herold"
            },
            {
                "oClass": "http://purl.org/eiffo/ecv#ECVSteward",
                "oInstance": "http://purl.org/eiffo/ecv#ECVSteward_22",
                "stewardAffiliation": "Jet Propulsion Laboratory California Institute of Technology, US",
                "stewardName": "Sassan Saatchi"
            }
        ],
        "oClass": "http://purl.org/eiffo/ecv#ECV",
        "oInstance": "http://purl.org/eiffo/ecv#AboveGroundBiomassECV1",
        "product": [
            {
                "oClass": "http://purl.org/eiffo/ecv#ECVProduct",
                "oInstance": "http://purl.org/eiffo/ecv#ECVProduct_073",
                "productDefinition": "Mass of live and/or dead organic matter in terrestrial vegetation.",
                "productName": "Maps of aboveground biomass"
            }
        ]
    },
...
}
```

The **SDG REST API** (see Figure below) allows to retrieve all instances from the SDG concepts: goals, targets, indicators and series.

<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/rest_api_sdg.jpg" alt="REST API - SDG" align="center" />
</p>

The Table below shows the result for one *Target* and its related information, from the whole array of targets. Once again, you can see the different fields and, at the same time, the corresponding **class** and the **individual/instance** from the ontology.

```
[
    {
        "inScheme": "http://metadata.un.org/sdg",
        "indicator": [
            "http://metadata.un.org/sdg/C010101"
        ],
        "isTargetOf": "http://metadata.un.org/sdg/1",
        "note": "Target 1.1",
        "oClass": "http://metadata.un.org/sdg/ontology#Target",
        "oInstance": "http://metadata.un.org/sdg/1.1",
        "prefLabel": "By 2030, eradicate extreme poverty for all people everywhere, currently measured as people living on less than $1.25 a day",
        "sdgCode": "1.1",
        "subject": [
            "http://eurovoc.europa.eu/2062",
            "http://eurovoc.europa.eu/6781",
            "http://metadata.un.org/thesaurus/1000544",
            "http://metadata.un.org/thesaurus/1006166"
        ]
    },
...
}    
    
```


<br/><br/>

</div>  


<br/><br/>





## SPARQL endpoint
<div align="justify">
   
TBC 


<br/><br/>

</div>  


<br/><br/>


