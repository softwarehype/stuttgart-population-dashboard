• Stuttgart Population Dashboard (Power BI)



I built this dashboard to explore how Stuttgart's population has changed since 1986, broken down by district and age group. It runs on open data from the city's own statistical office, and the goal was to turn a plain CSV into something you can actually read a story from.



• What the data shows



A few things jumped out once I dug in:



\- Stuttgart grew fast between 2011 and 2017, then slipped a little during the pandemic in 2020 and 2021. By 2022 the city was home to roughly 610,000 people.

\- Bad Cannstatt is the biggest district by a clear margin, with about 12% of everyone. Most of the population sits in just a handful of large districts.

\- Here's the one I didn't expect: the share of people 65 and older peaked around 2009 at nearly 19%, and then it actually fell through the 2010s. So many young people moved in that Stuttgart got younger during those years, which is the opposite of what you usually hear about German cities aging.



That last point is a good example of why I like this kind of work. The obvious guess was wrong, and the data said so.



• What's in the dashboard



The report has three pages:



\- Überblick gives you the headline numbers, the population trend from 1986 to 2022, and a short summary of the findings.

\- Stadtbezirke ranks every district and lays them out in a table with population, share of the city, and rank.

\- Altersstruktur shows how the age mix shifted over time, plus the 65+ trend on its own.



!\[Overview](UberBlick%2001.png)

!\[Districts](Stadtbezirke%2002.png)

!\[Age structure](Alterstruktur%2003.png)



• Where the data comes from



Landeshauptstadt Stuttgart, Statistisches Amt, Einwohner nach Altersgruppen und Stadtbezirken (open data): https://opendata.stuttgart.de



• How I built it



\- Power BI Desktop for the model, the visuals, and the interactivity.

\- Power Query for cleaning. I filtered down to one year-end snapshot per year and fixed some broken character encoding in the district names.

\- A star schema: one fact table for the population figures, plus three lookup tables for year, district, and age group.

\- DAX measures for year-over-year growth, each district's share of the city, the ranking (using RANKX), the 65+ share, and the latest-year KPIs.

\- One data-quality catch I'm proud of: the source had two measurement dates per year, which was quietly double-counting the population. I spotted it when the growth rates looked impossible, traced it back, and fixed it.



\---



Built by Matthew Okeke as part of my data analytics portfolio.

