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
| fk\_user\_idx | INDEX | user | ASC |
| fk\_league\_idx | INDEX | league | ASC |

#### Foreign Keys

| Foreign Key | Referenced Table | Column | Referenced Column |
| :--- | :--- | :--- | :--- |
| fk\_user | 'couch\_potato'.'users' | user | id |
| fk\_leagues | 'couch\_potato'.'leagues' | league | name |

#### Script

```sql
CREATE TABLE `events` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `user` int(11) NOT NULL,
  `league` varchar(45) NOT NULL,
  `date` date NOT NULL,
  PRIMARY KEY (`id`),
  KEY `fk_league_idx` (`league`),
  KEY `fk_user_idx` (`user`),
  CONSTRAINT `fk_leagues` FOREIGN KEY (`league`) REFERENCES `leagues` (`name`),
  CONSTRAINT `fk_user` FOREIGN KEY (`user`) REFERENCES `users` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci
```

## games

#### Columns

| Column | Datatype | PK | NN | AI | Default |
| :--- | :--- | :--- | :--- | :--- | :--- |
| id | INT\(11\) | ✅ | ✅ | ✅ |   |
| user | INT\(11\) |  ❌  | ✅ | ❌  |   |
| event | INT\(11\) |  ❌  | ✅ | ❌  |   |
| hometeam | VARCHAR\(100\) | ❌   | ✅ | ❌  |   |
| awayteam | VARCHAR\(100\) | ❌   | ✅ | ❌   |   |
| starttime | VARCHAR\(12\) | ❌   | ✅ | ❌   |   |
| homescore | INT\(11\) | ❌   |  ❌   | ❌   |   |
| awayscore | INT\(11\) | ❌   | ❌    | ❌   |   |
| whistle\_start\_time | VARCHAR\(32\) | ❌   | ❌    | ❌   |   |
| whistle\_end\_time | VARCHAR\(32\) | ❌   | ❌    | ❌   |   |

#### Indexes

| Index | Type | Columns | Order |
| :--- | :--- | :--- | :--- |
| PRIMARY | PRIMARY | id, user | ASC |
| user\_idx | INDEX | user | ASC |
| event\_idx | INDEX | event | ASC |

#### Foreign Keys

| Foreign Key | Referenced Table | Column | Referenced Column |
| :--- | :--- | :--- | :--- |
| fk\_event | 'couch\_potato'.'events' | event | id |

#### Script

```sql
CREATE TABLE `games` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `user` int(11) NOT NULL,
  `event` int(11) NOT NULL,
  `hometeam` varchar(100) NOT NULL,
  `awayteam` varchar(100) NOT NULL,
  `starttime` varchar(12) NOT NULL,
  `homescore` int(11) DEFAULT NULL,
  `awayscore` int(11) DEFAULT NULL,
  `whistle_start_time` varchar(32) DEFAULT NULL,
  `whistle_end_time` varchar(32) DEFAULT NULL,
  PRIMARY KEY (`id`,`user`),
  KEY `user_idx` (`user`),
  KEY `event_idx` (`event`),
  CONSTRAINT `fk_event` FOREIGN KEY (`event`) REFERENCES `events` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=20 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci
```

## httplog



## incidents



## leagues



## progress



## sports



## status



## teams



## users

