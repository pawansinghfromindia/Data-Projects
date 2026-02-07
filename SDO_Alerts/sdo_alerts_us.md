## SDO Alerts US and CA

<details>
  <summary>Infosys partnered P&G Project </summary>

<img width="63" height="62" alt="image" src="https://github.com/user-attachments/assets/d42e17db-440f-42db-a6c2-e7c3aeeee580" />

Infosys Project
- Infy ID & Credentials
- Username : pqr.xyz.08@infosys.com
- Password : *********


<img width="63" height="62" alt="image" src="https://github.com/user-attachments/assets/c0017b60-ba4a-4ff0-895f-496f3eb9c1c8" />

P&G Project (Procter & Gamble, American multinational consumer goods corporation)
- PingID - ping.pg.com
- Pulse Secure, VPN - https://vpn.pg.com
- itaccess.pg.com
- Username : xyz.pqr15@pg.com
- Password : *******

</details>

<details>
  <summary> <b> Project Description </b> </summary>

<br/>

**SDO Alerting - Daily and Weekly**
- Sending Daily and Weekly alerts to Vendor and their Retailers across their stores for each and every products to manage, track and increase the sales for 2 countries US and CA
- Used ETL process to feed the source data from blob storage.
- Apply Rules Engine Logic where define the configuration, priority based on each dimension to priotize the alerts based on retailer stores, category, brand, sector, sub-sector and product with their status and chronicity.
- Used Azure Storage Explorer from where we get the source feed and also upload the daily and weekly alerts , Databricks  to write the code logic in notebooks, ADF Pipeline to receive the source feed  and to send the alerts, github to deploy the app.
- Tech Used : **SQL | Python |Microsft Azure | Databricks| ADF Pipeline | PowerBI**.

**Recovered Sales**	
- This logic is build on top of SDO Alerts, where we calculate the total sales and ranked the store-skus based on the last one year data and based on that also add the records in daily alerting flow for those alerts which are exlcluded on previous day due to alert rank limit as they're having more sales so we gave those store-sku chances again on the next day to be included in alerting.
- This logic improves and helps to send the alerts which increases the sales and we recovered the sales which got excluded due to our priority and rules engine logic. 

**Self-Service Portal**
- A user friendly web portal to automate the  Alert configurations .
- A portal where client add new configuration, update or modify the already existing configuration, instead of sending it over mail..
- Tech Used : **HTML | CSS | Javascript**


</details>

<details>
  <summary>P&G SDO Alerts <b>Architecture</b> </summary>

<br/>

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/730b9250-6df5-42c2-8cbc-16742a33cf40" />

<br/>

**CCA and DD-API Feed** <br/>
- launchpadna04
- CCA Feed i.e. Customer Collaborative Analytics
- DD-API(push) to US Launchpadna07(Azure Data Lake v2)

**Data Lake** <br/>
- US Launchpadna07(Azure Data Lake v2)
- Copy Alerts csv files Responses from acosta SFTP(WinSCP) to US Launchpad07(Azure Data Lake)
- Send Alerts csv files from US Launchpad07(Azure Data Lake) to acosta SFTP(WinSCP)
- Send Wrong Read Feedback from US Launchpad07(Azure Data Lake) to acosta SFTP(WinSCP)

same goes for other vedors like Instacart and Albertsons

**ADF(Azure Data Factory), Logic App and Databricks Notebooks** <br/>
Take the files from US Lunchpadna07(Azure Data Lake) <br/>
By using **Logic App** for Email Notification(with attachements) through Pipeline **ADF(Azure Data Factory)**.
send PI Cases resolved by Acosta amd Item not traited (a csv file).


**Extraction, Loading and Transformation (Data Lake to Databricks Notebooks vice-versa)** <br/>
To Extract and Load data from US Lunchpadna07(Azure Data Lake) we get data into **Launchpadna07 DataBricks Cluster** (Delta Lake and Rule Engine).
Transform the data and send it back to US Lunchpadna07(Azure Data Lake).

We do this by Databricks Notebooks and to automate the notebooks run daily we has **ADF(Azure Data Factory)**,
From Here, we also send emails to SDO Devops teams about the Alerts and everything whether alerts are placed successfully or we got the responses or not through Logic Apps.


**Databricks to PowerBI** <br/> 
From Databricks we import data to PowerBI(SDO Aerts Reports and Dashboard)

