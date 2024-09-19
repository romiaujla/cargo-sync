# Cargo-Sync Database Design Documentation

This document provides detailed information about the tables and columns in the Cargo-Sync database.

Table of contents

|Table Name|Description|
|-|-|
|[Company](#company)|A table that holds company information|

---

## Tables

### Company

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`company_id`| Primary key|`integer`|<span style="color:red; font-weight:bold;">X</span>||
|`name`|Name of the company|`varchar(255)`|<span style="color:red; font-weight:bold;">X</span>||
|`doing_business_as`|If the company operates under a different name.|`varchar(255)`|✓||
|`motor_carrier_number`|Motor Carrier Number provided by the FMCSA, for companies registered with FMCSA.|`integer`|✓||
|`dot_number`|Department of Transportation (DOT) Number, i.e. required for interstate commerce in the USA.|`integer`|✓||
|`scac_code`|Standard Carrier Alpha Code (SCAC), it is a unique code for transportation companies.|`varchar(255)`|✓||
|`ein`|Employer Identification Number, also called Tax identification number for businesses.|`varchar(255)`|<span style="color:red; font-weight:bold;">X</span>|


