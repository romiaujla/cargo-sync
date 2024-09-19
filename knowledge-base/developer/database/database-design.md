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
|`company_id`| Primary key|`integer`|❌||
|`name`|Name of the company|`varchar(255)`|❌||
|`doing_business_as`|If the company operates under a different name.|`varchar(255)`|✓||
|`motor_carrier_number`|Motor Carrier Number provided by the FMCSA, for companies registered with FMCSA.|`integer`|✓||
|`dot_number`|Department of Transportation (DOT) Number, i.e. required for interstate commerce in the USA.|`integer`|✓||
|`scac_code`|Standard Carrier Alpha Code (SCAC), it is a unique code for transportation companies.|`varchar(255)`|✓||
|`ein`|Employer Identification Number, also called Tax identification number for businesses.|`varchar(255)`|❌|
|[`type`](#type)| Sole Proprietorship, Partnership (GP, LP, or LLP), LLC, Inc., NPO, Co-op, Joint Venture, Trust, B-Corp, Low-Profit LLC, Close Corporation, Series LLC| `varchar(128)`|❌||
|`phone`|Company phone number|`varchar(16)`|❌||
|`email`|Company email|`varchar(32)`|❌||
|`website`|Company website|`varchar(128)`|✓||
|`primary_contact_first_name`||`varchar(128)`|||

#### Company Type

1. Sole Proprietorship
    - A business owned and run by one individual. There is no legal distinction between the owner and the business.
2. Partnership
    - General Partnership (GP): Owned by two or more people, where each partner has equal responsibility and liability.
    - Limited Partnership (LP): One or more general partners manage the business and are personally liable for debts, while limited partners have limited liability and typically only invest.
    - Limited Liability Partnership (LLP): Similar to a GP, but offers liability protection to all partners, protecting them from debts of the partnership or wrongful actions of another partner.
3. Limited Liability Company (LLC)
    - A hybrid structure that offers the liability protection of a corporation and the tax benefits of a partnership or sole proprietorship. Owners are referred to as members.
4. Corporation (Inc.)
    - C Corporation (C-Corp): A legal entity separate from its owners (shareholders). It offers strong liability protection but is subject to double taxation (once at the corporate level and again on dividends).
    - S Corporation (S-Corp): A special type of corporation that allows profits and some losses to pass through directly to owners' personal income without corporate tax. There are strict rules for ownership and profit distribution.
    - Professional Corporation (PC): A corporation for licensed professionals (e.g., doctors, lawyers). It protects owners from liability for other owners' malpractice.
5. Non-Profit Organization (NPO)
    - A corporation that operates for charitable, educational, religious, or public service purposes. It can apply for tax-exempt status with the IRS.
6. Cooperative (Co-op)
    - A business owned and operated for the benefit of those using its services. Profits and earnings are distributed among members.
7. Joint Venture
    - A temporary business partnership between two or more parties to complete a specific project or goal. It's treated like a partnership for tax purposes.
8. Trust
    - A fiduciary arrangement in which one party holds assets for the benefit of another. Trusts can operate as business entities in some cases.
9. Benefit Corporation (B-Corp)
    - A for-profit company that also pursues a social mission. They are subject to accountability standards and must report on their social and environmental performance.
10. L3C (Low-Profit Limited Liability Company)
    - A type of LLC that prioritizes a charitable mission but can also make a small profit. It’s a hybrid between an LLC and a non-profit.
11. Close Corporation
    - A type of corporation with a small number of shareholders and less formal structure. These are often family-owned businesses.
12. Series LLC
    - A unique form of LLC that allows for the creation of multiple “series” or sub-LLCs under one master LLC, often used for holding multiple assets or businesses under one umbrella.