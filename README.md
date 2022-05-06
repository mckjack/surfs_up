# Surfs Up 
## Purpose
The purpose of this analysis was to study the temperature trends of June and December. We studied this data through the use of technologies such as Python, Pandas, SQLite, and SQLAlchemy. Our end goal was to analyze the sustainability of the surf and ice cream shop business. 
## Results 
From the analysis we were able to reach the summary statistics of the temperature in Oahu in June and December.

![december](https://github.com/mckjack/surfs_up/blob/main/December%20Stats.png)

![june](https://github.com/mckjack/surfs_up/blob/main/June%20Stats.png)
- Since December's standard deviation is higher than June's meaning the temperatures are more spread out indicating that the temperatures aren't as constant and are spread out ranging high to low. 
- The minimums of both each December and June are very different with December being 56F and for June 64F where as the maximums are very similar being 83F for December and 85 for June. This can result in Decembers temperature getting very low. 
- The average temperatures are fairly different for June and December. June's average temperature is 75F and December's is 71F meaning that on average the temperatures are not too different in June and December. 

## Conclusion
The two times of the year, June and December, are not fairly different temperature wise making both suitable times for the surf and ice cream shop to open. However, lets investigate with some other queries on the data to reveal different data than temperature in June and December. The following code reveals the amount of precepitation in the two months.
- session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 6).all()
- session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 12).all()

We also can get the amount of precipitation from the most active station in the months of December and June
- session.query(Measurement.prcp).filter(Measurement.station == 'USC00519281').filter(extract('month', Measurement.date) == 6).all()
- session.query(Measurement.prcp).filter(Measurement.station == 'USC00519281').filter(extract('month', Measurement.date) == 12).all()
