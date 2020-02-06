# Objects

## Create Message

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
  "match_id": 60,
  "whistle_start_time": "2020-02-04T18:40:00.000Z",
}
```
{% endtab %}
{% endtabs %}

## Result Message



## Finish Message



## Canceled Message



