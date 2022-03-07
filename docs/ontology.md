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


**The fourth step consists in defining the classes and the class hierarchy**. Now the definition process really starts. Note that this step and the following one (properties) are tightly intertwined – they are typically done together- and are the most critical ones in the design process.
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


## SDG taxonomy
<div align="justify">

TBC


<br/><br/>

</div>


## ECV Taxonomy
<div align="justify">
   
TBC 


<br/><br/>

</div>   


<br/><br/>





## EO Taxonomy
<div align="justify">
   
TBC 


<br/><br/>

</div>   


<br/><br/>




## EIFF-O
<div align="justify">
   
TBC 


<br/><br/>

</div>   


<br/><br/>


