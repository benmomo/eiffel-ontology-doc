# Ontologies used in EIFFEL



---

## Methodology
<div align="justify">

The determination of the purpose and scope of the ontology is just the first step in the general methodology, which is represented in the Figure below

<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/methodology.jpg" alt="Methodology" align="center" />
</p>

The depicted process is iterative, but can be repeated continuously; this means that, at any given step S1, the ontology developer can go back to a previous step S2 (S2<S1) to enhance or correct it. This typically happen after evaluating step S1 and checking that there is something missing to satisfy the goal or scope. It is important to highlight that **there is no single perfect way to model a domain upon which the scope of the ontology is built, but multiple valid alternatives**. 

**The first step determines the scope**. Here we need to be clear with the domain under study and the type of knowledge we want to manage within such domain. Therefore, this step should answer the following questions: 

- Which **domain** should be covered with the ontology?
- What will be the **purpose** of the ontology in this domain?
- What **types of questions** are answered by the knowledge represented in the ontology? Related to that there is a common approach and recommendation to the use of **competency questions**. Note that some of these questions might change within the lifecycle of the ontology, as it gets refined iteratively.
- **Who** will use and maintain the ontology? Not only users (stakeholders) might be relevant here, but also other entities supported by the ontology. For example, if EIFFEL is developing an NLP search tool, it might be relevant to include synonyms and related speech information for the concepts in the ontology.

**The second step should consider reusing any existing ontologies**. Before starting to develop something new, reusing existing ontologies (if any) is crucial. Ontologies are something which should be reused over and over again, if possible. The world is full of things interconnected and so is also the semantic web. By reusing some existing ontology, you can incorporate part (or all) of the knowledge to your domain, reducing the space of uncertainties while connecting things (concepts, entities). From a market perspective, it also **saves cost and time**. Not only by using part (or all) of the existing ontology, but also by **reusing other existing tools** that might be available and have already been tested with the former ontologies. In fact, the combination of an ontology and a tool is probable the best way to validate such ontology and check whether it can be reused for the target application.
Only in the case that there is no suitable ontology or if the adaptation is too complex, then a new ontology should be created. For EIFFEL, there will be something new, but linked with other semantic concepts and ontologies described in previous chapters.

**The third step relates to building a terminology**. Before starting with classes and properties, it is important to **identify and list the main concepts**. Basically, it is a collection of vocabulary terms stating:
- The **concepts** we are talking about (e.g., datasets, location, ECV)
- The main **properties** that have these concepts (e.g., spatiotemporal properties)
- **What** we do want to **say about** these concepts (e.g., find a dataset Dx in timeframe Tx and location Lx providing ECVx information; find related services Sx using such dataset Dx in order to satisfy a defined SDGx).


**The fourth step consists in defining the classes and the class hierarchy**. Now the definition process really starts. Note that this step and the following one (properties) are tightly intertwined - they are typically done together- and are the most critical ones in the design process.
Classes are collection of **concepts with similar properties** within the designated domain (e.g., class of dataset, class of ECV, etc.). This is completely open for the ontology designer and they can decide the best way to define the classes. Furthermore, it is also open the way in which the class hierarchy is built: 

- **Top-down**: from the most general concept to the most specialized one
- **Bottom-up**: from the most specific classes (leaves of the tree) to the most general ones
- **Middle-out**: intermediate approach that allows starting with the clearest (typically most important) concepts and then build the hierarchy by generalizing and specializing additional concepts (classes).
Note that the hierarchy (or hierarchies) of classes is not strict and can overlap in some way, this is not a problem from the point of view of knowledge. A class can have more than one parent class if this really makes sense in the designated domain for our application. 


**The fifth step defines the properties (slots) for each class**. The internal structure of a class is determined by its **properties or attributes**. Most of them should come from step 3, from which we can take the remaining terms (not classes) and accommodate them in each class. The properties can be further divided into:
- *Intrinsic*: those properties that are specific to that class
- *Extrinsic*: those properties that are more general to other classes (e.g., name, location)
- Relationships with other classes (individuals) 
Obviously, a subclass inherits the properties of the parent class.
After this step, together with the previous one, most (if not all) of the competency questions created in step 1 should be capable of being answered.


