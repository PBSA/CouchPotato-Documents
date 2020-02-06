# Objects

## BOS Objects

The following objects are used to pass data to the following five API endpoints, or objects from response messages for:

* \`\`[`add_Game`](./#add_game)\`\`
* \`\`[`start_Game`](./#start_game)\`\`
* `add_Results`
* `finish_Game`
* `cancel_Game`

### Create \(Add\) Message

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

### In Progress \(Start\) Message

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

### Result Message

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

### Finish Message

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

### Cancel\(ed\) Message

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

### Success Response Object

Object attributes from a Success: 200 response.

{% tabs %}
{% tab title="Attributes" %}
| Name | Description |
| :--- | :--- |
| id |  |
| id\_approve |  |
| message |  |

"id":"78359ca1-7cf1-4272-abdd-03101d3a0eb1","id\_approve":"4428ac99-e623-4f13-af9a-953c20b0fd97","message":{"arguments":{"season":"2019\/2020"},"call":"create","id":{"away":"Manchester City","event\_group\_name":"EPL","home":"Chelsea","sport":"Soccer","start\_time":"2020-02-04T18:30:00.000Z"},"provider\_info":{"match\_id":null,"name":"couch-potato","pushed":"2020-02-06T18:19:46.000Z","source":"direct string input","source\_file":""},"timestamp":"2020-02-06T18:19:46.000Z","unique\_string":"2020-02-04t18:33:00.000z**soccer**epl**chelsea**manchester\_city**create**20192020"},"result":"processing"}}
{% endtab %}

{% tab title="Example" %}
{"status":"200","title":"Game added","message":{"id":"78359ca1-7cf1-4272-abdd-03101d3a0eb1","id\_approve":"4428ac99-e623-4f13-af9a-953c20b0fd97","message":{"arguments":{"season":"2019\/2020"},"call":"create","id":{"away":"Manchester City","event\_group\_name":"EPL","home":"Chelsea","sport":"Soccer","start\_time":"2020-02-04T18:30:00.000Z"},"provider\_info":{"match\_id":null,"name":"couch-potato","pushed":"2020-02-06T18:19:46.000Z","source":"direct string input","source\_file":""},"timestamp":"2020-02-06T18:19:46.000Z","unique\_string":"2020-02-04t18:33:00.000z**soccer**epl**chelsea**manchester\_city**create**20192020"},"result":"processing"}}
{% endtab %}
{% endtabs %}

## 

