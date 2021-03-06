# Azure Databricks Labs

**Azure Databricks** is an Apache Spark-based big data analytics and machine learning framework optimized for the Microsoft Azure Cloud.
Databricks is integrated with Azure to provide one-click setup, streamlined workflows, and an interactive workspace that enables collaboration between data scientists, data engineers, and business analysts.


This tutorial helps you understand how to use Azure Databricks Spark to prepare raw data for analytics.


# Getting Started

Follow the **Step 1** to set up the lab environment for the Data Engineering lab and Spark sql & Performance optimization.
## Step 1: Deploy Sql Data Warehouse.

1. **Login** to [Azure portal](https://portal.azure.com) using the credentials provided in the environment details page. You will be having access to one resource group.</br>
2. **Select** Create a Resource  search for **Sql Data Warehouse** select Create, add the details as follows:
    * **Select** the Pre-created Resource group 
    * **Data Warehouse name**: nyctaxidb
    * In server **Create new** add the credentials as follows:
      * **Server name**: nyctaxicab-**SUFFIX**
      * **Server Admin Login**: demouser
      * **Password**: demo@pass123
      * **Select** the location used in your Resource group
     * **Allow** Azure services to access server
   
   <kbd>![](images/data_warehouse.png)</kbd></br></br>
3. In **Performance level** Select **Gen2 DW100c**.
   <kbd>![](images/data_warehouse1.png)</kbd></br></br>
4. Go to Data Warehouse , go to **security** select **Firewalls and virtual networks**
     * **Rule Name**: all
     * **START IP**: 0.0.0.0
     * **END IP**: 255.255.255.255
     * **Save**
   <kbd>![](images/ip_config.png)</kbd></br></br>  
5. In **Sql DataWarehouse** go to **Connection strings** copy the **JDBC** url and save it for later use.
    <kbd>![](images/jdbc_3.png)</kbd></br></br>
   
   

## Step 2: Verify the resources.

1. **Open** the resource group and you can find a **Databricks workspace** already deployed.</br></br>
<kbd>![](images/01_rg.jpg)</kbd></br></br>
2. Go to the Azure Databricks workspace, and then click on **Launch Workspace**.</br></br>
<kbd>![](images/02_Launch.jpg)</kbd></br></br>
3. You are now inside your Databricks workspace.</br></br>
<kbd>![](images/databricks.jpg)</kbd>


## Step 3: Attach the Notebook to your cluster.

1. **Open** the Databricks Workspace.</br>
2. Click on **Clusters** tab to view the available Databricks Clusters. **Start** the cluster if it is in terminated state.</br></br>
<kbd>![](images/cluster_1.png)</kbd></br></br>
3. Now let's **Click** on the **Workspace** tab and open the folder named **Shared**, where you can find Data Engineering notebook. Open the  notebook.</br></br>
<kbd>![](images/data_engineering.png)</kbd></br></br>
4. Click on **`detached`** written on the top-left corner, and you'll see a list of active clusters.</br></br>
<kbd>![](images/05_attach.jpg)</kbd></br></br>
5. **Attach** your notebook to a running cluster. A green icon shall appear on top, meaning our notebook is now attached to our cluster and is ready to be executed. Now you need to follow the instructions specified in each of the Notebooks.

### Your Databricks Environment is ready now and you can proceed with the labs.
1. **Open** the Databricks Workspace.</br>
2. **Click** on the **Workspace** tab, open the folder named **Shared**, where you can find a Notebook. **Open** the notebook named **Lab-DataEngineering**.</br></br>
<kbd>![](images/data_engineering.png)</kbd></br></br>
3. **Attach** the cluster in to this Notebook, if you haven't attached it yet.</br>
**Note**: We have to install a Library in our cluster as **Machine Learning and Real-Time Stream Analytics** require some packages to import.
Following are the steps to install a library.
* **Open** the Databricks Workspace.</br>
* Go to cluster and click on **Libraries**.
    <kbd>![](images/library.png)</kbd></br></br>
* Then click on **Install New** and go to maven and add co-ordinate as **com.microsoft.azure:azure-eventhubs-spark_2.11:2.3.3** and install.
   <kbd>![](images/library_1.png)</kbd></br></br>
*  You can see that Library package is installed , the package will be used in Real-Time stream analytics notebook.
    <kbd>![](images/library_2.png)</kbd></br></br>

4. Follow the instructions in the notebook to continue with the lab. To run the cells in the Notebook, **Click** on the **Play** button in the top right corner of that cell and then **Click** on **Run Cell**</br></br>
<kbd>![](images/run_cell.jpg)</kbd></br>
5. After completeing `Lab-DataEngineering`,  **Open** the Databricks Workspace. **Click** on the **Workspace** tab, open the folder named **Shared**, where you can find Notebooks. **Open** the notebook named **SparkSql & Performance Optimization**, attach the cluster and follow the instructions in the notebook.</br></br>
6. Follow the same for **Machine Learning** ,**Real-Time stream analytics** ,**Azure Databricks Delta** and **Data Orchestration using Azure data Factory** notebooks.

`Note :` For **Real-Time stream analytics** and **Data orchestration using Azure Data factory** , First we need to have **Machine Learning** Tested as we require trained model for Real-Time stream analytics and Data orchestration using Azure Data factory