**The sixth step refines the properties by defining their constraints**. Constraints are sometimes also called **restrictions or facets** and simply describe (restrict) the set of possible values of a given property. Several common facets are:

- *Cardinality*: indicates how many values a property can have. Depending on the system, this can vary between single/multiple cardinality and minimum and maximum cardinality.
- *Value-type*: Some examples are String, Number, Boolean, Enumerated and Instance
- *Domain and range*: allowed classes for properties of type Instance are called a range for that property. The domain, on the other hand, is the set of classes to which a property is attached.
There are other ways of characterizing properties (e.g., *transitive, functional, asymmetric*, etc.), but we will not dig in those aspects for the moment.


**The final (seventh) step creates the instances for the different classes**. The process of defining an instance (individual) implies:
- Selecting the target class
- Creating an instance of that class (the Instance will have a property type with the value of the class, similar to OOP)
- Filling the properties of such class (here the individual can be related to other individuals/instances)


Bear in mind that this is an iterative process that repeats as long as you want; at any given step the ontology designer can go back and make a refinement. Note also that the world is continuously changing, and the produced ontology will probably need to be improved in the future to adapt to future applications.

</div>
<br/><br/>

## ECV Taxonomy
<div align="justify">
   
The ECV ontology has been created following the current online information provided by GCOS. It has been a **hard and tedious work** because there is **no repository of structured data** to extract the information automatically, and the information given in form of **PDF fact sheets** were ported manually as individuals of the ontology. The structure of the ECV ontology is depicted in the Figure below.    

<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/ecv_ontology.jpg" alt="ECV Ontology" align="center" />
</p>

This ontology is focussed on **ECVs (Essential Climate Variables)**, which are the main entities and whose properties relate to other entities:
-	ECVs pertain to a **domain**, which can be **Atmosphere, Land** and **Ocean**, considered *first level* domains. Each domain, according to GCOS, has some *second-level* domains:
    -	The Atmosphere first-level domain includes **Surface, Upper-Air** and **Atmospheric Composition** second-level domains.
    -	The Land first-level domain includes **Hydrosphere, Cryosphere, Biosphere** and **Anthroposphere** second-level domains.  
    -	The Ocean first-level domain includes **Physical, Biogeochemical** and **Biological/ecosystems** second-level domains.
In summary, there are **54 ECVs** split among these 10 second-level domains as of 2022. This categorization is subject to be changed by GCOS in a near future, but no further information is provided in this regard by this organization. We think that by having a structed way of handling the information the update (in fact, any update) will be more comfortable, safer and automatic.  

-	ECVs are also assigned to a **scientific area**, somehow also related to the domain, but with its own independent meaning. These scientific areas were given by CGOS and to our knowledge do not follow any official taxonomy. Some examples are: *Hydrosphere, Physical Properties, Energy and Temperature, Carbon cycle and other GHGs*, etc.

