# Semi-Supervised Methods For Text Categorization In Transcripts

**Objective:**<br />
Make a model that would correctly identify topics that are being discussed in the transcripts.

**Data:**<br />
The data is a topical chat with Alexa in JSON format. The data has multiple conversations with
almost any random topic. The topics are not restricted to any particular domain and can range
from sports to politics, to leading organizations. The dataset contains human-human knowledge-grounded open-domain conversations. 

Source: https://github.com/alexa/Topical-Chat/tree/master/conversations

**Data Preparation:**<br />
The first task was to get the JSON object data into an alternate speaker format<br />
Speaker 0: Hi I am Amrit<br />
Speaker 1: Hi i am Srishti<br />
This can be found in file [Data_Prep.ipynb](https://github.com/SrishtiPatil/supervised-methods-for-text-categorization/blob/main/Data_Prep.ipynb)

**Data Tagging/Dictionary Defination:**<br />
Generation is a process of identifying the topics and their associated tags in the conversations.<br />
For example The tags in - “Are you fan of Google or Microsoft? Both are excellent Technology they are helpful in many ways. Google is a leading alphabet subsidiary and Chrome OS is one of the best product. Did you know google has hundreds of life quotes to cut the grass in the past?”
are **Org** - Google, Microsoft, Alphabet and **Cardinal** - hundreds.<br />
This can be found in file [Tag_Generation.ipynb](https://github.com/SrishtiPatil/supervised-methods-for-text-categorization/blob/main/Tag_Generation.ipynb)

**Topic and Tags assignment:**<br />
Once the dictionary is defined to assign the tag to the entire dataset that we have. First we
need to separate the speaker and the message, assign the tags to the message then convert it
to a tuple, and store it as tagged training data set<br />
This can be found in file [Topics_and_Tagging.ipynb](https://github.com/SrishtiPatil/supervised-methods-for-text-categorization/blob/main/Topics_and_Tagging.ipynb)

**Algorithm Application:**<br />
Since the data was multilabel, the target variable needed to be separated(similar to one-hot encoding). To achieve this MultilabelBinariser was used. This converted the tagged variable into a matrix with 18 columns(18 tags).<br />
Since the approach is supervised classification algorithms chosen are Naive Bayes, Linear SVC, and Logistic regression. As the data had multiple labels the approach is One vs Rest (OVR) for all the algorithms.<br />
This can be found in file [TopicClassificationAlgo.ipynb](https://github.com/SrishtiPatil/supervised-methods-for-text-categorization/blob/main/TopicClassificationAlgo.ipynb)

**Results:**<br />
The validation accuracies are much better than expected. For Tags like Person(which could have
any name and not all names are included in the training dictionary), Geo-Political Entity the
scores are low. But for generalized tags, the scores are satisfactorily high. Of all the 3 models
applied **One vs Rest-Naive Bayes** gave the best accuracy.<br /><br />
The results of algorithms performance is attached below:<br /><br />
![Accuracy](https://user-images.githubusercontent.com/24762755/130923138-db64c847-ea6e-4143-b6ed-61300dba7d7b.jpg)

