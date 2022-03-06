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

TBC


<br/><br/>

</div>


## Related work
<div align="justify">
   
TBC (projects, ontologies, formats)


<br/><br/>

</div>


   


<br/><br/>

</div>



 
