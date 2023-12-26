# DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-
The main aim of the project is to build an ETL pipeline for Nigeria Population data using Microsoft Fabric using Architecture such as LakeHouse, Notebook, Semantic Model and Power BI for data visualization.

# Introduction
In many cases, companies require information from trustworthy sources outside their own databases. This data is important for tasks like studying the market and connecting analytical insights to the outside world, such as conducting a SWOT Analysis.

# Objective of the Project
The aim of the project is to create a system that can collect, organize, and update information from the Worldometer website. This makes the data easily accessible for everyone in the organization to use whenever they require it using Microsoft Fabric Architecture.
## Project Architecture
Microsoft Fabric is a collection of tools designed for individuals working with data, covering tasks in data engineering, analytics, and machine learning. It accommodates various preferred tools like Python, R, SQL, and DAX, as well as user-friendly options like DataFlow (Power Query). This entire framework is constructed on the Microsoft Azure platform.
In our project, we utilized a Workspace, which acts as a designated folder within Fabric to organize all our projects and resources. We also incorporated other components of the Microsoft Fabric Architecture, including Notebooks, Semantic Models, and Power BI. Each of these elements plays a specific role in managing and presenting our data effectively.

![Architecuture Image](https://github.com/Ainaganiu/DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-/blob/main/Pictures/architecture.png)

The diagram above illustrates how our solution flows within Microsoft Fabric, from ingesting and processing the data. We obtained the dataset for this project by pulling information from the Worldometer website using its URL. Using a notebook, we read and transformed the data, loading it into a Fabric Lakehouse. Subsequently, we employed a SQL endpoint to query the data, and connected this endpoint URL to Power BI for creating visualizations based on the queried dataset.

# ETL Process
After establishing a Workspace and Lakehouse, the Extract, Transform, Load (ETL) process of the project was carried out. This involved connecting to the dataset using the Notebook option within the workspace.
![Notebook](https://github.com/Ainaganiu/DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-/blob/main/Pictures/notebook.png)


Most of the integration the dataset employed in this project is an HTML file extracted from the Worldometers website, focusing on information related to the population of Nigeria. The dataset was connected using Python leveraging the pandas DataFrame.
Upon connecting to the data, it was identified that there are three tables in the provided URL. To ensure compatibility with the SQL Endpoint—avoiding spaces between text and eliminating duplicates—we utilized a Python function. This function was designed to standardize the format of column headers.
![urlloading](https://github.com/Ainaganiu/DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-/blob/main/Pictures/urlloading.png)
![dataframe](https://github.com/Ainaganiu/DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-/blob/main/Pictures/dataframe.png)
![tables1](https://github.com/Ainaganiu/DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-/blob/main/Pictures/dataTables.png)  

# Removing Headers Space
We employ a custom or pre-defined Python function aimed at streamlining the process of removing spaces from column headers. The primary motivation behind this approach is to establish a reusable and efficient piece of code. By encapsulating the header cleaning logic within a function, we enhance the code's versatility, allowing it to seamlessly handle the task of cleaning table headers for any dataset.

![removeHeader](https://github.com/Ainaganiu/DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-/blob/main/Pictures/cleanedheader.png)

# Loading the Table into Lakehouse
Following the standardization of column headers, the next step involves saving the DataFrame into files within the Lakehouse. 

![saveLakehouse](https://github.com/Ainaganiu/DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-/blob/main/Pictures/savingLakehouse.png)

Subsequently, these files are promoted into tables, rendering them prepared and organized for seamless use within the organization. This process ensures that the data is not only cleaned and standardized but also structured in a way that aligns with the organization's requirements for easy accessibility and analysis.

![file Lakehouse](https://github.com/Ainaganiu/DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-/blob/main/Pictures/FilesLakehouse.png)
![Load Table](https://github.com/Ainaganiu/DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-/blob/main/Pictures/LoadToTable.png)
![Table Overview](https://github.com/Ainaganiu/DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-/blob/main/Pictures/LakehouseTableView.png)

# Querying the Tables
Microsoft Fabric provides us the option to use SQL to query the tables in the lakehouse using T-SQL or visual query option (Drag and Drop). In order to perform this, we swichted to SQL Analytics Endpoint as shown below

![Clicking SQL Endpoint](https://github.com/Ainaganiu/DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-/blob/main/Pictures/clickSQL.png)

# Creating View
After utilizing SQL to query the dataset, the extracted dataset was saved into a view. This step is crucial for creating a virtual representation of the queried data. Views serve as dynamic, customized perspectives on the dataset, allowing for tailored analyses and facilitating easier access to specific subsets of information as needed by different teams within the organization.

![query2](https://github.com/Ainaganiu/DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-/blob/main/Pictures/top10.png)

![query1](https://github.com/Ainaganiu/DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-/blob/main/Pictures/query2.png)
![visual Query](https://github.com/Ainaganiu/DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-/blob/main/Pictures/visualquery.png)

# Data Visualization
In this project, we've successfully ingested the data into the Microsoft Fabric Lakehouse. The subsequent step involves generating a report for end-users to visualize the dataset's output and gain insights derived from it. Using Power BI Desktop This report serves as a user-friendly interface, providing a clear and comprehensible presentation of the data findings, making it accessible and meaningful for stakeholders within the organization.

**Choosing Lakehouse Connection**
![connecting 1](https://github.com/Ainaganiu/DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-/blob/main/Pictures/lakehouse_connection.png)

**Conneting to Nigerian Population Lakehouse**
![Nigerian Lakehouse](https://github.com/Ainaganiu/DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-/blob/main/Pictures/selectingNigerian.png)

**Selecting Direct Query to Load the Data in Real Time**
![Connection Setting](https://github.com/Ainaganiu/DATA-ENGINEERING-WITH-MICROSOFT-FABRIC-A-CASE-OF-INGESTING-NIGERIAN-POPULATION-DATA-/blob/main/Pictures/connection.png)






