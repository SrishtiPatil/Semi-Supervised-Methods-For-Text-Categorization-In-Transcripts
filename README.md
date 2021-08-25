# Supervised methods for text categorization
**Objective:**
Make a model that would correctly identify topics that are being discussed in the transcripts.

**Data:** 
The data is a topical chat with Alexa in JSON format. The data has multiple conversations with
almost any random topic. The topics are not restricted to any particular domain and can range
from sports to politics, to leading organizations. The dataset contains human-human knowledgegrounded open-domain conversations. 

Source: https://github.com/alexa/Topical-Chat/tree/master/conversations

**Data Preparation:** 
The first task was to get the JSON object data into an alternate speaker format<br />
Speaker 0: Hi I am Amrit<br />
Speaker 1: Hi i am Nikhil/Srishti<br />
This can be found in file [Data_Prep_alexa_github.ipynb](https://github.com/SrishtiPatil/supervised-methods-for-text-categorization/blob/main/Data_Prep_alexa_github.ipynb)


**Data Tagging:**
As the approach chosen was Supervised Approach I needed to tag over 1800,000 rows. Each statement had more than one topic hence to avoid making it laborious I opted for a semi-supervised approach for tagging. I used the Spacy library for tagging each word. 
