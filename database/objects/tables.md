---
description: 'The following is a list of the tables in the Couch Potato database:'
---

# Tables

**Legend**:

**PK**- Primary Key

**NN** - Not Null

**AI** - Auto Increment

## errorlog

### Columns

| Column | Datatype | PK | NN | AI | Default |
| :--- | :--- | :--- | :--- | :--- | :--- |
| id | INT\(11\) | ✅ | ✅ | ✅ |   |
| timestamp | DATETIME |  ❌  | ✅ | ❌  | CURRENT\_TIMESTAMP |
| status | VARCHAR\(4\) |  ❌  | ✅ | ❌  |   |
| subcode | VARCHAR\(4\) | ❌   | ✅ | ❌  |   |
| title | VARCHAR\(255\) |  ❌  | ✅ | ❌  |   |
| message | VARCHAR\(1000\) |  ❌  |  ❌  | ❌  |   |

### Indexes

| Index | Type | Columns | Order |
| :--- | :--- | :--- | :--- |
| PRIMARY | PRIMARY | id | ASC |

### Foreign Keys

None.

## events





## games

