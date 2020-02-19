---
description: 'The following is a list of the tables in the Couch Potato database:'
---

# Tables

**Legend**:

**PK**- Primary Key

**NN** - Not Null

**AI** - Auto Increment

## errorlog

#### Columns

| Column | Datatype | PK | NN | AI | Default |
| :--- | :--- | :--- | :--- | :--- | :--- |
| id | INT\(11\) | ✅ | ✅ | ✅ |   |
| timestamp | DATETIME |  ❌  | ✅ | ❌  | CURRENT\_TIMESTAMP |
| status | VARCHAR\(4\) |  ❌  | ✅ | ❌  |   |
| subcode | VARCHAR\(4\) | ❌   | ✅ | ❌  |   |
| title | VARCHAR\(255\) |  ❌  | ✅ | ❌  |   |
| message | VARCHAR\(1000\) |  ❌  |  ❌  | ❌  |   |

#### Indexes

| Index | Type | Columns | Order |
| :--- | :--- | :--- | :--- |
| PRIMARY | PRIMARY | id | ASC |

#### Foreign Keys

None.

#### Script

```sql
CREATE TABLE `errorlog` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `timestamp` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP,
  `status` varchar(4) NOT NULL,
  `subcode` varchar(4) NOT NULL,
  `title` varchar(45) NOT NULL,
  `message` varchar(1000) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=2 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci
```

## events

#### Columns

| Column | Datatype | PK | NN | AI | Default |
| :--- | :--- | :--- | :--- | :--- | :--- |
| id | INT\(11\) | ✅ | ✅ | ✅ |   |
| user | INT\(11\) |  ❌  | ✅ | ❌  |   |
| league | VARCHAR\(45\) |  ❌  | ✅ | ❌  |   |
| date | DATE | ❌   | ✅ | ❌  |   |

#### Indexes

| Index | Type | Columns | Order |
| :--- | :--- | :--- | :--- |
| PRIMARY | PRIMARY | id | ASC |

#### Foreign Keys

None.

## 





## games