Later we do also mount the Data from MDM (Retailer Viewpoints P&G Product and Site) where we have **Core Data Lake** there we have Facts and dimension. Through DD API {push} we take the data from Core Data Lake to Core Data Hub and mount(for staging) to our Databricks.

**MDM = Master Data Management** <br/>
Master Data Management (MDM) in data lakes integrates the centralized governance of master data with the scalable, flexible storage of data lakes. - This combination enables organizations to establish a single source of truth for critical business entities—such as customers, products, and suppliers—while handling vast volumes of structured, semi-structured, and unstructured data. 

</details>

<details>
  <summary>P&G SDO Alerts  <b>Process Flow</b> </summary>

<br/>

**SDO Automated Alerts Process Flow** <br/>
- ADF = Azure Data Factory
- ADB = Azure Databricks
- ABS = Azure Blob Storage
- Logic App
- CCA(Customer Collaborative Analytics) and DD-API(Datadog API)
- Microsoft Azure Storage Explorer
  - Subscription > Storage Account > different account for different team/purpose/data > Blob Container > Folders and files


<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/add36174-6d18-4dce-a419-f9ee041ca4e1" />


```python
# Azure Data lake Storage Gen 2 supports Delta Lake and is denoted as abfss
source = "abfss://landing-zone-osa@blobcdhlaunchpadna07dd.dfs.core.window.net";
mount_point = "/mnt/blob/ddapi/landing-zone-osa";
extra_config()

display(dbutils.fs.mount());

mount_point = "/mnt/blob/ddapi/landing-zone-osa";
mount_point = "/mnt/blob/ddapi/landing-zone-pos";
mount_point = "/mnt/blob/ddapi/landing-zone-mdm";
mount_point = "/mnt/blob/ddapi/landing-zone-osa/standard-archive";

mount_point = "/mnt/syn-alerts-acosta-inbound"; // where we input/place the file
mount_point = "/mnt/syn-alerts-acosta-outbound"; // where we get the responses
mount_point = "/mnt/syn-alerts-feed-outbound"; // where we get the responses


```

</details>

<details>
  <summary> <b> SDO Alerting</b> </summary>

1. Sourcing the Data from CCA or DD-API
2. Response Processing
3. Alert Processing
4. Alert Sending

</details>

<!--------------------------------------------------------------------->
## SDO Alerts 

<details>
  <summary> Dimenstions of Alerting</summary>

| Country | Code | States    | city              |
|---------|------|-----------|-------------------|
| USA     | US   | 50 states | across the cities |
| CANADA  | CA   |           |                   |

| Vendor            |
|-------------------|
| ACOSTA            |
| Crossmark         |
| Albertson         |



| Retailers     | Secure_Group_Key | SSID   | RR_Code | Sub_RR_Code |
|---------------|------------------|--------|---------|-------------|
| Walmart       | 130052           |        |  WMT_US | WMT_US_PI   |
| Walmart       | 130052           |        |  WMT_US | WMT_US_OOS  |
| Loblaws       | 130027           |        |  LBL_CA | LBL_CA      |
| Kroger        | 130045           | 3738   |  KRGR_US|             |
| Meijer        | 130021           | 3484   |  MJR_US |             |
| SAMS          | 130058           |        |  SAMS_US|             |
| FAMILY DOLLAR |                  |        |  FD_US  |             |
| TARGET        | 171760           |        |  TGT_US |             |
| COSCO         | 171760           |        |  CSC_US |             |
| Harris Teeter | 171760           |        |  HT_US  |             |
| CVS           | 171760           |        |  CVS_US |             |


| Alerting Type  | Detail                         |
|----------------|--------------------------------|
| 3PL            |**3PL = Third Party Logistics** |
| DA             |**DA = Direct Alerting**        |
| EA             |**EA = External Alerting**      |


| Status       |
|--------------|
| Active       |
| NonActive    |

| Alert_type | Details            |
|------------|--------------------|
| PI         | Phantom Inventory  |
| OOS        | Out of Stock       |


|             Chronicity     | Code       |
|----------------------------|------------|
| Active ExtremeChronic      | ```A-EC``` |
| Active Chronic             | ```A-C```  |
| Active NonChronic          | ```A-NC``` |
| NonActive ExtremeChronic   |```NA-EC``` |
| NonActive Chronic          |```NA-C```  |
| NonActive NonChronic       |```NA-NC``` |
| NonActive ExtremeChronic   |```SOA-EC```|
| NonActive Chronic          |```SOA-C``` |
| NonActive NonChronic       |```SOA-NC```|

