[← Cargo Sync Documentation](../../../readme.md) [← Developer Knowledge Base](../readme.md)

# Database Naming Convention

## General Conventions
- Singular Table names
    - Use singular form for table names (e.g. `company`, `user`, `role`, etc.), as each row represents a single entity.
- Lowercase names with underscores (Snake Case)
    - Use lowercase letters and separate words with underscores: `company_name`, `company_address`.
    - This format is readable and widely supported across databases like PostgreSQL.

## Naming Conventions for Tables
- Descriptive Entity Names
    - Name tables based on the entity they represent: `company`, `user`, `load`.
- Join Tables (For Many to Many relationships)
    - For tables used to represent relationships between two entities, use both entity names, joined by an underscore, in alphabetical order.
    - E.g `load_user`, `company_user`, `equipment_load`

## Naming Convention for Columns
- Consistent Prefixes for Foreign Keys
    - Name foreign key columns using the pattern: `fk_{referenced_table}_id`.
    - E.g. `fk_company_id`, `fk_user_id`
- Use Postfixes to Distinguish Multiple Foreign Keys from the Same Table:
    - Name foreign key columns using the pattern: `fk_{referenced_table}_id_{distinguishing_property}`.
    - E.g. `fk_location_id_pick_up`, `fk_location_id_drop_off`.
- Avoid Ambiguous Names
    - Instead of just `id` for primary keys, use specific names like `company_id`, `user_id`.
- Boolean Fields
    - Use `is_` or `has_` as prefixes for boolean fields.
    - E.g. `is_active`, `has_insurance`
- Timestamps
    - Name timestamp columns clearly to indicate their purpose:
    - E.g. `created_at`, `modified_at`, `deleted_at`

## Naming Conventions for Indexes
- Use Table and Column in Index Name
    - E.g. if indexing the `email` field in the `user` table: `idx_user_email`.

## Naming Conventions for Constraints
- Unique Constraints
    - Use `uq_{table}_{column}`
    - E.g. `uq_user_email`
- Check Constraints
    - Use `chk_{table}_{column}`
    - E.g. `chk_user_age`

## Naming Conventions for Procedures and Functions
- Use Verb-Noun Pattern
    - Name procedures or functions based on their action: `get_employee_data`, `update_invoice_status`.
- Avoid Abbreviations
    - Use full words for readability. Avoid unnecessary abbreviations unless they are well understood.




