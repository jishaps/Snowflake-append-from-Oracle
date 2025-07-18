# Snowflake-append-from-Oracle
1) Pull the data into a csv file from Oracle
2) Using the UI in Snowflake, create a table for the csv file
3) After this I noticed that 1-Aug-24 from the csv file is considered as 1-Aug-0024 in Snowflake. So updated the table (update table set date_col = DATEADD(YEAR,2000,date_col)
4) Data Validation using sum and distinct
5) Check the count before and after. I used the insert into statement as there is no duplicates but added a where clause to make sure no duplicates. The existing table has date_col < Jul 2024 and the new table has data of Aug and Sep 2024. INSERT INTO destination SELECT * from source WHERE date_col > to_date('07-31-2024','MM-DD-YYYY')
6) DROP TABLE source (Here it is temperary table for holding the data from the csv file)
