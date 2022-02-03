# Tour Ontology Namespace  

## Index of Terms  

| **Classes:** |[Person](#sf01), [Place](#sf02), [Organization](#sf03), [Activity](#sf07), [Tour](#sf0701), [Business Entity](#sf031), [City](#sf024), [Continent](#sf022), [Country](#sf023)|  
| :------------|:----------------------------------------------------|  
| **Object Properties:** |[hasCapital](#sf045), [hasCity](#sf043), [hasContinent](#sf041), [hasCountry](#sf042), [hasPlansToVisit](#sf04011), [hasProvider](#sf046), [hasTour](#sf044)| 
| **Data Properties:** |[hasName](#sf051), [hasTourDescription](#sf053), [hasTourDurationInDays](#sf0521), [hasWikiDataEntry](#sf054)| 

___  

## Classes
### SF01
**Label:** Person  
**Description:** a human being.   
**Subclass Of:**  
**Disjoint with:** [Place](#sf02), [Tour](#sf0701), [Activity](#sf07), [Organization](#sf03)  
**Identifiers:**  [FIBO: Person](https://spec.edmcouncil.org/fibo/ontology/FND/AgentsAndPeople/People/Person)

___  

### SF02
**Label:** Place  
**Description:** a particular position, point, or area in space; a location.      
**Subclass Of:**  
**Disjoint with:** [Organization](#sf03), [Person](#sf01),[Tour](#sf0701), [Activity](#sf07)   
**Identifiers:**  

___  

### SF024
**Label:** City  
**Description:** a place where people live that is larger or more important than a town.  
**Subclass Of:**  [Place](#sf02)
**Disjoint with:**  
**Equivalent To:** [City](#sf024) *and* [hasCountry](#sf042) **exactly** 1 [Country](#sf023),  
   [City](#sf024) *and* [hasContinent](#sf041) **exactly** 1 [Continent](#sf022)  
**Identifiers:**  

___  

### SF023
**Label:** Country  
**Description:** a nation with its own government, occupying a particular territory.    
**Subclass Of:**  [Place](#sf02)
**Disjoint with:**  
**Equivalent To:** [Country](#sf023) *and* [hasContinent](#sf041) **exactly** 1 [Continent](#sf022)  
**Identifiers:** [OMG: Country](https://www.omg.org/spec/LCC/Countries/ISO3166-1-CountryCodes/Country)  

___  

### SF022
**Label:** Continent  
**Description:** any of the world's main continuous expanses of land.     
**Subclass Of:**  [Place](#sf02)
**Disjoint with:**  
**Equivalent To:** {Asia , Africa , Europe , 'North America' , 'South America' , Antarctica , Australia}  
**Identifiers:**  

___  

### SF03
**Label:** Organization  
**Description:** an organized group of people with a particular purpose.     
**Subclass Of:**  
**Disjoint with:** [Place](#sf02)  
**Identifiers:**  

___  

### SF031
**Label:** Business Entity  
**Description:** an entity that is formed to engage in business activities.      
**Subclass Of:**  [Organization](#sf03)  
**Disjoint with:**  
**Identifiers:**  [FIBO BE](https://spec.edmcouncil.org/fibo/ontology/BE/LegalEntities/LegalPersons/BusinessEntity)  

___  

### SF07
**Label:** Activity  
**Description:** a thing that a person or group does.     
**Subclass Of:**  
**Disjoint with:** [Place](#sf02), [Organization](#sf03), [Person](#sf01)  
**Identifiers:**  

___  

### SF0701
**Label:** Tour  
**Description:** a journey for pleasure in which several different places are visited.  
**Subclass Of:**  [Activity](#sf07)
**Disjoint with:** [Place](#sf02), [Organization](#sf03), [Person](#sf01)  
**Equivalent To:** [Tour](sf0701) *and* [hasPlansToVisit](#sf04011) **min** 2 [City](#sf024)  
**Identifiers:**  

___  

## Properties  
### SF045
**Label:** hasCapital  
**Description:** Capital city of the subject Country.  
**Characteristics:** Functional, Inverse Functional, Asymmetric, Irreflexive  
**Domain:** [Country](#sf023)  
**Range:** [City](#sf024)  
**Inverse Of:**   

___  

### SF043
**Label:** hasCity
**Description:** City belonging to the country or continent in question
**Characteristics:** Asymmetric  
**Domain:** [Country](#sf023) *or* [Continent](#sf022)  
**Range:** [City](#sf024)  
**Inverse Of:**  

___  

### SF041
**Label:** hasContinent
**Description:** continent for the city or country in question.
**Characteristics:** Asymmetric  
**Domain:** [City](#sf024) *or* [Country](#sf023)  
**Range:** [Continent](#sf022)  
**Inverse Of:**  

___  

### SF042
**Label:** hasCountry
**Description:** 
**Characteristics:** Asymmetric  
**Domain:** [City](#sf024) *or* [Continent](#sf022)  
**Range:** [Country](#sf023)  
**Inverse Of:**  

___  

### SF04011
**Label:** hasPlansToVisit
**Description:** place that a Tour plans on visiting.  
**Characteristics:** Asymmetric, Irreflexive    
**Domain:** [Tour](#sf0701)  
**Range:** [City](#sf024)  
**Inverse Of:**  

___  

### SF046
**Label:** hasProvider
**Description:** Tour Provider. Assuming tour packages are unique.  
**Characteristics:** Functional, Inverse Functional, Asymmetric, Irreflexive    
**Domain:** [Tour](#sf0701)  
**Range:** [Business Entity](#sf031)  
**Inverse Of:**  [hasTour](#sf044)  

___  

### SF044
**Label:** hasTour
**Description:** (Inverse) Functional property because seems reasonable to assume each provider will have slightly different tour package.   
**Characteristics:** Functional, Inverse Functional, Asymmetric, Irreflexive    
**Domain:** [Business Entity](#sf031)    
**Range:** [Tour](#sf0701)  
**Inverse Of:**  [hasProvider](#sf046)  

___  

