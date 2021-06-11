# DH100-Project
## An analysis of presidential press briefings sourced from the American Presidency Project
### By Sam Slack

### About the author
Sam is a rising senior at UC Berkeley. He studies Data Science with an emphasis in robotics. Although he has some experience with data processing, this is his first foray into NLP, and he is excited to see what he can do in a more humanities-oriented context.

### Goal
Characterize the language of white house press briefings throughout recent history, tracking use of language centered around different foci 

### Data source
American Presidency Project website: https://www.presidency.ucsb.edu/
This is a UCSB archive that has press briefings dating back to the Clinton administration

### Scraping
Web scraping is done using some assistance/ inspiration from kshaffer’s github page specifically on scraping from this site (which does not appear to have a public or easily findable API): https://github.com/kshaffer/presidencyproject/blob/master/presidency_project.Rmd
Using the search results of all press briefings, each page was scraped for links to individual briefings and the links were compiled into a dataset. Then, using a modified version of kshaffer’s “deglaze” function, the links were scraped for the raw text that they contained, as well as title and date in R’s datetime format. 

### Categorization
The exact list of categorization words is as yet undetermined and subject to change multiple times, but the core principle of the process is manual selection of a number of relevant words that center around a particular theme, such as the economy, climate change, or public health. This approach, as opposed to an automated categorization, eliminates the need for stopwords and a lot of data processing, though it is more subjective. The hope is to be able to repeatedly iterate through the selection process to find word groups that show the clearest difference over time and between administrations, while remaining topically relevant and not subject to habitual speech patterns of presidents or press secretaries at the time.

### Tokenization
Using NLTK, each row (representing a separate press briefing) can be tokenized and analyzed based on frequency of relevant words, giving categorical scores for relevancy. This can then be used to track overall trends in categorical relevancy, both by administration and by in general over time. 
