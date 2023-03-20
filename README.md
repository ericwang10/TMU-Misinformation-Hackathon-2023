# UofT-Misinformation-Hackathon-2023
Eric Wang and Eric Long 

How to Install:
Download and run the python notebook in order 
for the api keys, create an xlsx file containing the 5 api keys in the first column of the file 

the order is: 
1. api key
2. api key secret
3. access token
4. access token secret
5. bearer token 

To run the twitter bot, run the main block of code marked by the "#creating a twitter api client to post" comment 


**(a) outline your solution**
We have created a social media fact-checker bot that runs on Twitter. By tagging the bot's social media handle, the bot will analyze the text/claim provided in the tweet, or a news article/website if a link is provided. The bot is able to handle both direct claims (tagging to verify a claim within the tweet), and fact checking of the parent tweet in the discussion thread above.

Furthermore, if a tweet includes a link, the bot will through the website and parse the information provided in the link instead. 

Afterwards, the twitter bot will utilize the openAI API to confirm the validity of the statement using GPT-3.5 (ChatGPT). This response is then posted in the Twitter thread as a reply to the original tagged Tweet. 

The prompts are engineered to provide 3 classes of outputs.
1. True or False based on the statement and facts 
2. Statement is an opinion. This is when there is no fact or statement to prove, and thus is labelled as an opinion.
3. Inconclusive/Unsure. If ChatGPT is unsure of its answer, it will try to output "CANNOT DETERMINE" instead 

**(b) describe all planned and implemented functionalities**

Implemented: Twitter real time tagging and response. ChatGPT prompt answers and validity checking. Web scraping of posted links. Twitter bot replies in tagged tweet. 

Planned: addition of GPT-4 multimodal features to detect different mediums of misinformation. Important categories include pictures (fake news, photoshop, deep fakesetc) and audio (fake audio, voice overs, etc). Furthermore, the improved logical reasoning of GPT-4 will help tackle more sophisticated misinformation. More importantly, the updated information cutoff (2022+) will help GPT-4 maintain a more relevant and informed database of the world. 

**(c) how your solution can be deployed to fight misinformation online and by whom **

Misinformation is rampant on Twitter and other social media discussion sites. This is especially true during discussions/arguments between users online. Misinformation can be intentional, such as when users deliberately spread false or misleading information for personal gain or to influence an audience. It can also be unintentional, when users share information without verifying its accuracy or rely on biased sources. False information can contribute to polarization and further divide people with different views, especially in the realm of US politics and the debate between political groups. We wanted to specifically address the use of misinformation/made up information in online discussion threads to support an internet argument.

The ease of use of Twitter, its wide audience, the potential to go viral, and a lack of repercussions encourages misinformation and a lack of consideration before posting. This is shown by how easy it is to write something random and post the tweet. 

By offering a bot that has a similar level of convenience as regular tweeting (simply tag and post), we provide users with an effortless way to combat misinformation without needing to spend significant time or resources conducting research to disprove another individual's point or news article. Our goal was to make this solution a direct improvement to the social media lab's OpenAI Demo App, which required users to navigate away from Twitter and onto a separate website.

Our Twitter fact-checking bot aims to disrupt the cycle of misinformation by offering users a convenient method for verifying the accuracy of claims in real-time. By simplifying the process of identifying and debunking misinformation, we can foster a more informed and responsible approach to online discussions. 

**(d) whether and how you evaluated its effectiveness.**

To analyze the accuracy and validity of the ChatGPT model, we have downloaded a labelled political fake/real news dataset. Unfortunately, due to the popularity of ChatGPT and GPT-4, we were unable to properly test the model's accuracy on this dataset without being timed out by the API. This formal evaluation of accuracy will be a planned functionality for the future. 

As a real world test, we have applied the bot in various Twitter sections such as politics, investing, sports, and climate change to analyze its potential and efficacy. 

A few points we noticed is that:
1. The ChatGPT model is willing to say "Opinion" or "Unsure" a lot, rather than providing a faulty answer. This was one of the things we wanted to improve on compared  to the social media lab's OpenAI Demo App, which we observed to provide black or white answers more frequently. (an example would be the prompt "apples are good"). 
2. The dated information cutoff of ChatGPT causes a few claims and statements to be misclassified. This is especially true in politics, where the latest and hottest things are talked about, and narratives shift very fast in the light of new information. One example of this would be the arrest warrant for Vladimir Putin, which was only announced in March of 2023 but mistakenly marked as satire by ChatGPT. 





