# Bootcamp Recruitment Data Warehouse

This project is a data warehouse solution for analyzing recruitment data from a bootcamp. It uses Pentaho Data Integration (Kettle) for the ETL process and a Mondrian schema for OLAP analysis.

## Project Components

### Data Source

The data warehouse is based on a star schema, which is visualized in the `DataSource/Start Schema.png` file.

### ETL (Kettle)

The ETL process is handled by Kettle transformations (.ktr files) and orchestrated by a job (.kjb file). These files are located in the `Kettle/` directory.

The ETL process loads data into the following dimension and fact tables:

*   **Dimensions:**
    *   `dim_candidate`: Candidate information.
    *   `dim_date`: Date dimension.
    *   `dim_interviewer`: Interviewer information.
    *   `dim_location`: Location information.
*   **Facts:**
    *   `fact_applicants`: Applicant data.
    *   `fact_interviewer`: Interviewer data.

The main job file `Job.kjb` runs all the necessary transformations to populate the data warehouse.

### OLAP Schema (Mondrian)

The `SchemaWorkbench/Schema.xml` file is a Mondrian schema that defines the OLAP cube. This schema allows you to analyze the data using a BI tool that supports Mondrian, such as Pentaho BI Server or Saiku.

## How to Use

1.  **Set up your database:** Create a database with the schema described in `DataSource/Start Schema.png`.
2.  **Configure Kettle:** Configure your Kettle environment to connect to your source and destination databases.
3.  **Run the ETL job:** Execute the `Kettle/Job.kjb` file using Pentaho Data Integration to populate the data warehouse.
4.  **Deploy the OLAP schema:** Deploy the `SchemaWorkbench/Schema.xml` file to your BI server.
5.  **Analyze the data:** Connect to the OLAP cube using your BI tool to analyze the recruitment data.
