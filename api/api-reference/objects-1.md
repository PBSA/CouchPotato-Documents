# Objects

## BOS Objects

The following objects are used to pass data to, or objects from response messages, the five API endpoints:

* \`\`[`add_game`](./#add_game)\`\`
* \`\`[`start_game`](./#start_game)\`\`
* \`\`[`add_Score`](./#add_score)\`\`
* \`\`[`finish_Game`](./#finish_game)\`\`
* `cancel_Game`

### create

Parameters for new BOS incident message to create a game and add to Couch Potato database.

{% tabs %}
{% tab title="Object" %}
| Parameter | Description | Type | Required |
| :--- | :--- | :--- | :--- |
| `sport` | Sport name | String | Yes |
| `league` | League \(Event Group\) of sport | String | Yes |
| `home` | Home team name | String | Yes |
| `away` | Away team name | String | Yes |
| `start_time` | Start date/time of game | Date | Yes |
| `user` | Current user id | Number | Yes |
{% endtab %}

{% tab title="Example" %}
```csharp
{
  "sport": "Soccer",
  "league": "EPL",
  "home": "Norwich City",
  "away": "Manchester City",
  "start_time": "2020-02-04T18:33:00.000Z",
  "user": 35,
  "match_id": 60
}
```
{% endtab %}
{% endtabs %}

### in\_progress

Parameters for new BOS incident message to start a game and add to Couch Potato database.

{% tabs %}
{% tab title="Object" %}
| Parameter | Description | Type | Required |
| :--- | :--- | :--- | :--- |
| `sport` | Sport name | String | Yes |
| `league` | League \(Event Group\) of sport | String | Yes |
| `home` | Home team name | String | Yes |
| `away` | Away team name | String | Yes |
| `start_time` | Start date/time of game | Date | Yes |
| `whistle_start_time` | Actual time the game started | Date | Yes |
| `match_id` | Unique match identifier | Number | Yes |
{% endtab %}

{% tab title="Example" %}
```csharp
{
  "sport": "Soccer",
  "league": "EPL",
  "home": "Norwich City",
  "away": "Manchester City",
  "start_time": "2020-02-04T18:33:00.000Z",
  "match_id": 60,
  "whistle_start_time": "2020-02-04T18:40:00.000Z"
}
```
{% endtab %}
{% endtabs %}

### result 

Parameters for new BOS incident message to set the score of a game and add to Couch Potato database.

{% tabs %}
{% tab title="Object" %}
| Parameter | Description | Type | Required |
| :--- | :--- | :--- | :--- |
| `sport` | Sport name | String | Yes |
| `league` | League \(Event Group\) of sport | String | Yes |
| `home` | Home team name | String | Yes |
| `away` | Away team name | String | Yes |
| `start_time` | Start date/time of game | Date | Yes |
| `home_score` | The score for the home team | Number | Yes |
| `away_score` | The score for the away team | Number | Yes |
| `match_id` | Unique match identifier | Number | Yes |
{% endtab %}

{% tab title="Example" %}
```csharp
{
  "sport": "Soccer",
  "league": "EPL",
  "home": "Norwich City",
  "away": "Manchester City",
  "start_time": "2020-02-04T18:33:00.000Z",
  "home_score": 1,
  "away_score": 4,
  "match_id": 60
}
```
{% endtab %}
{% endtabs %}

### finish 

Parameters for new BOS incident message to finish/complete a game and add to Couch Potato database.

{% tabs %}
{% tab title="Object" %}
| Parameter | Description | Type | Required |
| :--- | :--- | :--- | :--- |
| `sport` | Sport name | String | Yes |
| `league` | League \(Event Group\) of sport | String | Yes |
| `home` | Home team name | String | Yes |
| `away` | Away team name | String | Yes |
| `start_time` | Start date/time of game | Date | Yes |
| `whistle_end_time` | The time the game ended | Date | Yes |
| `away_score` | The score for the away team | Number | Yes |
| `match_id` | Unique match identifier | Number | Yes |
{% endtab %}

{% tab title="Example" %}
```csharp
{
  "sport": "Soccer",
  "league": "EPL",
  "home": "Norwich City",
  "away": "Manchester City",
  "start_time": "2020-02-04T18:33:00.000Z",
  "match_id": 60,
  "whistle_end_time": "2020-02-04T20:30:00.000Z"
}
```
{% endtab %}
{% endtabs %}

### canceled

Parameters for new BOS incident message to cancel a game and add to Couch Potato database.

{% tabs %}
{% tab title="Object" %}
| Parameter | Description | Type | Required |
| :--- | :--- | :--- | :--- |
| `sport` | Sport name | String | Yes |
| `league` | League \(Event Group\) of sport | String | Yes |
| `home` | Home team name | String | Yes |
| `away` | Away team name | String | Yes |
| `start_time` | Start date/time of game | Date | Yes |
| `match_id` | Unique match identifier | Number | Yes |
{% endtab %}

{% tab title="Example" %}
```csharp
{
  "sport": "Soccer",
  "league": "EPL",
  "home": "Norwich City",
  "away": "Manchester City",
  "start_time": "2020-02-04T18:33:00.000Z",
  "match_id": 60,
}
```
{% endtab %}
{% endtabs %}

### Add Game Success Response 

Object attributes for a 200 response from an [add\_game](./#add_game) call.

{% tabs %}
{% tab title="Attributes" %}
| Name | Text |
| :--- | :--- |
| status | Always 200 |
| title | Game added |
| message | \[home \] v \[away \] - \[start\_time\] |
{% endtab %}

{% tab title="Example" %}
```java
{
    "status":"200",
    "title":"Game added",
    "message":"Arsenal v Liverpool - 2020-02-25T01:33:00.000Z"
}
```
{% endtab %}
{% endtabs %}

### Start Game Success Response 

Object attributes for a 200 response from an [start\_game](./#start_game) call.

{% tabs %}
{% tab title="Attributes" %}
| Name | Text |
| :--- | :--- |
| status | Always 200 |
| title | Game started |
| message | \[home \] v \[away \] - \[whistle\_start\_time\] |
{% endtab %}

{% tab title="Example" %}
```java
{
    "status":"200",
    "title":"Game started",
    "message":"Chelsea v Chelsea - [whistle_start_time]2020-02-04T18:05:47.736Z"
}
```
{% endtab %}
{% endtabs %}

### Add Score Success Response 

Object attributes for a 200 response from an [add\_score](./#add_score) call.

{"status":"200","title":"Scores added","message":"Chelsea 4 v Arsenal 2"}

{% tabs %}
{% tab title="Attributes" %}
| Name | Text |
| :--- | :--- |
| status | Always 200 |
| title | Scores added |
| message | \[home \] \[home\_score\]v \[away \]\[away\_score\]  |
{% endtab %}

{% tab title="Example" %}
```java
{
    "id":"78359ca1-7cf1-4272-abdd-03101d3a0eb1",
    "id_approve":"4428ac99-e623-4f13-af9a-953c20b0fd97",
    "message":
        {
            "arguments":
                {
                   "home_score": 4,
                   "away_score": 2
                },
            "call":"create",
            "id":
                {
                    "away":"Manchester City",
                    "event_group_name":"EPL",
                    "home":"Chelsea",
                    "sport":"Soccer",
                    "start_time":"2020-02-04T18:30:00.000Z"
                },
            "provider_info":
                {
                    "match_id":60,
                    "name":"couch-potato",
                    "pushed":"2020-02-06T18:19:46.000Z",
                    "source":"direct string input",
                    "source_file":""
                },
            "timestamp":"2020-02-06T18:19:46.000Z",
            "unique_string":"2020-02-04t18:33:00.000zsoccereplchelseamanchester_citycreate20192020"
            },
    "result":"processing"
    }
}
```
{% endtab %}
{% endtabs %}

