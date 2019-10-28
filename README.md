# Chicago Food Inspection

# Abstract

Food is essential to human lives, in that it not only provides nutrients for survival, but also satisfies the need for social bonding: people like to gather around meals and beverages, be it going out to eat and drink, or over a home-cooked meal. Either way, food facilities such as restaurants, pubs, coffee shops, and grocery stores are a major part of people's daily lives. 
However, according to the WHO, 1 in 10 people fall ill every year from eating contaminated food, and 420 000 people die each year as a result. This risk is especially high when eating out at restaurants rather than cooking your own meals. Therefore, monitoring and maintaining food safety in food facilities is crucial for the health and general well-being of the population. 
Chicago is the third largest city in the United States and is home to more than 16,000 food establishments. The Chicago Department of Public Health’s Food Protection Program aims to ensure that all food preparation in every food establishments across the city is done in compliance with City ordinances and regulations by conducting recurring science-based inspections. 
The Chicago Food Inspection dataset will allow us to determine food safety levels in Chicago and what affects them, as well as predict if a food facility will pass the inspections, and maybe make some generalizations that apply beyond the city of Chicago. In other words, we want to obtain more insights into food-related risks in Chicago and the attention food establishments pay to the health of its customers. The chosen dataset gives us information from which we wish to extract interesting patterns for our study. 

# Research questions

   - Is food safety getting better with time?
   - Do chain restaurants pay more attention to the safety of their customers? 
   - Study per facility type: are some facility types safer than others? 
   - What is the relationship between establishments location and safety and how can we realize an interactive map of Chicago that            highlights it?
   - Can we predict if a facility will pass an inspection on the basis of the violations and other factors such as facility type,            location, etc? 
   - Can we find seasonal patterns i.e. are some violations more likely to occur during certain months of the year?
   - Which inspection types are more likely to be failed than others?
   - What facility (restaurant, grocery store etc.) is more likely to present a particular type of violation?

# Dataset

We decided to use the Chicago Food Inspections dataset provided by the City of Chicago Open Data platform. 
It is a relatively small .csv dataset (only 220 MB) which contains details about food establishments inspections carried out in the city of Chicago from 01.01.2010 onward. It provides useful information about various aspects of the inspections such as: facility type, violation type, inspection type, risk category or location.
The fields are for the most part straightforward. The only column that needs extra processing is the “Violations” column. It stores the encountered violations as free text comprising: the violation code and title followed by comments. The challenge here is to parse the contents of this column using natural language processing techniques in order to identify key words in the comments that can be used to discover new patterns and trends.
Moreover, some columns must be discarded because they contain either redundant or useless information. For example, the “Latitude” and “Longitude” columns are to be discarded because the “Location” column already contains these information. Similarly, the City and State columns must be discarded since the inspections only occurred in Chicago.
Another hurdle in managing the data is the fact that on 7/1/2018, the Chicago Department of Public Health’s Food Protection unit changed its definition of violations. Thus, we will have to conduct extensive research about the violation types, how they changed and how the old ones can be mapped to the new ones. Besides, in order to avoid artifacts of the redefinition of violation types when studying changes in long term trends, two filtered views were created: one showing inspection records through 6/30/2018 and one showing inspection records from 7/1/2018 forward. We thus may use these two filtered datasets for our study. 
Finally, the dataset may still contain duplicates inspection reports. Hence, we will also have to add a step in our pre-processing pipeline to account for this inconvenience.

# A list of internal milestones up until project milestone 2

**Week1:** 

   - Download the dataset and set up the work environment.
   - Remove useless columns.
   - Figure out how to identify duplicate records and remove them.
   - Read further documentation of the dataset in order to understand how to handle and map the changes in the `Violations` column.
   - Check if the geomarkers are accurate enough for the later Map visualizations.
      
**Week2:**

   - Perform preliminary analysis using various statistical measures (histograms, inspect feature distributions).
   - Identify the main patterns and trends.
   - Build aggregations of records based on different common features and draw some initial conclusions.

**Week3:**

   - Perform further analysis based on the trends we observed in Week2.
   - Find hidden correlations between features and what information they provide that can be useful for the data story.
   - Find adequate visualization tools to support our observations.

**Week4:**

   - Complete the analysis and exploration stage.
   - Tidy up the notebook, add explanatory comments, highlight conclusions, clean up and filter the plots.
   - Decide what the upcoming goals are for milestone 2 and write a comprehensive plan.

Milestone 2: November 25

# Questions for Tas

- Are there tools other than Folium that we could use to realize an interactive map?
- What NLP tools/libraries are most appropriate to process the “Violations” column’s contents in order to extract important key words?
- Which of our research questions seem most promising/reasonable and should wepursue first?


