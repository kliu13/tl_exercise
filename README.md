# tl_exercise

Process:

I started out just by going through the data and transforming it into a form I would be able to work with a bit easier. First, I removed the non state locations (ex. Guam, Diamond Princess, etc) just to make the initial exploration a bit easier, as I’m mainly just interested in the states at this point. I also converted the Date variable from char to dates.

My first step was to plot the number of cases in the US over time, to see what the overall trend has been. During the data manipulation for this part, I found a strange, very low observation. Upon further inspection, I found that this was caused by the 4/13/20 observation for Florida being recorded at a different time from all the other states that day. Since my case sums depended on identical Date entries, I changed the Florida date/time to match the rest before continuing with my little plot. 

I then zeroed in on California by itself. The plot of CA’s aggregate cases over time shows periods of slowed vs rapid growth. I then made a plot of daily cases in California (calculated as the difference in aggregate cases), which shows us the fluctuation in a little more detail. This made me curious to see whether these spikes/drops correspond to California’s varying COVID policies. I inserted green lines when CA started loosening restrictions, and red lines when CA re-tightened policies. Just from the graph, it does seem that reopening led to increased rates of COVID. (Next steps would include looking at the increased rates/whether these rates may be coincidence, using hypothesis testing, as well as a more detailed examination of CA’s reopening policies. Perhaps I could repeat the same process with the rest of the states, and see whether states that adopted similar policies would experience similar changes in confirmed cases.)

My next step was to see how cases vary by state. I took the average incident rate for each state and arranged them in ascending order. (I use rates instead of aggregate cases in order to account for states’ varying populations). I also made a choropleth map for easier visualization. We can see that some states (eg Vermont, Maine) do much better (ie, lower rates) than others (eg. North Dakota). It could be that these states adopted better policies, where “better” is judged by lowest COVID rates, though some other metrics could also be used (death rate, hospitalizations, etc). 
In order to determine whether states with lower COVID rates had better policies in place, versus just noise in the data, I would perform a multiple comparison test with a null hypothesis that beta_1 = beta_2 = … = beta_50 (representing probability of testing positive for COVID), the alternative hypothesis being that at least one beta does not equal the rest.
For a visual comparison, I calculated the (1- 0.05/1225)% confidence interval of the incidence rate for each state and plotted them together. (I used the Bonferroni correction to make the overall error rate 0.05). We can see that some states have much more spread than others, and that the states without overlapping error bars would have stronger evidence towards rejecting the null hypothesis.
However, this test would rely on the assumption that the population of each state is identical, and differences arise from policies varying state by state. This is a rather substantial assumption to make. For example, if North Dakota has a higher proportion of elderly residents when compared to Maine, then it would not be fair to attribute North Dakota’s poor incidence rate to policy instead of addressing the possibility that there are more high-risk residents there. There are numerous variations that would have to be addressed before reaching any conclusions.


Reading multiple csv file method taken from: https://stackoverflow.com/questions/11433432/how-to-import-multiple-csv-files-at-once
CA policy timeline:
https://calmatters.org/health/coronavirus/2020/04/gavin-newsom-coronavirus-updates-timeline/?


