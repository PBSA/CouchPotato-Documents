# Error Codes

## **General Errors**

### **430  - Failed to Delete League**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 430 | Failed to delete event league \[league\] | League might not exist or parameters are missing. |

### **431  - Failed to Delete Game**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 431 | Failed to delete game \[game\] | Game might not exist or parameters are missing. |

### 432 - Failed to get all games by Date Range

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 432 | Failed to get all games in the date range \[startdate\] to \[enddate\] | Invalid date range or parameters are missing |

### 433 - Failed to get all games

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 433 | Failed to get all games | None |

## **BOS Errors**

### **450 - Not normalized incident**

**Incident message contained either an invalid sport or league \(event group\).**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 450 | Not normalized incident | Object of type [BOS Schema](../bos-schema.md) |

### **451- Invalid data format**

**Incident message was incorrectly formed.**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 451 |  Invalid data format | Object of type [BOS Schema](../bos-schema.md) |

## **Incident Errors**

### **460 - Invalid sport**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 460 |  Invalid sport \[sport\] | Try one of: \[list of valid sports\] |

### **461 - Invalid league**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 461 |  Invalid league \[league\] | Try one of: \[list of valid leagues\] |

### **462 - Invalid home team**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 462 |  Invalid home team \[team\] | Try one of: \[list of valid teams\] |

### **463 - Invalid away team**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 463 |  Invalid away team \[team\] | Try one of: \[list of valid teams\] |

### **464 - Invalid start time**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 464 |  Invalid start time | Format is \[YYYY-MM-DDTHH:MM:SS.00Z\] |

### **465 - Duplicate teams**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 465 |  Invalid teams selection \[home\] v \[away\] | Teams must be different |

### **466 - Invalid user**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 466 |  Invalid user id \[user\] | The user id was invalid |

## **Add Game Errors**

### **470 - Add new game parameter error\(s\)**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 470 |  Missing parameters \[list of parameters\] | Parameters are: sport, league, home, away, start\_time, user |

### **471 - Failed to get last event id**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 471 | Failed to get last event id | None |

### **472 - Failed to add new event**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 472 | Failed to add new event | None |

### **473 - Failed to get new event id**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 473 |  Failed to get new event id | None |

### **474 - Failed to add new game**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 474 | Failed to add new game | None |

### **475 - Failed to get new game id**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 475 | Failed to get new game id | None |

### **476 - Failed to update game progress**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 476 | Failed to update game progress | None |

### **477 - Failed to add new game progress**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 477 | Failed to add new game progress | None |

### **478 - Game already exists**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 478 | Game already exists | A game can't be created more than once |

## **Start Game Errors**

### **480 - Start game parameter error\(s\)**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 480 |  Missing parameters \[list of parameters\] | Parameters are: sport, league, home, away, start\_time, whistle\_start\_time, ****match\_id |

### **481 - Whistle start time is before start time**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 481 | Whistle start time \[whistle\_start\_time\] is before the start time \[start\_time\] | The whistle start time must be equal to or after the start time. |

### **482 - Failed to add whistle start time**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 482 | Failed to add whistle start time | None |

### **483 - Failed to update game progress**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 483 | Failed to update game progress | None |

### **484 - Game must not have already started**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 484 | Game must not have already started | None |

## **Add Scores Errors**

### **485 - Add score parameter error\(s\)**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 48**5** | Missing parameters \[list of parameters\] | Parameters are: sport, league, home, away, start\_time, home\_score, away\_score, match\_id |

### **486 - Game must be in progress**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 486 | Game must not have already started | None |

### **487 - Failed to add scores**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 487 | Game must not have already started | None |

## **Finish Game Errors**

### **490 - Finish parameter error\(s\)**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 4**90** | Missing parameters \[list of parameters\] | Parameters are: sport, league, home, away, start\_time, whistle\_end\_time, match\_id |

### **491 - Whistle end time is before whistle start time**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 491 | Whistle end time \[whistle\_end\_time\] is before the whistle start time \[whistle\_start\_time\] | The whistle end time must be equal to or after the whistle start time. |

### **492 - Failed to add whistle end time**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 492 | Failed to add whistle end time | None |

### **493 - Failed to update game progress**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 493 | Failed to update game progress | None |

### **494 - Game must have a score**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 494 | Failed to update game progress | A game can't be finished until the scores are added |

## **Cancel Game Errors**

### **495 - Canceled parameter error\(s\)**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 49**5** | Missing parameters \[list of parameters\] | Parameters are: sport, league, home, away, start\_time, whistle\_end\_time, match\_id |

### **496 - Failed to update game progress**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 496 | Failed to update game progress | None  |

### **497 - Game can't be canceled**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 496 | Game can't be canceled | A game can only be canceled if it hasn't started, or if it's still in progress |

