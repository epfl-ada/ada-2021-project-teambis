# Can differences in self-confidence between men and women be observed from what they say?

## 0 - Link to Data Story

https://naomi-iizuka.github.io/

## 1 - Motivation

Sociology studies have regularly analyzed how self-confidence varies amongst the genders, and overall results generally show that men tend to have higher self-confidence than women: a phenomenon that has been dubbed the “Confidence Gap”. Studies show that women usually underestimate their abilities, expect to be discovered for their incompetence at any time and often experience the “Imposter's Syndrome”, a sociological phenomenon where a person thinks they do not deserve their position. The main aim here is to determine whether this “Confidence Gap” is observable throughout quotations found in the Quotebank database for the year **2020**. Following this, an interesting analysis would be to see whether profession could influence confidence, at least based on the provided expressions. We will thus compare quotations extracted from of US Congresswomen and US women who are not a Congress. Focus on a single gender should allow us to solely observe any profession-related variations.

## 2 - Project Interrogations

For this project, we will analyse the provided data and ultimately try to answer to the following interrogations: 

* ***Is there a difference in the expression of confidence between men and women?***
* ***What are the most used phrases or expressions by confident vs less confident speakers?***
* ***Does profession involving rhetoric influence results as well?***

In addition to the quotation-centric Quotebank data, we will use the additional information on speakers and the QID label descriptions provided by the ADA teaching staff.

NB : The article on which we are going to extract these confidence-relating phrases and on which we will base the comparison will be provided on the team’s GitHub.

## 3 - Analysis

### 3.1 - Pre-processing
Our first step consisted in pre-processing and performing a first clean of the initial dataset (ensuring that there is a speaker associated to the quote, that there is a unique qID per speaker, that a speaker has at least one quotation, …) in order to extract only the relevant information, such as speaker name, speaker qID, quotation, gender, … We also had to add or clarify certain variables such as whether the speaker was from the USA or was a Congressperson, to facilitate further analysis. 

#### 3.2 - Confidence Scores!
The first part consisted in analyzing each quote and assigning a confidence score for each, which will then be used to establish an overall confidence score for a given speaker. Basing off a sociology study that had experimentally associated confidence scores to certain key phrases such as "I believe", "I think", "I am sure", … ,  we were able to parse the dataset having tokenised these key phrases and thus find the number of occurences of these key words in each quotation. Chunking of the processed dataset was necessary in order to facilitate extraction of information. It is important to mention that the study adapted a score for key phrases in the present and in the past tense. We thus obtain an output table that contains qID, the quotation and the confidence_score. The confidence score was determined by simply retrieving the maximum value displayed by the quote. 
Following this, merging the datasets containing the quotations' information with the speakers' dataset allowed us to summarise all elements relative to the speakers and namely allow us to determine an overall confidence score for each speaker. The speakers' confidence scores were determined by, once again, retrieving the maximum confidence score returned by each of his·her quotations.

### 3.3 - Are men really more confident than women??
Having now obtained each speaker's score, we were able to plot and analyse many elements and subsets of this processed dataset. Various plots were used in order to visualise both the distributions (histograms, kernel density estimates, …) and key numerical values such as mean, max and min, standard deviation (boxplots, …) .The graphical analysis was performed in 3 parts:

#### *How are confidence scores distributed?*
The idea here was to visualise:
- Mean Score Distribution
- Max Score Distribution
- Standard Deviation Distribution

#### *How are expressions distributed?*
The idea here was to visualise:
- Distribution of expressions from all speakers
- Distribution of expressions from male and female speakers
- Distributions of expressions from confident and non-confident speakers

#### *How do men/women and US Congresswomen/Non-Congresswomen compare?*
By plotting the maximum confidence scores of a given subset of speakers against another subset of speakers, we were able to determine which subgroup of speakers appeared more confident based on the expressions found in Quotebank's quotations. In order to assess significance of the difference in confidence, Student's t-tests were performed for each comparison of subgroups.

## 4 - Proposed Timeline

* Week 1:
  * Quotebank/2020 dataset wrangling
  * Extraction and pre-processing of the initial dataset

* Week 2:
  *  Extracting and cleaning important information relative to quotes
  *  Extracting and cleaning important information relative to speakers
  *  Initial data visualisation (distribution of genders, distribution of speakers' DOB, …)

* Week 3:
  *  Association of confidence scores for quotes and for each speaker
  *  Semantic and syntactic comparison of quotes

* Week 4:
  *  Merging information of quotes and speakers
  *  Plotting and analysis 
  *  Optimisation and code cleaning

## 5 - Task Allocation

* Maëva: extraction of important information relative to quotes/speakers, merging information of quotes/speakers, attempts to include dataset from other years, final analysis, association of confidence scores
* Naomi: pre-processing, importing information from background study, final analysis, Data Story
* Florette: pre-processing, initial data visualisation, attempt of semantic comparison, plotting , final analysis, Data Story
* Alexy: initial data visualisation, syntactic comparison, plotting, final analysis
