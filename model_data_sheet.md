# Datasheet 


## Motivation

- For what purpose was the dataset created?

The dataset was created for the purpose of the Kaggle competition titled 'Linking Writing Processes to Writing Quality', sponsored by the The Learning Agency Lab. 
- Who created the dataset (e.g., which team, research group) and on behalf of which entity (e.g., company, institution, organization)? Who funded the creation of the dataset?

The dataset was created on behalf of competition host Vanderbilt University, a private research university in Nashville, Tennessee together with ​The Learning Agency Lab, an independent nonprofit based in Arizona. The funding of the dataset and competition was additionally supported by the Bill & Melinda Gates Foundation, Schmidt Futures, and Chan Zuckerberg Initiative.

 
## Composition

- What do the instances that comprise the dataset represent (e.g., documents, photos, people, countries)? 

The instances that comprise the dataset are logs of individual keystrokes produced by subjects during the typing of an essay, which are contained in the train_logs.csv dataset, and the corresponding essay scores, contained in the train_scores.csv dataset. The instances in the train_logs.csv dataset have the following features:
        
        id - The unique ID of the essay
        
        event_id - The index of the event, ordered chronologically
        
        down_time - The time of the down event in milliseconds
        
        up_time - The time of the up event in milliseconds
        
        action_time - The duration of the event (the difference between down_time and up_time)
        
        activity - The category of activity which the event belongs to
        
            Nonproduction - The event does not alter the text in any way
            Input - The event adds text to the essay
            Remove/Cut - The event removes text from the essay
            Paste - The event changes the text through a paste input
            Replace - The event replaces a section of text with another string
            Move From [x1, y1] To [x2, y2] - The event moves a section of text spanning character index x1, y1 to                
                                             a new location x2, y2
        
        down_event - The name of the event when the key/mouse is pressed
        
        up_event - The name of the event when the key/mouse is released
        
        text_change - The text that changed as a result of the event (if any)
        
        cursor_position - The character index of the text cursor after the event
        
        word_count - The word count of the essay after the event

The instances in the train_scores.csv dataset have the features id and score.
 
- How many instances of each type are there? 

There are 8405898 instances of keystroke logs.

- Is there any missing data? No

- Does the dataset contain data that might be considered confidential (e.g., data that is protected by legal privilege or by doctor–patient confidentiality, data that includes the content of individuals’ non-public communications)? No

## Collection process

- How was the data acquired? 

Participants of this project were hired from Amazon Mechanical Turk, a crowdsourcing platform. They were invited to log onto a website that housed a demographic survey, a series of typing tests, an argumentative writing task, and a vocabulary knowledge test. Participants were required to use only computers with a keyboard. During the argumentative writing task, participants were asked to write an argumentative essay within 30 minutes in response to a writing prompt adapted from a retired Scholastic Assessment Test (SAT) taken by high school students attempting to enter post-secondary institutions in the United States. To collect participants' keystroke information during the argumentative writing task, a keystroke logging program was written in vanilla JavaScript and was embedded in the script of the website built for this project. The program listened to the keystroke and mouse events in the designated text input area using JavaScript’s addEventListener method. It also logged the time stamp and cursor position information for each keystroke or mouse operation. Additionally, this program simultaneously aggregated the logged information and identified operation types (e.g., input, delete, paste, replace) and reported text changes in the writing process. 

- If the data is a sample of a larger subset, what was the sampling strategy? N/A 

- Over what time frame was the data collected?

As mentioned above, the essay task itself took 30 mins, however it is not clear over what timeframe the various essay data was collected. 

## Preprocessing/cleaning/labelling

- Was any preprocessing/cleaning/labeling of the data done (e.g., discretization or bucketing, tokenization, part-of-speech tagging, SIFT feature extraction, removal of instances, processing of missing values)? If so, please provide a description. If not, you may skip the remaining questions in this section. No

- Was the “raw” data saved in addition to the preprocessed/cleaned/labeled data (e.g., to support unanticipated future uses)? 
 
## Uses

- What other tasks could the dataset be used for? 

If the results were compelling enough, one could in theory expand the scope of the the model suggested by the Kaggle competition and use the dataset to build a model that actually automatically marks essays based on their typing logs. 

- Is there anything about the composition of the dataset or the way it was collected and preprocessed/cleaned/labeled that might impact future uses? For example, is there anything that a dataset consumer might need to know to avoid uses that could result in unfair treatment of individuals or groups (e.g., stereotyping, quality of service issues) or other risks or harms (e.g., legal risks, financial harms)? If so, please provide a description. Is there anything a dataset consumer could do to mitigate these risks or harms? No

- Are there tasks for which the dataset should not be used? If so, please provide a description.

It would be dangerous to use this dataset to build anything other than a general predictive tool, i.e. to build a model as discussed above that would actually provide an official mark for essays in a course or exam setting.

## Distribution

- How has the dataset already been distributed? 

The dataset was distributed to the Kaggle platform, where it is available for use in the 'Linking Writing    
Processes to Writing Quality' competition which ended on the 9th of January 2024. 

- Is it subject to any copyright or other intellectual property (IP) license, and/or under applicable terms of use (ToU)?  

It is subject to the following license: CC-BY-NC 4.0. 

## Maintenance

- Who maintains the dataset?

The platform that hosts it, i.e. Kaggle.