-	ECVs have one or more **ECV Steward** assigned. They are (voluntary) representatives for each ECV, **in charge of keeping track of all related information** (mainly data sources and products) for a given ECVs. An ECV steward can be assigned to more than one ECV (typically if they fall under the same domain or scientific area). Unfortunately, the current information provided by GCOS concerning the ECV stewards seems **very limited and probably not updated**. For each ECV, you basically get a name (o more) for the ECV steward, but no proper contact information. In terms of ontologies, it seems impossible here with the given info to use any available contact ontology or FOAF ontology.  In the best case, but not for all ECVs, GCOS provides an [online list](https://gcos.wmo.int/en/terrestrial-observation-panel-climate/ECV-Stewards) of ECVs, associated stewards and their affiliations; however, the status is as of September 2020.

-	ECVs have a series of associated **data sources** that provide information for such ECV. The data sources are classified under four types: **in situ data, gridded in situ data, Reanalysis data and satellite data**.  Apart from this category, a data source has a name (typically the name of the provider) and a weblink to access the datasets.

-	ECVs have one or more **products** associated, each one with a **name, a description and a set of requirements**. A requirement unit covers various variables, such as **frequency, resolution, required measurement uncertainty, stability and related standards/references**.

While inserting the 54 ECV individuals in the ontology the name has been respected and kept from GCOS. Moreover, links to official icon and PDF factsheet has also been included as part of the properties of each ECV.

<br/><br/>

</div>   


<br/><br/>



## SDG taxonomy
<div align="justify">

The United Nations (UN) provides a platform for [linked data services](http://metadata.un.org/?lang=en) that is hosted by the Dag Hammarskjold Library. Currently it only hosts two resources:

-	**UNBIS Thesaurus**: it contains a list of terms that are used in indexing and cataloging documents and other material relevant to UN. This is not particularly relevant for our EIFFEL ontology.
-	**Sustainable Development Goals (SDGs)**: The [web list](http://metadata.un.org/sdg/?lang=en) includes all 17 SDGs together with their targets and indicators. This information seems relevant because it can be **linked with datasets from the EO field**. In other words, datasets associated to the EO world can be used to develop EO applications which probably aim at targeting one SDG or, more specifically, one of the targets and indicators. 

As this online repository didn't provide a structured file to process the data, we contacted the Dag Hammarskjold Library to request for JSON or OWL files. Fortunately, they provided a [GitHub repository](https://github.com/UNStats/LOD4Stats) including the requested and additional information. We will provide here just a brief summary to understand its meaning as part of the EIFFEL ontology.
The general process is depicted in the Figure below and considers three main use cases:

-	**Dataset description**: by using metadata and promote discoverability. It considers schema.org or DCAT annotations as well as CSVW. Datasets might also be tagged with concepts from other taxonomies in order to generally contextualise the dataset. For SDG they considered UNBIS and Eurovoc (multilingual thesaurus managed by the Publications Office of the European Union).
-	**Data description**: by expressing statistical data in linked data compliant formats. It considers RDF Data Cube vocabulary and SCOVO (Statistical Core Vocabulary) as well as spatiotemporal concepts.
-	**Content linking**: by associating different content types in a meaningful way. It involves finding similarity among different items based on their semantic annotations.

<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/sdg_approach.jpg" alt="SDG approach" align="center" />
</p>

The **SDG ontology** is the core part and implements the structure of the SDG goal-target-indicator-series hierarchy, as depicted in the Figure below. The ontology by itself it pretty simple and straightforward, and uses the SKOS core vocabulary, which is a widely used W3C standard employed by taxonomies and thesauri. The formal list of classes, properties and data types can be found in the [official website](http://metadata.un.org/sdg/ontology?lang=en).

<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/sdg_ontology.jpg" alt="SDG ontology" align="center" />
</p>

The **SDG taxonomy** defines the different individuals for the different classes (goal, target, indicator, series). Moreover, it includes mappings (via *skos:exactMatch property*) to external vocabularies:

-	UNBIS and Eurovoc
-	Matches with the SDG Interface Ontology (SDGIO), another SDG initiative to link SDG concepts with other vocabularies and ontologies
-	Matches with SDG goals in [Wikidata](https://www.wikidata.org/wiki/Q7649586) 


<br/><br/>

</div>








## EO Taxonomy
<div align="justify">
   
*Note: The information presented here is extracted or summarized from deliverable D4.3 - Assessment of Copernicus Uptake (Update of the user-oriented taxonomy) of the CopHub.AC H2020 project (Copernicus Academy Hub for Knowledge, Innovation and Outreach).*


</div>   


### 1. Introduction
<div align="justify">

In an attempt to bring services from the EO sector to their markets an EO taxonomy was created for several reasons, among others:

- 	It is a tool to improve the **understanding between communities**
-	It follows the process of **naming, classifying, categorizing and structuring** EO services and products
-	It provides a clear and **common description** of the knowledge landscape (ontologies, taxonomies, associations among terms, keywords, etc.)

In summary, it tries to somehow address the following question: **how can end users know which EO services are available for their needs in their specific activity?**

The **taxonomy** effort is a process of **naming and classifying** the EO services and products as a tool to improve the understanding between communities while the specific **ontology** analysis is a process of defining **vocabulary, representation of knowledge and making relationships**.

Though there are some partial taxonomy approaches, no EO standard exists today. The EO taxonomy tries to harmonise them in a hierarchical perspective, but also providing relevant aspects such as: 
-	verbs to define the object
-	verbs to communicate the actions that the final users need to understand in the elaboration of the services


|DIKW|Question|Description|
|---|---|---|
|Data & Information|**What** data?|Refers to geospatial data content, including its quality and usability. How the data is consistently (temporally/geographically) collected and how it is 'made' with a certain level of accuracy and confidence (spatial, temporal and spectral resolution). The validation and uncertainty assessment are a crucial requirement from the end-user perspective of a satellite data product.|
|Knowledge|**How** and what type of access? |Final or intermediate users request the information be structured in some meaningful way so as to convey facilitate decision making. The data are represented in such a way, e.g., accessing and integrating the defined data layers to produce geospatial information, developing data models as to allow a justifiable belief in the user, through which decisions can be made|
|Wisdom|**Why** the user needs that information? What type of EO user?|It is related to the user of the information products derived from the data (as well as data models) across vertical markets but also amongst key user communities. The wisdom generated through the EO data service provision is the justifiable belief in the state of the world, based on the knowledge generated from the data, from which sound decisions can be made|


A common language is defined in terms of:

-	**Data collection**
-	**Data processing**, including pre-processing (levels 0,1) and processing (levels 2,3,4)
-	**Data analysis**, as part of data processing, but due to its relevance, considering three realms:
    -	Descriptive (what happened?)
    -	Analytics (what will happen?)
    -	Prescriptive (how can we make it happen?)
-	**Data use** (aggregation, visualization, distribution)
-	**Standardised verbs** (assess, detect, forecast, map, monitor and analyse)
-	**Thematic** (technician/expert view) **approach**. This is broken down into: 
    -	Domain (level 1)
    -	Area (level 2)
-	**Market **(customer/user view) **approach**
    -	Market (level 1)
    -	Sector (level 2)
-	**EO service** as level 3 convergence from market and thematic approach. 
-	**EO applications**, products and parameters and essential variables as level 4 entities

Markets and thematic views are briefly described in the next sections.
During the update of the EO taxonomy, EARSC also studied other structures, taxonomies and the potential mappings among concepts and/or categories, such as:

-	**Copernicus Entrusted Entities taxonomy**: there 6 areas (atmosphere, marine, land, climate change, security and emergency), but are not focussed on the uptake language of the users. They all six can be integrated at L1 or L2 of the EO taxonomy.
-	**GSA's (now EUSPA) GNSS taxonomy**: up to 16 areas. Some of them map well to the EO taxonomy (agriculture and forestry, energy, infrastructure, etc.), but others (aviation, rail, drones, geomatics) are more indirectly related to EO services.
-	**GEO Societal Benefit Areas (SBAs)**: there are 9 areas here intended to provide support for decision making. The EO taxonomy market perspective offers alignment with the full set of SBAs.
-	**International organizations' approaches**: such as OECD topics, Global Industry Classification Standard (GICS), Industrial Classification Benchmark (ICB). Thomson Reuters Business Classification (TRBC), Eurostat and World Bank. All these structures present good alignment with the market perspective
-	**Commercial service providers**
-	**H2020 projects**: such as NextGEOSS and e-shape. NextGEOSS provides [13 thematic areas](https://catalogue.nextgeoss.eu/thematic-areas).  The [e-shape project](https://e-shape.eu/ ) covers 7 thematic areas (agriculture, health, renewable energy, ecosystem, water, disasters and climate) aligned with UN Sustainable Development Goals (SDGs) and GEO SBAs. By using the EO taxonomy, one may link and expand the E-SHAPE pilots, currently presented in SDG silos, to a (potential) user community.
-	**ENVRI community**:  the community of [Environmental Research Infrastructures](https://envri.eu/research-infrastructures/ ), projects, networks and other diverse stakeholders  basically defines 4 main domains (atmospheric, marine, solid earth and biosphere).

<br/><br/>

</div>   

### 2. Market view
<div align="justify">

The market view provides a tool to help classify and understand the markets for EO services as well as to define the type of customer. The representation of market stakeholders in the use of value-added services and applications is illustrated in the Figure below, and it focuses on user needs and the use of Earth observation from the users' point of view.

<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/eo_ontology_marketView.jpg" alt="EO ontology (market view)" align="center" />
</p>

A descriptive table is provided for each leaf/sector, but we will show just one example for environmental and climate in the table below


|Sector|Users|Needs relevant to EO services|
|---|---|---|
|Environmental ecosystems & pollution|Environmental ecosystems & pollution users include coast guards, ambulance services, fire services, police services, civil protection organisations and rescue services|-	assist with the preservation of the natural environment such as reservoirs, inland water monitoring, water management systems (hydrological, hydrogeological maps, water point);<br/> -	solutions that safeguard the environment such as environmental impact assessment, strategic environmental consultancy, sustainability, waste & resources);<br/> -	resilient & sustainable ecosystems including continuous monitoring of ecosystems such as wetlands; |
|Meteo & climate|Meteorologists in a range of downstream sectors |-	disaster resilience and assessing extreme weather;<br/> - monitor, understand, evaluate and assess the impact of the climate change;<br/> -	prediction of conditions of atmosphere reliable weather forecasts;<br/> - mitigation actions preventing/reducing the emission of greenhouse gases into the atmosphere;<br/> - climate change data modelling (aerosol, biomass, cloud, fire, greenhouse gases (GHG), glaciers, ice-sheets, land cover, land surface temperature, ocean colour, ozone, permafrost, salinity, sea ice, sea level, sea state, soil moisture, snow, sea surface temperature (SST), water vapour);<br/> - renewable energy production prediction, all kinds of commodities market trading, inventory management|


The **market view** is depicted in the Figure below. The basic overall concept is **View**. Though theoretically it could be possible to have multiple views, the EO taxonomy only defines two of them: market and provider view. We will focus first on the **MarketView**. The class contains one single individual to define the market view as defined by EARSC. This directly connects with the next class, **Market**. A MarketView is basically defined by a set of Markets it covers. EARSC defines 8 different markets (individuals of the Market class) in its latest version. This would allow to define other MarketView individuals with different Market individuals (e.g., previous versions of EARSC) or add additional Market individuals as the market evolves and new releases appear.
The MarketView is also defined by the different operations or needs that the user might have. This is represented by the **UserNeed** class. EARSC defines (in its latest version) 6 main needs, as depicted in the Figure below. These six needs are also mapped to another simple DIKW categories. Basically, both are ways of characterizing the user need and the added value that is to be provided (e.g., an 'assessment need' will provide more added value than a 'detection need', and will probably imply a more complex service deployment in terms of software and/or hardware).

<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/eo_market_view.png" alt="EO ontology (market view)" align="center" />
</p>

Each market individual is composed of one or several Sectors, represented by the **Sector** class. It is a way of further reducing the scope the better define the target segment. EARSC defines 26 sectors (26 Sector individuals) in its latest version.  
Each Sector defines a set of potential users or stakeholders interested in consuming EO services related to this specific sector. Such user profile is represented by the class **UserGroup**, and there is a one-to-one mapping between sector and user group. The userGroup concept has not been developed by EARSC and could have been defined as an internal part of Sector, but splitting both concepts give more flexibility to the ontology. The userGroup class is characterized by one or more EO needs (**EONeed** class), which are generic expectations from the users within a given sector in terms of exploiting EO data. EARSC briefly defines several EO needs for each sector.
Finally, the concept of EO service (**EOService** class) is also included in this market view. However, this concept is better explained by EARSC in the thematic perspective, as will be described next.


<br/><br/>

</div>   


### 3. Thematic view
<div align="justify">

The thematic view provides a tool to help describe and classify the services and products that are offered by the service providers. The 'thematic perspective' deals unambiguously with a thematic application area (e.g., agriculture), which is not linked per se to the processing or acquisition of EO (or indeed, other kinds of) data or, quite naturally, to activities further upstream (i.e. satellite and sensor design or manufacture), instead the source focuses on concepts, challenges and applications in a specific domain (e.g. agriculture) or thematic segment (agriculture monitoring).
The updated structure of the taxonomy thematic viewpoint allows for 4 levels/tiers in the description of EO services from the supplier side point of view. The Table below presents the EO services structure.



|Level|Name|Coverage|Description|
|---|---|---|---|
|L1|**Thematic classes (DOMAIN)**|Single block of knowledge (big category of objects)|Largest conceptual category (typically nouns) covering all known areas of EO services from the supplier's point of view. The EARSC taxonomy contains 6 classes. |
|L2|**Thematic segment (AREA)** |Set of EO services (Greater detail of objects)|Classifies concepts in greater detail, i.e. different segments. The upgrade proposes 31 areas compared with the 25 in the previous taxonomy.|
|L3|**EO Service (SERVICE)** |Purpose of the information |EO services (sometimes considered applications by service providers) propose an action or a sequence of actions (specific events appropriate in a given situation, e.g., 'assess the environmental impact of farming'. For example, it unifies major entities such as environment, agriculture or deeper in granularity such as crops. The range today covers more than 80 services.|
|L4|EO Application |Specific for a geographical area, timeline, etc.| This level presents set **keywords** which in effect define the **products** which make up a service (key words are also considered in our taxonomy to represent **products, parameters or essential variables**).|


It must be noted that within both the service provider and user communities the terms service and application tend to be used interchangeably. A **service** is defined as being a process incorporating e.g., sets of algorithms, EO data, model outputs etc. that are applied to give information or knowledge of the Earth, and an **application** as a specific implementation of that process.
The Figure below represents the upgraded taxonomy with the Thematic (Supplier) perspective

<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/eo_ontology_providerView.jpg" alt="EO ontology (provider view)" align="center" />
</p>

For each specific domain (level 1), specific set of actions (verbs) are identified for each of the thematic areas (level 2). For example, for the **atmosphere and climate change**, we have the following description:

-	*The atmosphere and climate domain encompass all atmosphere and climate change focused services/applications which* **assess, monitor, forecast** *and provide timely, continuous and independent data (e.g., emissions, climate forcing, greenhouse gases, reactive gases, O3, solar UV radiation, aerosols...) which affect temperature, air quality and the transmission of solar radiation. These services/applications closely monitor each of the Earth's different subsystems and help to better* **understand and evaluate** *the impact of climate change and its impacts on the atmosphere, meteorology or hydrological cycles.**

And the different thematic areas will have the following thematic keywords

|Thematic area|Thematic keyword|
|---|---|
|**atmosphere** | ...quality-controlled information related to air composition, pollution and health, solar energy, greenhouse gases (GHG) emissions and climate forcings |
|**Climate change** | ...long-term datasets (also linked to weather forecasts) on key indicators of climate change systematically generated and preserved to better understand climate change and associated adaptation and mitigation measures and risk management (i.e., large-scale ecological response to global climate change such greening of the Arctic). The assessment of climatic variations may persist over decades or more. This is measured through geophysical quantity/quantities associated with climate variations and change as well as the impact of climate change onto Earth (time series analysis, anomaly detection, missing data reconstruction, forecasting). Climate change is triggering factors on geohazards or direct effect for many land and ocean processes.|
|**metereology** | ...seasonal preparedness, forecasting of meteorological variables e.g. air temperature, wind, humidity, cloud coverage, precipitation and evapotranspiration (related to numerical weather prediction models, in-situ observational data and machine learning techniques). |


The **provider view** is depicted in the Figure below. One might find similarities in the way the ontology is built compared with the market view:

-    There is one single **ThematicView** individual (ThematicView class) that derives from the View class.  
-    The ThematicView can be broken down into several **Domains**. This is the first level of segmentation, and EARSC defines *6 individuals*. It is equivalent to the Market class in the market view, but here it is the provider who defines the different segments.
-    Domains are decomposed into **Areas**, which is the second level of segmentation, and EARSC defines *31 individuals*. It is equivalent to the Sector class in the market view. 

<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/eo_provider_view.png" alt="EO ontology (provider view)" align="center" />
</p>

The **EOService** class represents the third level of segmentation according to EARSC, and it is a high-level and general representation of a service using EO data. Currently EARSC defines more than 80 services for the different areas. In order to better understand such concept, let's take an individual from the ontology as example:

<p align="center">
<img src="https://github.com/benmomo/eiffel-ontology-doc/raw/main/docs/img/eo_service_example.png" alt="EO ontology (service example)" align="center" />
</p>

As can be seen, the EOService individual **#EOService_001** is associated to the **#AtmophereArea** individual. This service is further defined with the action to be performed on the associated Area (*relatedAction* property) as well as a further refinement of the action (*type* property). A short description allows to better understand the aim of this particular service. 
The thematic view elaborates further the concept of service by introducing a *fourth* segmentation layer, called EO application (**EOApplication** class). According to the EARSC, it is expected to be a particular implementation of the EO service (e.g., at a particular location, within a particular time range, etc.). EARSC does not define any EO application; however, any implementation available in the market or elsewhere is supposed to fall under this category:

-    Use cases from the EIFFEL project
-	 Use cases from other projects (e.g., e-shape projects)

Being an EO application a specific implementation of an EO service, it is further composed of a product (**Product** class) and a set of parameters (**Parameter** class). The concept of Product is not clearly defined by EARSC, but it points in the direction of a product offer and how it could be described. No example was provided so the concept still remains quite open and flexible.
The parameters relate to the inputs required or used by the service (application) to generate the result, being one of such inputs the **Essential Variables**(EVs). Those variables are critical to observe and monitor different aspects of the Earth system, covering oceanography, climatology, biodiversity and geodiversity.  Considering the core domain of the EIFFEL project, the Essential Climate Variables (ECVs) are of nuclear importance.   
The previous Figure also depicts links between the given concepts of the EO taxonomy and the previous **SDG** and **ECV** ontologies. ECVs can be directly included as a subclass of EVs. The SDG ontology, through an SDG or a target concept, can be linked as an additional property of an EO service and/or EO application.


<br/><br/>

</div>   


### 4. Alignment with Copernicus
<div align="justify">

The alignment is summarized in the table below.



|EO thematic perspective|Copernicus Service|Copernicus components/areas/applications|
|---|---|---|
|Atmosphere & climate EO services | Copernicus Atmosphere Monitoring Service (CAMS) | -air quality and atmospheric composition <br/> - ozone layer and ultra-violet radiation <br/> - emissions and surface fluxes <br/> -solar radiation <br/> -climate forcing <br/> |
| | Copernicus Atmosphere Monitoring Service (CAMS) | -support adaptation and mitigation policies by providing consistent and authoritative information about climate change (assessment of climate change impacts, risk management, sustainable human iterations within the environment...)|
|Built environment EO services | Services related to Copernicus Land Monitoring Service (CLMS) but specific for built environment  | |
|Disasters & geohazards EO services  | Copernicus Emergency Management Service (Copernicus EMS) | - a mapping component; (e.g. as digital or printed map outputs) <br/> - an early warning component (The European Flood Awareness System (EFAS), The European Forest Fire Information System (EFFIS), The European Drought Observatory (EDO), Global Flood Awareness System (GloFAS), Global Wildfire Information System (GWIS) and Global Drought Observatory (GDO)... |
|Land EO services | Copernicus Land Monitoring Service (CLMS)  | - systematic monitoring of biophysical parameters <br/> - land cover and land use mapping <br/> - thematic hot-spot mapping <br/> - imagery and reference data </br>  |
|Marine EO services | Copernicus Marine Environment Monitoring Service (CMEMS)  | - Marine safety <br/> - Marine resources <br/> - Coastal and marine environment <br/> - Weather, seasonal forecasting and climate <br/>  |
|Safety & security EO services | Copernicus security service(s)  | - crisis prevention, preparedness and response <br/> - Border surveillance <br/> - Maritime surveillance <br/> - Support to EU External Action <br/>  |



<br/><br/>

</div>   


## EIFF-O
<div align="justify">
   
TBC 


<br/><br/>

</div>   


<br/><br/>


