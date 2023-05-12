# Obtain League of Legends Professional Match Data using Azure Data Factory
### Why this project?
* As a League of Legends fan, it is always fascinating to me to be able to predict which team is going to win.
* Having match data automatically updated, ready to be used would make prediction easier.

### How this project works?
This project utilize Azure Data Factory’s comprehensive set of data integration solutions both outside and inside Azure environment:
* Pulling League of Legends professional tournaments data from Google Drive
* Transforming and loading data to Azure SQL database for query
* Sending email notifications whenever an update has been made inside ADF

### Data Flow Diagram
![image](https://github.com/kazerurouni/is4900-project/assets/117042809/e3789d45-e511-4bf5-886f-d0b96155c550)

### Future Revisions
One thing I really like about ADF is its extensive set of connectors and transformations which helps integrate data from various sources and to various destinations. So as future revisions, I will be adding to the Data Factory a data analytics tool (Databricks), a data visualization tool (PowerBI) and Azure Machine Learnng.

### Deploying Resources
First you need to create an Azure Data Factory as well a SQL database. Microsoft Learn's quickstarts can be found in these links: 
* Create Azure Data Factory (follow the "Create a data factory" section only): https://learn.microsoft.com/en-us/azure/data-factory/v1/data-factory-build-your-first-pipeline-using-editor 
* Create SQL Database: https://learn.microsoft.com/en-us/azure/azure-sql/database/single-database-create-quickstart?view=azuresql&tabs=azure-portal

Next, you also need to deploy logic app that can connect to your email account and send out noficication emails. This can be done using this button bellow: <br>
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FrealAngryAnalytics%2Fadf%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a> <br>
*In order for this logic app to be deployed successfully, you need to make sure to sign in to your email.*

Finally, you can create resources inside your ADF by using the button below: <br>
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fkazerurouni%2Fis4900-project%2Fmain%2FTemplateForFactory.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a><br>
*There are few things you need to fill in:*
  * Azure sql database connection string - will be the source. Found in "settings -> Connection Strings" dialog. Using SQL Authentication is probably easiest. Replace "User ID" and "Password" entries with your real values or the deployment will fail.
  * HTTP URL. This is the URL for your recently created Logic app. Found in "logic app designer" -> click on "When a HTTP request is received" and copy the "HTTP Post URL"
