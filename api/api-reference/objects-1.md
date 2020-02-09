# Objects

## BOS Objects

The following objects are used to pass data to, or objects from response messages, the five API endpoints:

* \`\`[`add_game`](./#add_game)\`\`
* \`\`[`start_game`](./#start_game)\`\`
* \`\`[`add_Score`](./#add_score)\`\`
* `finish_Game`
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
| `match_id` | Unique match identifier | Number | No |
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
| `match_id` | Unique match identifier | Number | No |
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
| `match_id` | Unique match identifier | Number | No |
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
| `match_id` | Unique match identifier | Number | No |
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
| `match_id` | Unique match identifier | Number | No |
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
| Name | Description |
| :--- | :--- |
| id | Unique response identifier for the incident |
| id\_approve | Unique identifier for the incident approval |
| message | Message body of type [create schema](../bos-schema.md#create) |
| result | Status of operation - usually "processing" |
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
                    "season":"2019\/2020"
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

### Start Game Success Response 

Object attributes for a 200 response from an [start\_game](./#start_game) call.

{% tabs %}
{% tab title="Attributes" %}
| Name | Description |
| :--- | :--- |
| id | Unique response identifier for the incident |
| id\_approve | Unique identifier for the incident approval |
| message | Message body of type [in\_progress schema](../bos-schema.md#in_progress) |
| result | Status of operation - usually "processing" |
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
                   "whistle_start_time":"2020-02-04T18:35:00.000Z"
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



### Add Score Success Response 

Object attributes for a 200 response from an [add\_score](./#add_score) call.

{% tabs %}
{% tab title="Attributes" %}
| Name | Description |
| :--- | :--- |
| id | Unique response identifier for the incident |
| id\_approve | Unique identifier for the incident approval |
| message | Message body of type [in\_progress schema](../bos-schema.md#in_progress) |
| result | Status of operation - usually "processing" |
{% endtab %}

{% tab title="Example" %}

{% endtab %}
{% endtabs %}