> SOA = Service-Oriented Architecture

| sub_sector | Category               |
|------------|------------------------|
|            | Appliances             |
|            | Baby Care              |
|            | Fabric Care            |
|            | Family Care            |
|            | Faminine Care          |
|            | Hair Care              |
|            | Health Care            |
|            | Home Care              |
|            | Oral Care              |
|            | Personal Care          |
|            | Shave Care             |
|            | Skin Care              |
|            | Skin and Personal Care |

> Prod_keys, Corp_brand_name, corp_sub_sector, category, category_group_num, brand_group_num

</details>
<!---------------------Dimesion of Alerting-------------------->

<details>
  <summary> Microsoft Azure Storage Explorer </summary>

<br/>

Subscription : prod05, prod03

Storage Account / Blob / Container / Files

</details>
<!------------------- Azure Storage Explorer ----------------------->

<details>
  <summary> Databricks </summary>

<br/>

Databricks Notebooks : Classification of Notebook based on job done

SDO_Common Notebook, SDO_Sandbox Notebook

```powershell
Workspace/SDO_Alerts_US/DDAPI
│
├── 1.1 Daily_tables 
├── 1.2 Ingest_PG_Dimensions
├── 1.2 Ingest_CCA_Feed
├── 2.1 Validate_CCA_Feed
├── 2.2 Ingest_PG_Dimensions
├── 3.1 Ingest_PG_Dimensions
├── 3.2 Ingest_PG_Dimensions
├── 4.0 Rule_Engine_Notebook
├── 5.1 Merge_data_Notebooks
├── 6.1 Validate_Sending_Alerts_Notebooks
└── 6.2 Final_Sending_Alerts
```

DDAPI Database Creation and Ownership 

**DDAPI_Daily_Tables**, Daily Data for all retailers (From DDAPI) 

**Ingest_CCA_Feed** -  Load CCA Data, Append the latest unique data to raw CCA_Repo
- Few important columns : data_provider_key, secure_group_key, ssid in POS for Mapping
- Calendar table, product_categories, Product_Dimension_Table

**Validate_CCA_Feed** - Pure Duplicate Check, Duplicate Checks on combinations, count SOP difference with past 2 days

- CCA Source Feed Tables
- POS Tables
- Create Static Tables
- Rules Engine
- Recovered Sales
- Self Service Portal : Alert Configuration, Cluster Configuration
- DRC = Dim

</details>
<!-------------------DataBricks----------------------->

<details>
  <summary>Schema and Delta Tables</summary>

<br/>

- Source Feed tables
- Facts tables
- Dimension tables
- Configuration tables


Schemas :
```sql
syn_alerts_raw
syn_alerts_processing
syn_alerts_refined
syn_alerts_output
sdo_commons



```
Tables :
```sql
syn_alerts_raw.facts
syn_alerts_refined.dim_retailer
syn_alerts_refined.dim_store_retailer
syn_alerts_refined.dim_product_retailer
syn_alerts_refined.dim_retailer_configuration
syn_alerts_refined.rules_engine_config
syn_alerts_refined.fact_alert_answers_repo  where site_id = 3738149

sdo_common.sdo_store_dict where tdlinc in(1746195, 2233489)


_ddapi_osa_data.fact_osa_ddapi_retailer1,2,3
_ddapi_osa_data.fact_osa_ddapi_repo
```
Important Columns
```
coverage
```

| data_provider_key  | secure_group_key | src_id | data_provider_name |
| 1000010175353      | 171980           | 3995   | Albertsons |
| 1000010175353      | 130089           | 3845   | Big Lots   |
| 10000101-----      | 130047           | 3740   | Family Dollar |
| 10000101-----      | 130045           | 3738   | Kroger  |
| 10000101-----      | 130021           | 3484   | Meijer |
| 10000100296230     | 130003           | 1434   | SAMs   |
| 10000101751979     | 171760           | 3940   | Target |

</details>

---

## SDO Alerts terms and process

