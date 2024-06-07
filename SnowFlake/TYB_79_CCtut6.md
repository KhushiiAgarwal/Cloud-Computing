Name : Khushi Agarwal

Roll no:-79

Division: TY-CS-B

Problem statement Lab 8: **Snowflake** 

**Step 1: Create an account on Snowflake**

![](Aspose.Words.d94c3abd-9895-4e2c-8af5-9de5e961923f.001.png)


![](Aspose.Words.d94c3abd-9895-4e2c-8af5-9de5e961923f.002.png)

The Homepage/Dashboard displays all pre-built worksheets.


**STEP 2: Exploring Snowflakes & its products**

![](Aspose.Words.d94c3abd-9895-4e2c-8af5-9de5e961923f.003.png)

To create a database:

- Click on data in left side menu
- Now click on Databases. Click **+** Sign on right side 
- Name the database and click on create

![](Aspose.Words.d94c3abd-9895-4e2c-8af5-9de5e961923f.004.png)

![](Aspose.Words.d94c3abd-9895-4e2c-8af5-9de5e961923f.005.png)

To create Schema:

- Click on schema under data à  database à database\_name à **+** schema à Standard
- Now write a SQL query and you’ll get its definition

![](Aspose.Words.d94c3abd-9895-4e2c-8af5-9de5e961923f.006.png)

To explore streamlit:

- Projects à streamlit à + Streamlit App
- Name the new app and select an appropriate database & its schema. Click Create

![](Aspose.Words.d94c3abd-9895-4e2c-8af5-9de5e961923f.007.png)

- Now by clicking on created app, we see a demo Python code as below for a simple visualization is provided.

![](Aspose.Words.d94c3abd-9895-4e2c-8af5-9de5e961923f.008.png)

**CODE**


\# Import python packages

import streamlit as st

from snowflake.snowpark.context import get\_active\_session

\# Write directly to the app

st.title("Example Streamlit App :balloon:")

st.write(

`    `"""Replace this example with your own code!

`    `\*\*And if you're new to Streamlit,\*\* check

`    `out our easy-to-follow guides at

`    `[docs.streamlit.io](https://docs.streamlit.io).

`    `"""

)

\# Get the current credentials

session = get\_active\_session()

\# Use an interactive slider to get user input

hifives\_val = st.slider(

`    `"Number of high-fives in Q3",

`    `min\_value=0,

`    `max\_value=90,

`    `value=60,

`    `help="Use this to enter the number of high-fives you gave in Q3",

)

\#  Create an example dataframe

\#  Note: this is just some dummy data, but you can easily connect to your Snowflake data

\#  It is also possible to query data using raw SQL using session.sql() e.g. session.sql("select \* from table")

created\_dataframe = session.create\_dataframe(

`    `[[50, 25, "Q1"], [20, 35, "Q2"], [hifives\_val, 30, "Q3"]],

`    `schema=["HIGH\_FIVES", "FIST\_BUMPS", "QUARTER"],

)

\# Execute the query and convert it into a Pandas dataframe

queried\_data = created\_dataframe.to\_pandas()

\# Create a simple bar chart

\# See docs.streamlit.io for more types of charts

st.subheader("Number of high-fives")

st.bar\_chart(data=queried\_data, x="QUARTER", y="HIGH\_FIVES")

st.subheader("Underlying data")

st.dataframe(queried\_data, use\_container\_width=True)



![](Aspose.Words.d94c3abd-9895-4e2c-8af5-9de5e961923f.009.png)

Graph is generated from above code. Also it provides a table for the same.

![](Aspose.Words.d94c3abd-9895-4e2c-8af5-9de5e961923f.010.png)


Snowflake enables data storage, processing, and analytic solutions that are faster, easier to use, and far more flexible than traditional offerings. The Snowflake data platform is not built on any existing database technology or “big data” software platforms such as Hadoop. Snowflake combines a completely new SQL query engine with an innovative architecture natively designed for the cloud. To the user, Snowflake provides all of the functionality of an enterprise analytic database, along with many additional special features and unique capabilities.

**Architecture**

Snowflake’s architecture is a hybrid of traditional shared-disk and shared-nothing database architectures. Similar to shared-disk architectures, Snowflake uses a central data repository for persisted data that is accessible from all compute nodes in the platform. But similar to shared-nothing architectures, Snowflake processes queries using MPP (massively parallel processing) compute clusters where each node in the cluster stores a portion of the entire data set locally. This approach offers the data management simplicity of a shared-disk architecture, but with the performance and scale-out benefits of a shared-nothing architecture.

![Architecture overview](Aspose.Words.d94c3abd-9895-4e2c-8af5-9de5e961923f.011.png)

Snowflake’s unique architecture consists of three key layers:

- Database Storage
- Query Processing
- Cloud Services

**Database Storage**

When data is loaded into Snowflake, Snowflake reorganizes that data into its internal optimized, compressed, columnar format. Snowflake stores this optimized data in cloud storage.

Snowflake manages all aspects of how this data is stored — the organization, file size, structure, compression, metadata, statistics, and other aspects of data storage are handled by Snowflake. The data objects stored by Snowflake are not directly visible nor accessible by customers; they are only accessible through SQL query operations run using Snowflake.

**Query Processing**

Query execution is performed in the processing layer. Snowflake processes queries using “virtual warehouses”. Each virtual warehouse is an MPP compute cluster composed of multiple compute nodes allocated by Snowflake from a cloud provider.

Each virtual warehouse is an independent compute cluster that does not share compute resources with other virtual warehouses. As a result, each virtual warehouse has no impact on the performance of other virtual warehouses.

**Cloud Services**

The cloud services layer is a collection of services that coordinate activities across Snowflake. These services tie together all of the different components of Snowflake in order to process user requests, from login to query dispatch. The cloud services layer also runs on compute instances provisioned by Snowflake from the cloud provider.

Services managed in this layer include:

- Authentication
- Infrastructure management
- Metadata management
- Query parsing and optimization
- Access control
