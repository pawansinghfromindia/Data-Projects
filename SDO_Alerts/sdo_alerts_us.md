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

### Tech or Stacks
- Azure Portal
- Databricks
- Microsoft Azure Storage Explorer

---
<!--------------------------------------------------------------------->
## SDO Alerts US and CA

| Vendor            |
|-------------------|
| ACOSTA            |
| Crossmark         |
| Albertson         |



| Retailers     | Secure_Group_Key | SSID   |
|---------------|------------------|--------|
| Walmart       | 130052           |        |  
| Loblaws       | 130027           |        |
| Kroger        | 130045           | 3738   |
| Meijer        | 130021           | 3484   |
| SAMS          | 130058           |        |
| FAMILY DOLLAR |                  |        |
| TARGET        | 171760           |        |
| COSCO         | 171760           |        |
| Harris Teeter | 171760           |        |


| Alerting Type  |
|----------------|
| 3PL            |
| DA             |
| EA             |

> - **3PL = Third Party Logistics**
> - **DA = Direct Alerting**
> - **EA = External Alerting**

| Status       |
|--------------|
| Active       |
| NonActive    |


|             Chronicity               |
|--------------------------------------|
| Active ExtremeChronic ```A-EC```     |
| Active Chronic ```A-C```             |
| Active NonChronic ```A-NC```         |
| NonActive ExtremeChronic ```NA-EC``` |
| NonActive Chronic ```NA-C```         |
| NonActive NonChronic ```NA-NC```     |
| NonActive ExtremeChronic ```SOA-EC```|
| NonActive Chronic ```SOA-C```        |
| NonActive NonChronic ```SOA-NC```    |

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
```
Tables :
```sql
syn_alerts_raw.facts
syn_alerts_refined.dim_store_retailer
syn_alerts_refined.dim_product_retailer
syn_alerts_refined.dim_retailer_configuration
syn_alerts_refined.rules_engine_config
```

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
