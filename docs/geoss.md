# Semantics in Earth Observation 



---

## GEOSS
<div align="justify">

The **Global Earth Observation System of Systems (GEOSS)** was created by the **Group on Earth Observations (GEO)** in order to provide a common and global system where earth observation data could be offered and consumed for high-scale decision support systems.
Therefore, studying GEOSS in terms of semantics should probably be both the starting and end point, if the project intends to make a significant impact in terms of semantics and ontology (think big, go massive), even if the risks to succeed (influencing GEOSS policy) might also be high. 
A deep description of GEOSS is out of the scope of this documentation. We will highlight here the main conclusions in terms of semantics. For that, we used:

- Latest **documentatio**n available on their [website](https://earthobservations.org/geoss.php).

- **Deliverables** provided by the **EDGE project**, which made the latest contribution to the GEOSS portal.
- **Direct feedback from GEOSS members** to explore how GEOSS could be semantically improved and how it could be linked with EIFFEL's use cases.


<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/link_geoss_eiffel.jpg" alt="link GEOSS and EIFFEL" align="center" />
</p>

Unfortunately, the current status of **GEOSS does not provide semantic support**, searches are mainly keyword based and the filters are basically independent among each other. Besides **geospatial** and **temporal** filtering, only the **thematic areas** of *Climate* and *ECVs* seem to be especially relevant for EIFFEL.
It is also worthwhile to mention that ontology had been a relevant aspect in the past (2009), and a EO committee started to work in highlighting semantic vs semantic interoperability and studying various taxonomies and thesauri, but none of them were focussed on EO applications at that time. The GEOSS architecture then is shown in the Figure below. Sadly, the **work was discontinued** and no output ontology was provided nor included in the system (no reasons found yet).

<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/geoss_old_arch.jpg" alt="GEOSS old architecture" align="center" />
</p>


The architecture of GEOSS experienced big changes during the last decade, some categories were added, but still not clear taxonomy could be found. Searches are syntactic and using various protocols, as depicted in the Figure below. Here we can see how the GEOSS web portal connects to other data sources. Without going into detail one by one, **Opensearch** is the interface used for:

- The **DAB (Data Access Broker)**, through which most data providers integrate in GEOSS. Unfortunately, there is **no** such thing as Linked data in GEOSS.
- **NextGEOSS**, a recently ended research project which built a platform and somehow could be assimilated to EIFFEL's goals, so that we can compare to them. 


<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/geoss_arch.jpg" alt="GEOSS architecture" align="center" />
</p>


The GEOSS Curated Relationships domain is a set of tools that **allow the user**, without breaking any existing functionality, to contribute to the GEOSS Ecosystem Knowledge at **resources level**. It intends to facilitate resources access and related management features to the GEOSS community. There are various components that potentially allows an easier extension and also improves the overall scalability of the system. The **Resource editor** is a component available within the GEOSS Web portal that handles general resources management within the GEOSS Curated Relationships domain. 

Anyway, the GEOSS platform, as a system of system, is continuously evolving (see Figure below) and EIFFEL may be relevant contributors for it. 

<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/geoss_evolution.jpg" alt="GEOSS evolution" align="center" />
</p>


There are four working groups in GEO's 2020-2022 Work Programme:

- **Capacity Development (CD- WG)**: mainly related to collecting sharing and building CD tools
- **Climate change (CC-WG)**: intended to develop and implement CC strategies to foster the use of EO services for climate adaptation and mitigation, and supporting nations within the UNFCC and the IPCC.
- **Data (Data-WG)**: it addresses data policy, ethics and governance by suing EO tools
- **Disaster risk reduction (DDR-WG)**: it is mostly focussed on building disaster resilience and Disaster Risk Reduction (DDR) by using EO tools. It includes 3 subgroups, being one of the Climate Change and SDG Coordination (SG3)

From the point of view of the EIFFEL project in **general**, the **CC-WG** is clearly the most directly related group. More specifically, EIFFEL could make an impact on two subgroups: (SG3) enhancing the use of EO for mitigation, and (SG4) enhancing the use of EO for Adaptation and Loss & Damage.

From the point of view of **semantics in particular**, the **Data-WG** is probably the most relevant group, as it promotes the adoption of data sharing principles as well as the recommendation of enhancements towards interoperability of EO data, products and services. By applying semantics and ontologies to that, EIFFEL can potentially impact this WG.


</div>
<br/><br/>


## Copernicus
<div align="justify">

**Copernicus** is the European Union's Earth observation programme, offering **free and open** information services that use **satellite Earth Observation** and **in-situ** (non-space, ground segment) data. It is managed by the EC with the collaboration of the ESA, EUMETSAT, ECMWF, EU Agencies and Mercator Ocean. Copernicus supports EuroGEOSS and is the **European contribution** to the GEO's Global Earth Observation System of Systems (GEOSS)
The EO satellites used by the Copernicus services are split into two groups of missions:

- **Sentinel satellites**: Sentinel-1, -2, -3, -5P and -6 are dedicated satellites, while Sentinel-4 and -5 are instruments onboard EUMETSAT’s weather satellites.
- **Contributing Missions**: operated at National, European or International levels and provide additional data to Copernicus. ESA and EUMETSAT typically coordinate the delivery of data from these missions.

Copernicus provides services that can be used and build **impact in multiple domains**, such as: agriculture, blue economy, climate change and environment, development and cooperation, energy and natural resources, forestry, health, insurance and disaster management, security and defence, tourism, transport and urban planning.
More specifically, Copernicus officially identifies 6 main areas or services:

1. **Atmosphere**: the **Copernicus Atmosphere Monitoring Service (CAMS)** provides data (and forecasts) about the atmosphere in 5 areas: *air quality and atmospheric composition, ozone layer and UV radiation, emission and surface fluxes, solar radiation and climate forcing*.
   
2. **Marine**: the **Copernicus Marine Environment Monitoring Service (CMEMS)** provides oceanic information to support various topics, such as: 
    * *Marine safety* (currents, winds and sea ice for ship routing)

    * *Marine resources* (protection and sustainable management of living marine species)
	
    * *Coastal and marine environment* (water quality monitoring data, sea level rise, sea surface temperature)
    * *Weather, climate and seasonal forecasting* (temperature, salinity, sea level, currents, wind and sea ice)
        
3.	**Land**: the **Copernicus Land Monitoring Service (CLMS)** provides geographical information on land cover and its changes, land use, vegetation state, water cycle and Earth's surface energy variables. The main supporting applications in this field refer to *spatial and urban planning, forest management, water management, agriculture and food security, nature conservation and restoration, rural development, ecosystem accounting and mitigation/adaptation to climate change. Note that this last application directly links with Copernicus C3S, as they are not independent*.

4.	**Climate Change**: the **Copernicus Climate Change Service (C3S)** provides information about the past, present and future climate in Europe and the rest of the World to support adaptation and mitigation policies. We will comment more on this service in the next section.

5.	**Security**: this service provides supporting information for EU security challenges in three main areas:
    *	*Border surveillance* (immigrants at sea, cross-border crime, etc. Operated by Frontex) 
    
    *	*Maritime surveillance* (safety of navigation, support to fisheries control, fight marine pollution and law enforcement. Operated by EMSA)
    *  *Support to EU External Action -SEA- ** (support to third countries in crisis situations. Operated by SatCen).

6.	**Emergency**: the **Copernicus Emergency Management Service (CEMS)** provides geo-spatial information from satellite, in situ or open data sources to stakeholders related to the management of natural disasters and other emergency situations. It consists of:
    * *Mapping component* (maps for Civil Protection Authorities and Humanitarian Aid agencies. Implemented by the EC DG JRC. 
    * *Early warning component* (also subdivided into EFAS, EFFIS and EDO) 


<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/copernicus_general.jpg" alt="Copernicus Overview" align="center" />
</p>

More information about all services can be found on the [Copernicus website](https://www.copernicus.eu/en/copernicus-services). We will focus mainly in this document on Climate Change (C3S), as the EIFF-O should place a major effort on this domain according to the EIFFEL’s objectives, but some of the other services are also useful in the context of the EIFFEL pilots.

C3s is based on three fundamental questions:
- **How is the climate changing?** For this question C3S should provide EO data and reanalyses.
- **How will climate change in the future?** For this question C3S should provide predictions and projections.
- **How will climate change impact our society?** For this question C3S should provide climate indicators and sectorial information.


C3S offers free and open access to climate data and tools to help scientists, consultants, planners and policy/decision- makers analyse and build adaptation and mitigation policies. The data is also intended for the media and the general public. The data constitutes an unvaluable resource to the Global Framework for Climate Services (GFCS) and target the climate needs as defined by the Global Climate Observing System (**GCOS**). This last organization is in charge of the Essential Climate Variables (**ECVs**), which will be described in section 3  
C3S provides climate data through the Climate Data Store (CDS), but it is not about just offering datasets. The structure of C3s is decomposed in 4 building blocks:

-	**Climate datasets**: these are further divided into:
    * **Observations**: they are broadly organised or classified in form of ECV products, aligned with the ESA’s Climate Change Initiative (CCI).
    * **Climate reanalyses**: they are consistent time-series datasets resulting from combining past observations with models and are widely used to see the evolution of climate variables across time. Examples are ERA5 (ECMWF) and ERA5-Land.  
    * **Seasonal forecasts**: they are time-series datasets for forecast variables (air and sea-surface temperature, atmospheric circulation and precipitation) as well as graphical products They are updated on a monthly basis and cover a period of six months.
    * **Climate projections**: they are simulation datasets for the long-term period based on numerical models (GCM – CMIP5 or RCM- CORDEX) for GHG, aerosols, etc. Main issues here relate to increasing the resolution of the models as well as better estimating the (sources of) uncertainties.

-	**Tools for using climate data**: split into
    * **Toolbox**: it is a ser of tools for developers to create web-based apps based on CDS datasets, whose access is abstracted through an API. It is also executed on CDS infrastructure. The [landing page](https://cds.climate.copernicus.eu/cdsapp#!/toolbox) provides documentation, toolbox editor, API and application gallery.
    *	**Common data model (CDM)**: it provides a homogeneous format for all data and products in the CDS, so that they can be properly processed in the toolkit. The CDM is based on the Climate and Forecast (CF) convention.  According to the C3S [documentation](https://cds.climate.copernicus.eu/toolbox/doc/how-to/15_how_to_understand_the_common_data_model/15_how_to_understand_the_common_data_model.html), “the Toolbox CDM is a collection of dictionaries defining, for each variable in the CDS catalogue, the CDM compliant name, units, coordinates and attributes to be used in the Toolbox”


-	**Sectorial impacts**: it consists of a set of demonstrators to show how climate data can be used to target specific goals. They encompass three areas:
    * **Specific sectors**: water management, agriculture and forestry, insurance, energy, infrastructure & transport, health, coastal areas, disaster risk reduction, shipping, tourism, biodiversity and global users.
    * **Sectorial projects**: several projects were created to build various scenarios that make use of the data and tools of C3S.
    * **Data in action**: this relates to the concrete showcases of the demonstrator projects. 


Among the different aspects from C3S, and from the *perspective of building an ontology, the CDM is probably the closest approach*; even if it has a different goal than the EIFF-O, at least it is able to define a set of terms and establish a relationship among them.  
As the EIFF-O is intended to be used as an improved search tool, it is also worthwhile to briefly check for the different options available at C3S. Currently a user can search for 3 main types:

- **Datasets**:  composed of three main items
    * **Overview**: it provides a basic description as well as *data description* (type, horizontal coverage and resolution, vertical coverage and resolution, file format, versions, frequency update), *main variables* (name, unit, description) and *related variables*.
    * **Download data**: it allows to select the variable to be downloaded, as well as temporal filters (year, month, hour) and output format (e.g., GRIB2, NetCDF-4).
    * **Documentation**: links to related documents or wikis.
    
-	**Applications**: composed also of three main items
    * **Overview**: main description including the input variables and the user-selected parameters.
    * **Application**: widget with the app and the data description of the used dataset
    * **Source code**: application source code
- 	**Providers**: description of the given provider

Additional metadata for the datasets, applications and providers include:
- Contact information
- License
- Publication date
- References (citations, DOIs, etc.) -optional
- Related data (link to other related documents) -optional

The response of an issued request can be sort by relevancy, title or type. The additional filtering criteria are represented in the Figure below with the associated number of results (as of December 2021). 

<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/cds_filtering.jpg" alt="C3S CDS filtering criteria" align="center" />
</p>

<br/><br/>

</div>


## Related ontologies and thesauri for the EO field
<div align="justify">
   
Though there are many ontologies and thesauri for many different purposes, some of them are listed in the following summary Table with more or less relationship with the EO field.


|Ontology|Description|
|---|---|
|**SWEET** (Semantic Web for Earth Environmental Technology Ontology) |Originally developed by NASA’s JPL, it contains over 6000 concepts organized in various categories. Currently it is governed by the ESIP foundation and can be found on a [GitHub](https://github.com/ESIPFed/sweet)  repository. Top level concepts include Representation (e.g., time, space) and Realm (e.g., Ocean, Land Surface, Terrestrial Hydrosphere, Atmosphere). It has links and influence with *EnvO* (Environmental Ontology). <br/>**Possible link with EIFF-O**: concepts from the *ECV taxonomy* specified by GCOS can be mapped to Realm. Spatial and temporal properties from datasets can also be mapped to Representation.|
|**ESA Thesaurus** |The European Space Agency provides a service for publication and browsing of EO related vocabularies, including interfaces for integration. Currently there is only one Thesaurus in the [online list](https://thesauri.spacebel.be/en/) supported by the open-source web-based SKOS browser and publishing tool [Skosmos](https://skosmos.org/). The Thesaurus includes many concepts and are hierarchically organized under 3 top concepts (Earth Topics, Instruments and Platforms). Generally, concepts are not well described (no description field), but just defined and linked with other terms through the *broader, narrower* and *exactMatch* property of SKOS.<br/>**Possible link with EIFF-O**: The concept *Atmospheric Indicators* under Earth Topics --> Earth Topic --> Climate could be further extended (narrowed) with the associated ECVs. In fact, the concept Essential Climate Variables also exist under the same parent concept, but they are not linked. It seems that the main intention of this Thesaurus is to link Earth concepts with the systems and techniques to capture data from space (e.g., Imaging Radars, Radar Altimeters, Scatterometers).|
|**GEMET** (General Multilingual Environmental Thesaurus) |It has been developed as an indexing, retrieval and control tool for the European Topic Centre on Catalogue of Data Sources (ETC/CDS) and the European Environment Agency (EEA), Copenhagen. [GEMET](https://www.eionet.europa.eu/gemet/en/about/) is supported by the EEA and Eionet - the institutional environmental network of almost 40 European countries. It includes multiple concepts grouped by: (i) Human activities and products, effects on the environment, (ii) Natural environment, and (iii) social aspects, environmental policy measures. Here the concepts include a definition as a way of better describing the concept itself as well as other related terms. <br/>**Possible link with EIFF-O**: The concept of *climate change* is part of the vocabulary, and it extends further covering *climate change adaptation* and *climate change mitigation*. The applications (services) in EIFFEL can be tagged with these concepts.|
|**EUROVOC** |[EuroVoc](https://op.europa.eu/es/web/eu-vocabularies/dataset/-/resource?uri=http://publications.europa.eu/resource/dataset/eurovoc) is a multilingual, multidisciplinary thesaurus covering the activities of the EU and managed by the Publications Office of the European Union, which moved forward to ontology-based thesaurus management and semantic web technologies conformant to W3C recommendations. The scope of EuroVoc is quite general and not restricted to EO, but it potentially allows to align concepts administratively used by the European Union.<br/>**Possible link with EIFF-O**: the Thesaurus includes concepts such as *climate change policy* as part of the *environmental policy* concept, *adaptation to climate change* and *UNFCC*.|
|**AGROVOC** |[AGROVOC](https://www.fao.org/agrovoc/) provides a way to organize knowledge for subsequent data retrieval. It is a structured collection of concepts, terms, definitions and relationships. Concepts represent anything in food and agriculture, such as maize, hunger, aquaculture, value chains or forestry. These concepts are used to unambiguously identify resources, allowing standardized indexing processes, making searching more efficient. Each concept in AGROVOC also has terms used to express it in various languages, so called lexicalizations. Today, AGROVOC consists of +40 300 concepts and +953 000 terms in up to 41 languages. AGROVOC is a relevant thesaurus about food and agriculture, published as linked open data, available for public use. <br/>**Possible link with EIFF-O**: the Thesaurus includes concepts such as *climate change, climate change adaptation, climate change mitigation*, and *climate models*, among others.|
|**EARth** |[EARTh](https://vocabularyserver.com/cnr/ml/earth/en/) is a general-purpose thesaurus for the environment, which has been published as a SKOS dataset in the Linked Open Data Cloud. It intends to help in indexing and discovery environmental resources by refining and extending GEMET; besides it has been interlinked to popular LOD datasets as AGROVOC, EUROVOC, DBPEDIA and UMTHES. <br/>**Possible link with EIFF-O**: the Thesaurus includes plenty of concepts related to climate, such as *climate change, adverse climate change, climate damages, climate model*, etc.|
|**ENVO** (Environmental Ontology)|[ENVO](https://sites.google.com/site/environmentontology/home)  is a big ontology for environmental entities with hundreds of terms and many more imported, it is able to describe concepts such as ecosystems, planets and other environmental processes; thus, it increases the interoperability of environmental descriptions and FAIRness support.<br/>**Possible link with EIFF-O**: the Thesaurus includes concepts such as *climate change* and *climate system*.|
|


<br/><br/>

</div>


## Related projects related to the EO field. Summary analysis
<div align="justify">
   
This section includes a summary analysis and assessment of various research projects related to EO, based on three indicators:
-	**Semantic support** in the core architecture of the system
-	Proper **documentation** available to be used by third entities
-	Proper **software** and **support** available to be used by third entities

These three indicators might range from *None* to *High* and the description of the values are provided below for each of them.
The Semantic support is assessed with the following values:
-	**None**: No semantics or almost none (only keyword-based search and unrelated categories provided). Any other possible use of semantics has nothing to do with EO field
-	**Low**: A useful EO related taxonomy is provided
-	**Medium**: RDF (or JSON LD) is used to define or characterize entities related to EO aspects
-	**High**: An ontology is defined and used related to EO aspects

The documentation is evaluated depending on the availability and updatability/recentness of the documentation related to the used semantics:
-	**None**: no documentation or almost none
-	**Low**: static (old) documentation; no updates
-	**Medium**: Documentation available and updated from time to time, but difficult to find (no central place)
-	**High**: online documentation updated in a central location (e.g., readthedocs)

Another aspect to consider is the availability of software and related support:
-	**None**: no software available to be used 
-	**Low**: software available, but not open or very limited in its usage
-	**Medium**: Open software available, but no current update nor support
-	**High**: Updated software and open source (e.g., GitHub) 

The overall rating is then taken as the average of the previous 3 assessment indicators.



|Project|Semantic support|Documentation|Available software & support|Overall rating|
|---|---||---|---||---|
|**EDGE**|None|Low|Medium|Low|
|**NextGEOSS**|None|Low|Medium|Low|
|**GEOCRADLE**|None|Low|Low|Low|
|**Copub.AC**|Low|Low|None|Low|
|**EO4GEO**|Low|Low|Medium|Low|
|**Copernicus App Lab**|High|Low|Low|Medium|
|**SMURBS**|High|Low|None|Low|



<br/><br/>

</div>
   


<br/><br/>

</div>



 
