

This repository is a starting point for some simple analytics on how professional bicycle racing has expanded from Europe to the rest of the world (if it has) over history.

Right now I only have access to calendars from the UCI's website (www.uci.org) from 2006 - 2019. I hope to add further calendars, but so far no reply from the UCI for their archive.

In the UCI Calendars notebook, I combine each Excel file into one dataframe, and do some cleaning.

The dataset contains races for ME (elite men), WE (elite women), and MU (U23 Men), MJ (junior men), WJ (junior women).

In the years 2006-2007, the UCI had a war with race organisers, who removed their races from the UCI's calendar. As a result, you have to map Category 'MP' to 'ME', and Classes 'MNM' and 'AU1' to '1.UWT' (one-day WorldTour), 1.CH maps to '1.UWT', while GT1/GT2 and CPE should be mapped to '2.UWT' for the purposes of this analysis.

Other classes (1.Ncup) are unique to MU or other categories and were not affected by this nonsense.

The UCI breaks out countries into Continental circuits, which is the purpose of the dictionary at the start. NB I've only used the countries in the 2006-2019 dataset, so if old data has countries that have not held races in this time period that dictionary will need to be appended.

I've added the season to each file name for the calendars for ease of adding this field. The Continental circuits of Africa, Asia and Oceania and probably the Americas do not follow a calendar year due to their hemisphere, and start in arbitrary times in the fall - therefore race start date does not determine season/year.

I tried matching the UCI's way of spelling countries with Google's csv of latitude and longitude for each country (https://developers.google.com/public-data/docs/canonical/countries_csv) but it was too laborious and I found resources to create maps in Tableau.

For the purposes of the analyses, I have ignored races where pro riders race with national teams - continental, world championships, Olympics - and the various national championships which might not technically be professional races.

I've added a calculation for race days per event: end date minus start date plus 1. In the case of Grand Tours where there are rest days, I've taken any race over 21 days and made it 21 (the length of a Grand Tour in this time period). There are a handful of other races with rest days under 21 days long, but it's so infrequent it won't make any meaningful change to any analysis.

The data is exported as a csv file in /data. The analyses done in UCI Races groups, plots, tallies up race days by category and continent.

I downloaded Rankings data from the UCI for road, cyclo-cross, MTB in an attempt to see if there has been an overall change in the distribution of riders from various countries in the rankings overall and in the top x positions.

I attempted to look at the rider data from the UCI database, but found gaping holes in their dataset of registered riders and abandoned that project, thus the rankings were the only other alternative.
