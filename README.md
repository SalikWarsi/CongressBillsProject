# USA Congress Bills

# Abstract
The objective of the project is to look at the data of all bills introduced in United States Congress (both House of Representatives and the Senate) since 1973. I will be analyzing how many bills are introduced and what happens to these bills, as in whether they are passed into becoming a law or rejected in some stage before that. The project also aims to tackle whether the recent news about gridlock in congress is true and whether this has led to a lower amount of bills being successfully passed as law over this time period. Similarly, I would also look at the composition of the congress and the cosponsors of the bills to see if that affects them. Finally I would see if a bill being bipartisan has a higher chance of passing and whether we see changes in bipartisan support in the US congress.

Through this Project I intend to give a mathematical idea to someone about what is the chance of bill they are interested in passing and getting enacted.

# Hypotheses

I try to answer the following questions in this analysis:
1. Has the number of bills introduced in Congress changed over the years?
2. Has the ratio of Bills that are enacted into law changed over the years?
3. What factors affect the chances of a bill? Does having more cosponsors lead to a higher chance of the bill getting passed in the originating chamber?
4. Are bills more likely to pass if introduced by someone whose party has the majority in that chamber. Also are bills sponsored by minority members getting passed at a lower rate?
5. Does having bipartisan support increase the odds of a bill's success? 
6. Finally is there a decrease in bipartisan support in the congress?

## Data Sources
My primary data Source will be ProPublica's data of all the bills introduced in Congress in each session: https://www.propublica.org/datastore/dataset/congressional-data-bulk-legislation-bills 

This data is Licensed under Probublica's [Terms of Use](https://www.propublica.org/datastore/terms) . However, I have mailed them and confirmed that I am allowed to republish their data.

ProPublica have obtained this data from United States Github account (https://github.com/unitedstates) . As explained in https://github.com/unitedstates/congress/wiki/bills we only have data about all bills from 1973 onwards, as before that, the API only provides the data for bills that were enacted successfully. Also, there is a schema change from 2013 onwards which I will handle in my code.

You can either download this data directly from my provided source or from my provided Figshare account: https://figshare.com/articles/US_Congress/5660815 DOI: https://doi.org/10.6084/m9.figshare.5660815.v1 Unfortunately the data was too big for github.

Apart from this I will be using data from https://github.com/unitedstates/congress-legislators , specifically :
1. [Current legislators](https://theunitedstates.io/congress-legislators/legislators-current.csv)
2. [Historic legislators](https://theunitedstates.io/congress-legislators/legislators-historical.csv)

to find names and Political affiliation of the Legislators.

All data from [@unitedstates](https://github.com/unitedstates) is Public Domain.

I will have a copy of the data in this repository, so future researchers can use that directly.

## Methodology

I will be using a logistic regression to estimate the chances of a bill passing the chamber. At the same time I will also also be doing a linear regression to compare the size of majority and the chances of bill passing for a member of the majority.  

The advantage of using this approach is that not only is it a classifier it also gives the probability of the result which is what I want. Also it is easy to understand for the reader.

# Conclusion

I concluded that the number of bills introduced in congress each year has mostly remained same after 1977 onwards. However the ratio of bills that become enacted has decreased a bit over the last few years.

From our analysis, we can see that indeed having more cosponsors increases the chances of a bill passing congress and becoming law. Also while having cosponsors from one party is slightly helpful, having bipartisan support from both sides of a party helps the bill's chances a lot more.

However we also showed that unfortunately, bipartisanship has been decreasing in congress a lot over the years, possibly explaining the recent decrease in the number of bills that get passed, giving an impression of gridlock in the congress.

# Issues

These are the possible issues with my analysis:

1. Not all bills are equal. In my analysis I am treating bills as equal to each other. However a bill like healthcare is obviously much more important than another that just changes the name of a park. Therefore that should be factored in.
2. For counting the number of members of a political party, I used the count from the beginning of the congress. However some members might have resigned over the 2 years and this changed the numbers. This could have led to situations like 2001-2002 Senate as mentioned above which went from a tie break republican majority to a 49-49-2 split where neither party had a majority.
3. The relationship between a bill's passing probability and cosponsors is probably not linear in a logistic manner. However as we just seeing the coefficient, that should be fine.
4. The analysis doesn't imply that passing more bills is good for congress. Some could say that increased bipartisanship might lead to a decrease in opposition or decrease in debate. Therefore this should simply be seen as a statistical analysis that leads to future research

# Future work
The data about bills introduced in congress is a treasure trove. Some of the possible future research that we can do:
1. Do different committees have different procedures and if so does that lead to difference is probability of success of the bill?
2. How likely is it for women to Sponsor/ Cosponsor bills? Do these bills have a similar chance of success? This is especially important considering the low proportion of women in the Congress both currently and historically. The US GitHub does contain data for gender for the Legislators. 
3. Using the Wikipedia data for each Legislator, provided in US GitHub account, we could try obtaining more information and see how that affects their bills. For example, are legislators elected with a larger majority more likely to introduce more bills?


# License
My research would be released under an MIT License and the data is all public domain.

# Human Centered Data Science Perspective

I applied the following HCDS principles:
1. Licenses: I ensured that the research is licensed under a MIT license so others can use it.
2. Copyright: I ensured that all data is public domain. While the collectors and source of the data is ProPublica, I got a written mail from them, saying it is public domain data and could be used. I also cite their work in my research
3. Repeatability and Reproducibilty: The entire code and data (as well as how to obtain the data) is released here under a MIT License so it can be reproduced completely. To be completely transparent, my exploratory analysis is also in the python notebook.
4. Interpretability: I hav used methods like Logistic regression that are very transparent and easy to understand for the audience of the research. Also I have used visualisation to convey the informaion in a simple manner to promote this goal.
5. Qualitative Research: The project involved a lot of qualitative research to understand the topics such as the different kinds of status of a bill, as well as issues such as byelections, filibuster and how politicians can belong to one party but still caucus with another and so on. Without these analysis I would not have been able to do this project. However I am still amateur in this subject and probably made some errors. Feel free to please point them out.