- CCA Rules Engine and Ranking
- Daily Operations : Monitoring the ADF Pipeline
- Notebook Summary Details
- Notebook Tables Summary
- SDO Auto Alerts Design Document
- PI(Phantom Inventory) and OOS(Out of Stock) Responses and Flags
- OSA (On-Shelf Availability) Rootcause
- Store-SKU
- PowerBI Syndicated Alerts Life Cycle Summary
- Response Processing Logic
- New Retailer Onboarding

## Works related to SDO Projects

1. Prioritizing 10 doors in Meijer(Retailer) for Fabric Care(Category)
2. SKU Prioritization logic implementation for Albertsons InstaCart(Vendor)
3. Covering SAM's (Retailer) dynamically top 30 store lists to weekly static top 30 doors.
4. DD API Migration

<!--------------WinSCP SFTP---------------------------->
<details>
  <summary> <b>WinSCP</b> </summary>

<br/>

- We use WinSCP to send the Alerts and get the response via SFTP to Server and Server to SFTP.

- We does it through Databricks but in case of any connection issue or failure or something like that we sometime do manually. 

- But make sure that we have place the file correctly we monitor the WinSCP SFTP.

WinSCP is a popular, free, and open-source SFTP, FTP, FTPS, SCP, S3, and WebDAV client for Windows, designed for secure file transfers between a local computer and remote servers.

