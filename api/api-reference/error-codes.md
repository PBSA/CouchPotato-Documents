# Error Codes

## **400 - Bad Request**

### **BOS Errors**

#### **450 - Not normalized incident**

**Incident message contained either an invalid sport of league \(event group\).**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 450 | Not normalized incident | Object of type [BOS Schema](../bos-schema.md) |

#### **451- Invalid data format**

**Incident message was incorrectly formed.**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 451 |  **Invalid data format** | Object of type [BOS Schema](../bos-schema.md) |

### **General Errors**

#### **460 - Invalid sport**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 460 |  **Invalid sport \[sport\]** | Try one of: \[list of valid sports\] |

#### **461 - Invalid league**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| 461 |  **Invalid league \[league\]** | Try one of: \[list of valid leagues\] |

#### **462 - Invalid home team**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| **462** |  **Invalid home team \[team\]** | Try one of: \[list of valid teams\] |

#### **463 - Invalid away team**

| **Sub Code** | Title | Message |
| :--- | :--- | :--- |
| **463** |  **Invalid away team \[team\]** | Try one of: \[list of valid teams\] |

#### **464 - Invalid start date/time**

#### **465 - Duplicate teams**

#### **466 - Invalid user**

### **Add Game Errors**

#### **470 - Add new game parameter error\(s\)**

#### **471 - Failed to get last event id**

#### **472 - Failed to add new event**

#### **473 - Failed to get new event id**

#### **474 - Failed to add new game**

#### **475 - Failed to get new game id**

#### **476 - Failed to update game progress**

### **Start Game Errors**

#### **480 - Start game parameter error\(s\)**

#### **481 - Whistle start time is before start time**

#### **482 - Failed to update game progress**

#### **483 - Game must not have already started**

### **Add Scores Errors**

#### **485 - Add score parameter error\(s\)**

#### **486 - Game must be in progress**

#### **487 - Failed to add scores**

### **Finish Game Errors**

#### **491 - Finish parameter error\(s\)**

#### **492 - Whistle end time is before whistle start time**

### **Cancel Game Errors**

#### **495 - Canceled parameter error\(s\)** 

