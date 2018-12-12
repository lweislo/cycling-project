This repository is a starting point for some simple analytics on how professional bicycle racing has expanded from Europe to the rest of the world (if it has) over history.

Right now I only have access to calendars from the UCI's website (www.uci.org) from 2006 - 2019 - note the import of 2019 is likely incomplete as some races may go away while others may be pending a license... I hope to add further calendars, but so far no reply from the UCI for their archive. 

The dataset contains races for ME (elite men), WE (elite women), and MU (U23 Men), MJ (junior men) WU, WJ, and some other categories.

I've cleaned up the data and exported it into the 'combined' xls file, but it needs further munging. In the years 2006-2007, the UCI had a war with race organisers, who removed their races from the UCI's calendar. As a result, you have to map Category 'MP' to 'ME', and Classes 'MNM' and 'AU1' to '1.UWT' (one-day WorldTour) - (Just noticed another - 1.CH that needs to be '1.UWT'. While GT1/GT2 and CPE should be mapped to '2.UWT' for the purposes of this analysis.

Other classes (1.Ncup) are unique to MU or other categories and were not affected by this nonsense.

The end goal is to answer the question - is pro cycling expanding across the globe, and even if not, is the quality (rank - 1.2 < 1.1 < 1.HC < 1.UWT and 2.2 < 2.1 < 2.HC < 1.UWT (for women WE it's 1.WWT) on the rise or decline.

The UCI breaks out countries into Continental circuits, which is the purpose of the dictionary at the start. The UCI doesn't include this information in their own publicly available data, so I've gone ahead and assigned them to continents for you. NB I've only used the countries in the 2006-2019 dataset, so if old data has countries that have not held races in this time period that dictionary will need to be appended.

And just because the UCI balls up everything, I've had to re-do the downloads and have put the "season" in each file name. I'll update the script to grab the year and put it in the dataframe. The Continental circuits of Africa, Asia and Oceania and probably the Americas do not follow a calendar year due to their hemisphere, and start in arbitrary times in the fall.

If you don't care, just use start date as the year! Just ignore the xlsx files of the format (Calendar_ROA_12_10_2018 (x).xlsx)

I've also done all the hard work of matching the UCI's way of spelling countries with Google's csv of latitude and longitude for each country (https://developers.google.com/public-data/docs/canonical/countries_csv) omg there has to be an easier way...

The script here removes columns that have no meaning. We can probably come up with a weighting formula for each row that looks at the length of the race and its Class, or to simply determine the number of days (start/end date) of racing per country etc.

There's a lot to do before we get to the ultimate goal of an animated bubble map of evolution of cycling over the years across the globe...
