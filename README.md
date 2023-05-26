# six-day-crypto-trend
## Six Day Crypto Google Trends Search Analysis ##

This is a personal project where I wanted to do data cleaning, analysis, and visualization all in Google Sheets.

I used Google Trends to explore data. My final chart revealed that over a 6 day period, the words Bitcoin, Ethereum, Cardano, and Xrp all peak in searches around 4am each day.

![](https://docs.google.com/spreadsheets/d/e/2PACX-1vTUaWJqT1l7kvE5pSyhjFOSisfZDI1Tl16PTEs3llEi0LKLrIYZ-MXoTtaBTpFeUcjLElcRRGdCHRjJ/pubchart?oid=1743019569&format=image)

*Interactive chart* https://docs.google.com/spreadsheets/d/e/2PACX-1vTUaWJqT1l7kvE5pSyhjFOSisfZDI1Tl16PTEs3llEi0LKLrIYZ-MXoTtaBTpFeUcjLElcRRGdCHRjJ/pubchart?oid=1743019569&format=interactive

This sample size is not enough to come to any conclusions, but it definitely peaked my interest to dig further. I'm sharing because this is my first ever data analysis project and I wanted to clean the data myself to reproduce the visualizations (with only Google Sheets) that Google automates on their website.

# Prep #
I explored various popular cryptocurrency keywords to see if I could discover something interesting. I began by comparing ADA to BTC (Cardano to Bitcoin). This pulled incorrect data because searches for "ADA" were higher than the more popular "BTC". This is because the term "ada" relates to more than just the blockchain.

I settle with comparing the terms Cardano, Bitcoin, Ethereum, and XRP. Four popular cryptocurrencies. I then explored various timelines using Google's tools and discovered that the past 7 day view seemed most interesting.

# Cleaning #
I downloaded the data as a .csv file and imported to Google Sheets

![](https://github.com/JonathanEdwardLee/six-day-crypto-trend/blob/main/01Screenshot%202023-05-26%20180130.jpg)

Deleted first two rows and cleaned up the header. I also eliminated rows that contained partial data leaving only the days I had 24 hours of data for.

The only challenge was Google's date and time format. 2023-05-18T22. In order to convert this to a more user friendly readable time, I took several steps.

1. Split Date from Time: Data - **Split Text to Columns** - Custom - used "T" as the delimiter.
2. Convert 00-24 to a time: Create ":00" column - **=CONCAT()** - **=TIMEVALUE()**
3. Convert 2023-05-19 to 5/19: **=TO_DATE()**
4. Recombine date and time: **=TEXTJOIN(" ",,E2,F2)**

![](https://github.com/JonathanEdwardLee/six-day-crypto-trend/blob/main/02Screenshot%202023-05-26%20180213.jpg)

# Viz #
For this I used Google Sheets to Insert Chart and I went with a Smooth Line Chart.
You can view my spreadsheet here: https://docs.google.com/spreadsheets/d/1Mc1yDF8g6opxI1KGmpE0KLfi8ooxQ8g3NqaWAULRhJc/edit?usp=sharing

In conclusion, this project provided a simple small data set to prove i have some spreadsheet skills. I had fun doing it and I'm excited to explore this topic further with SQL, Tableau, and BigQuery.
