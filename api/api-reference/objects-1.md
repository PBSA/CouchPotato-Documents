# Objects

## Create Message

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

## In Progress Message

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

## Result Message

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

## Finish Message

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

## Canceled Message



