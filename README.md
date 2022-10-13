# Extract, Transform and Load – Adding “Backers” Data to the Independent Fundraising Database
## Overview

Crowdfunding campaigns generally use online platforms to raise the funds for a project or venture by accepting donations from a large number of people.  Often the success of such campaigns is dependant upon identifying, engaging and contacting individuals that connect or identify with the specific project or venture – a process which benefits greatly from establishing, maintaining and making efficient use of databases.  The client for this analysis, an increasingly popular crowdfunding platform called Independent Funding, originally asked to have all of their accessible project data moved into a  PostgreSQL database.  Following the extraction, transformation and loading of their existing spreadsheet data into tables in a tailored database, the client then produced additional data related to project “backers” and asked that it be inserted into a new table in the same database with appropriate relations to the original tables.  The following analysis represents an attempt to address this request and use queries to extract information from the resultant database. 

## Results

The first step of the process was to extract the “backers” data into a pandas DataFrame and then transform the data as required before resaving the data in csv format (See Figure 1)

![]( https://github.com/Scruffy-Bearie/Crowdfunding_ETL/blob/main/IMAGES/Figure1.png)

Following extraction and transformation of the “backers” data, information regarding the structure of and data types in the resultant table was incorporated into an existing entity relationship diagram for the database (See Figure 2).

### Figure 2: Entity Relationship Diagram for the Crowdfunding Database
![](https://github.com/Scruffy-Bearie/Crowdfunding_ETL/blob/main/IMAGES/Crowdfunding_db_relationships.png)

Using the entity relationship diagram, it was possible to alter the database schema for the existing database to include a table for the “backers” data and then import the new data into the database (See Figure 3).

![]( https://github.com/Scruffy-Bearie/Crowdfunding_ETL/blob/main/IMAGES/Figure3.png)

In order to verify that the “backers” data had been successfully/accurately loaded into the database, a query was created to determine from the “campaign” table the number of backers for each live project and then compared to an equivalent query run on the “backers” table (See Figure 4).

![]( https://github.com/Scruffy-Bearie/Crowdfunding_ETL/blob/main/IMAGES/Figure4.png)

Having verified that the “backers” information had been correctly incorporated into the database, two additional queries were run to obtain information regarding live campaigns that had yet to reach their fundraising objectives and contact information for the existing backers of those campaigns (See Figures 5 and 6).

![]( https://github.com/Scruffy-Bearie/Crowdfunding_ETL/blob/main/IMAGES/Figure5.png)
![]( https://github.com/Scruffy-Bearie/Crowdfunding_ETL/blob/main/IMAGES/Figure6.png)

## Summary

The results acquired clearly demonstrate that through use of the “Extract, Transform and Load” process it is possible to create databases that, when combined with appropriate queries, are capable of producing/providing required information in an efficient and elegant manner.
