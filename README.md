# TimeSeries_Data_Lab

Primary Requirements to Show Support For

100,000 devices in different geographies pushing 1 message over variable time speed.  We will start with 1 message every 10 seconds.
25 concurrent users looking at charting dashboard showing various views of the time series data.

Note - Can Divide everything by 6 if pre-aggregated at the minute level.

1 Device
Daily Messages - 8,640
Monthly Messages - 267,840
Annual Messages - 3,153,600
5 - year Forecast - 15,768,000

Full Scale (100,000 Devices)
Bytes/Second = 1MB/second (barely fit into TSI; able to get support ticket 2MB)
Daily Messages - 864,000,000 = 864 Million
Monthly Messages - 26,784,000,000 = 26.8 Billion  (potential chop to 4.5 Billion) - 2.6 TeraBytes
Annual Messages - 315,360,000,000 = 315 Billion
5 year forecast - 1,576,800,000,000 = 1.58 Trillion (assuming 3 columns & 32 bytes per column = 152 TeraBytes)

Each sub section will do the following:

Pushing Cluster(s)
1.  Spin up a single cluster with 100 nodes (each node simulates 1,000 devices)
2.  1 month retention rate Hot Store (2.6 Terabytes to prestore in Database)
3.  5 year retention for cold store (152 TeraBytes to prestore in cold store)

Reading Cluster(s)
SQL + Hadoop
    a.  Read from Hot Store while data is pushed in simultaneously.  Configure SQL Server with retention.



Design Flex Points

-------------------------------------------

1.  Retention Period (Hot/Warm Path)
2.  Retention Granularity (Hot/Warm Path)

-------------------------------------------

TODO:  Understand how TSI moves data between Warm & Archival Paths for query.

ONLY REAL OPTIONS:

1.  TSI (possibly need to verify with PM)
2.  SQL or other warm store