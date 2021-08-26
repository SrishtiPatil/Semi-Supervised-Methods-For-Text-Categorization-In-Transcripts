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
Speaker 1: Hi i am Srishti<br />
This can be found in file [Data_Prep.ipynb](https://github.com/SrishtiPatil/supervised-methods-for-text-categorization/blob/main/Data_Prep.ipynb)

**Data Tagging/Dictionary Defination:**
Generation is a process of identifying the topics and their associated tags in the conversations.<br />
For example The tags in - “Are you fan of Google or Microsoft? Both are excellent Technology they are helpful in many ways. Google is a leading alphabet subsidiary and Chrome OS is one of the best product. Did you know google has hundreds of life quotes to cut the grass in the past?”
are **Org** - Google, Microsoft, Alphabet and **Cardinal** - hundreds.<br />
This can be found in file [Tag_Generation.ipynb](https://github.com/SrishtiPatil/supervised-methods-for-text-categorization/blob/main/Tag_Generation.ipynb)

**Topic and Tags assignment**:
Once the dictionary is defined to assign the tag to the entire dataset that we have. First we
need to separate the speaker and the message, assign the tags to the message then convert it
to a tuple, and store it as tagged training data set<br />
This can be found in file [Topics_and_Tagging.ipynb](https://github.com/SrishtiPatil/supervised-methods-for-text-categorization/blob/main/Topics_and_Tagging.ipynb)
