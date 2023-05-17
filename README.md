# ABSTRACT

Skytrax airline reviews from 2016-2019 include ratings and written comments on six services offered on airplanes, including Seat Comfort, Cabin Service, Food Quality, Ground Service, Entertainment, and Value for Money. While the written comments reflect the personal experiences and opinions of customers, the ratings, which range from 1 to 5, are subjective and may not accurately reflect the objective reality of the services. As a result, analysis of the written comments in the reviews may be more useful in understanding customers' experiences and sentiments.

Through text mining, we can design a model to automatically process a huge number of reviews and find out what part of the service should be improved in those negative reviews. The procedures are as follow:
Firstly, extract training data (40,000) from the preprocessed data (64,095) and the rest is testing data. Then, use training data to train the six RNN models and create the six BOWs relative to each service provided on airlines, such as “Seat Comfort”, “Cabin Service”, “Food Quality”,
“Ground Service”, “Entertainment”, and “Value for Money.” Moreover, airline reviews from Skytrax not only comprise the review texts also comprise the scores on six services.

- RNN models (for each service): Consider reviews with service score between 1 to 2 as negative reviews; reviews with service score between 3 to 5 as positive reviews. Therefore, the RNN model is trained to differentiate whether the review is negative or positive depending on each service.

- Skip-gram-like (SGL) Method with BOW (for each service, take “Seat Comfort” as an example): Recall the negative reviews from training data used in RNN models. Search for the adjectives around some keywords in those reviews. Specifically, the keywords might be “seat”, “uncomfortable”, “sit”, etc. Because those reviews are already negative, the found adjectives are much likely negative as well. After the completion of the dictionary of adjectives, add some synonyms of those adjectives to the bag of words (BOW), so that the BOW is not too deficient.

Lastly, if the testing data is outputted as a negative review (for each service, take “Seat Comfort” as an example), find the same words between the negative review and the BOW relative to its service. For instance, the words in both the review and the BOW might be “hard”, “upright”, etc. Therefore, we are enabled to determine if any review is negative. If so, the trained RNN models and the SGL with BOW will output which service the airline company should improve and enhance.

We have successfully detected some keywords in certain reviews and those words truly reflect the essence of the review. However, for some example, our model outputs quite irrelevant words.