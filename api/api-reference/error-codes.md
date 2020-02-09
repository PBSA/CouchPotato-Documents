# Response Codes

## 200 - Success

## **400 - Bad Request**

### **BOS Errors**

| **Sub Code** | Title | Description | Response |
| :--- | :--- | :--- | :--- |
| 450 | **Not normalized incident** | Incident message contained either an invalid sport or league \(event group\) |  |
| 451 |  **Invalid data format** | Incident message was incorrectly formed. |  |

### **General Errors**

**460 - Invalid sport**

**461 - Invalid league**

**462 - Invalid home team**

**463 - Invalid away team**

**464 - Invalid start date/time**

**465 - Duplicate teams**

**466 - Invalid user**

### **Add Game Errors**

**470 - Add new game parameter error\(s\)**

**471 - Failed to get last event id**

**472 - Failed to add new event**

**473 - Failed to get new event id**

**474 - Failed to add new game**

**475 - Failed to get new game id**

**476 - Failed to update game progress**

### **Start Game Errors**

**480 - Start game parameter error\(s\)**

**481 - Bad whistle start time**

### **Finish/Cancel Game Errors**

**490 - Result parameter error\(s\)**

**491 - Finish parameter error\(s\)**

**492 - Canceled parameter error\(s\)**  


**495 - Bad whistle end time**  