**[Introducing WinSCP](https://winscp.net/eng/index.php)** <br/>
WinSCP is an open source free SFTP client, FTP client, WebDAV client, S3 client and SCP client and file manager for Windows. Its main function is file transfer between a local and a remote computer. Beyond this, WinSCP offers scripting and basic file manager functionality.

**[Connecting via SFTP]()** <br/>
To connect to an SFTP server using WinSCP: <br/>
**1. Download and install WinSCP from the official site or SourceForge.**

**2. Open WinSCP and use the Site Manager to configure a new session:**
- File protocol: Select SFTP.
- Host name: Enter the server’s IP address or domain.
- Port: Default is 22 for SFTP.
- User name: Enter your username.
- Password: Enter your password (or use a private key for key-based authentication). 

**3. For SSH key authentication:**
- Go to Advanced > SSH > Authentication.
- Select your private key file (.ppk, .pem, etc.).
- If using a .pem file, WinSCP will prompt to convert it to .ppk.

**4. Click Login. Confirm the server’s fingerprint if prompted.**

**5. Once connected, transfer files by dragging them between the local (left) and remote (right) panels.**

</details>

<!--------------------- CCA Feed -------------------------->
<details>
  <summary>  <b> CCA(Customer Collaborative Analytics) </b> </summary>

<br/>

Customer Collaborative Analytics refers to a data-driven approach where cross-functional teams—such as marketing, sales, customer service, product, and leadership—work together using shared data and insights to improve customer experiences, drive strategic decisions, and solve business problems collectively.

**Key Components of Customer Collaborative Analytics**
- **Unified Data Access**: Integrates customer data from multiple touchpoints (online/offline, social media, surveys, CRM, call centers) into a centralized, single source of truth.
- **Real-Time Insights**: Enables teams to analyze customer behavior, sentiment, and journey metrics in real time, supporting proactive decision-making. 
- **Cross-Team Collaboration**
- **Role-Based Governance**: Ensures data security and compliance (e.g., GDPR, HIPAA) through fine-grained access controls, while enabling appropriate collaboration

**Tools & Platforms**
- **Power BI**: Enables secure, role-based collaboration with workspaces, data sensitivity labeling, and real-time data access monitoring.
- Many other plaforms like Count, Adobe Customer Journey Analytics etc

> Note: True customer collaborative analytics requires both the right technology (cloud data warehouses like Snowflake, modern BI tools) and a culture that encourages data sharing, transparency, and cross-functional engagement.

**Benefits**
- **Improved Customer Experience**: Identifies pain points and opportunities across the customer journey, enabling personalized, omnichannel service.
- **Faster Decision-Making**: Reduces time-to-insight by allowing business users to explore data independently while collaborating with data teams. 
- **Enhanced Alignment**: Aligns teams around shared goals—such as reducing churn, increasing retention, or boosting NPS—by ensuring everyone uses the same data and metrics. 
- **Innovation Through Insight**: Uncovers hidden patterns in customer feedback and behavior, informing product development, marketing strategies, and service improvements.


</details>

<!--------------------- DD API -------------------------->
<details>
  <summary> <b>DD (Datadog) API</b> </summary>

<br/>

> The Datadog API is an HTTP REST API. The API uses resource-oriented URLs to call the API, uses status codes to indicate the success or failure of requests, returns JSON from all requests, and uses standard HTTP response codes. Use the Datadog API to access the Datadog platform programmatically.

- The Datadog API is a RESTful HTTP API that enables programmatic access to the Datadog platform for monitoring, analytics, and management tasks

- It supports read and write operations to submit metrics, manage dashboards, create monitors, send logs, and more.

[DD API](https://docs.datadoghq.com/api/latest/?tab=java)

**Key Features** <br/>

**Resource-Oriented URLs**: Uses standard HTTP methods (GET, POST, PUT, DELETE) and JSON for data exchange. 

**Authentication**: Requires API Key (DD-API-KEY) for all requests and Application Key (DD-APPLICATION-KEY) for management endpoints. 

**Endpoints by Function:** <br/>
- `Metrics API`: Submit custom metrics (e.g., gauge, counter) with tags.
- `Logs API`: Send logs directly to Datadog, including support for gzip compression.
- `Monitors API`: Create, update, and manage alerts.
- `Dashboards API`: Programmatically build and manage visualizations.
- `Synthetics API`: Manage synthetic tests and retrieve results.
- `SLOs API`: Track and manage Service Level Objectives.
- `Events API`: Post and retrieve events from the event stream. 

**Getting Started** <br/>
- `Obtain Keys`: Generate API and Application Keys from Organization Settings > API Keys and Application Keys in your Datadog account. 
- `Make API Calls`: Use headers like DD-API-KEY: <your_key> and DD-APPLICATION-KEY: <your_app_key> in requests. 
- `Use Client Libraries`: Official client libraries are available for Python, Java, Go, Ruby, TypeScript, and Rust to simplify integration. 

</details>
<!--------------technical terms---------------------------->
<details>
  <summary> <b>Technical terms involve in SDO Alerting</b> </summary>


**PI(Phantom Inventory)**
- Phantom Inventory (PI) refers to a situation where inventory systems report that products are available, 
but they are not actually present on the shelves or in stock.
- This discrepancy often arises due to replenishment errors, shrinkage (theft or damage),
  scanning inaccuracies, or improper handling, leading to lost sales and inaccurate demand forecasting. 

**OOS(Out of Stock)**
- Out of Stock (OOS) describes when a product is unavailable for purchase—either because it is physically missing from the shelf or
  due to a system error.
- OOS events begin when the last saleable unit is removed and end when the item is replenished

**OSA (On-Shelf Availability)** 
- On-shelf availability, or OSA for short, is the number of products that are immediately available for consumers to purchase.
  This defines success in retail and consumer packaged goods sectors because it dictates how quickly replenishable items must be
  stocked up upon consumption.

- On-Shelf Availability (OSA) is a key performance metric in retail and data analytics that measures the percentage of time a product
is physically available on the shelf for customers to buy.
- It is calculated as the ratio of available SKUs to total SKUs across stores.
- A high OSA (ideally over 98%) is critical for maximizing sales, as even a 2% drop in OSA can lead to a 1% loss in sales.
- OSA is influenced by three stages: warehouse availability, store availability, and shelf availability.

**SKU**
- Stock Keeping Unit) is a unique alphanumeric code assigned by a retailer or seller to identify and track individual products or
  product variations in inventory.

- Unlike universal codes like UPCs, SKUs are internal identifiers created by the business itself,
   allowing for customized tracking of attributes such as brand, size, color, style, and price.

- Purpose: SKUs enable efficient inventory management by helping businesses monitor stock levels,
  track sales by product, automate reordering, prevent stockouts, and manage multi-channel sales. 

- Format: Typically 4 to 12 characters long, SKUs are alphanumeric (a mix of letters and numbers), making them human-readable and customizable.

- Uniqueness: Each product variation (e.g., a small red t-shirt vs. a medium blue one) has its own SKU, ensuring precise tracking

- Usage: Used across retail, e-commerce, warehousing, and logistics. SKUs can be scannable via barcodes but are not required to be.

**SKU vs UPC**
- Key Difference from UPC:
  - While UPCs are standardized and universal (used across all retailers), SKUs are unique to each business
  - meaning the same product may have different SKUs across different companies.

SKUs are foundational to modern inventory systems and are essential for operational efficiency, scalability, 
and data-driven decision-making in sales and supply chain management.

</details
