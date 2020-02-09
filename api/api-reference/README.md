# API Reference

## add\_game

Adds a new game and sends a create incident message to BOS.

```http
POST /add_game/:create_message
```

**Header**

```http
{'Content-Type' : 'application/json'}
```

{% tabs %}
{% tab title="Parameters" %}
* `create_message`: Object of type [Create](objects-1.md#create-message)
{% endtab %}

{% tab title="Response" %}
* 200: Success
* 400: Bad Request
  * Sub codes [BOS Errors](error-codes.md#bos-errors)
  * Sub codes [General Errors](error-codes.md#general-errors)
  * Sub codes [Add Game Errors](error-codes.md#add-game-errors)
{% endtab %}

{% tab title="Example" %}
```typescript
var headers = new HttpHeaders({'Content-Type' : 'application/json'});
var postData:any = {};

postData.sport = "Soccer";
postData.league = "EPL";
postData.user = 1;
postData.home = "Chelsea";
postData.away = "Manchester United";
postData.start_time = "2020-02-04T18:33:00.000Z"
this.http.post(url + "add_game.php?" , postData, {headers}).map();
```
{% endtab %}
{% endtabs %}

**Database Operations**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Table</th>
      <th style="text-align:left">Operation</th>
      <th style="text-align:left">Response</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><em>events</em>
      </td>
      <td style="text-align:left">Add new event if this is the first game.</td>
      <td style="text-align:left">
        <p>200: Success</p>
        <p>400[472]: Failed to add new event</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>games</em>
      </td>
      <td style="text-align:left">Add new game</td>
      <td style="text-align:left">
        <p>200: Success</p>
        <p>400[474]: Failed to add new game</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>progress</em>
      </td>
      <td style="text-align:left">And new progress record. Set status to 0 (Not Started)</td>
      <td style="text-align:left">
        <p>200: Success</p>
        <p>400[472]: Failed to add progress</p>
      </td>
    </tr>
  </tbody>
</table>## start\_game

Starts an existing game and sends an in\_progress incident message to BOS.

```http
POST /add_game/:in_progress_message
```

{% tabs %}
{% tab title="Parameters" %}
* `in_progress_message`: Object of type [In Progress](objects-1.md#in-progress-message)
{% endtab %}

{% tab title="Response" %}
* 200: Success
* 400: Bad Request
  * Sub codes [BOS Errors](error-codes.md#bos-errors)
  * Sub codes [General Errors](error-codes.md#general-errors)
  * Sub codes [Start Game Errors](error-codes.md#start-game-errors)
{% endtab %}

{% tab title="Example" %}
```typescript
var postData:any = {};
postData.sport = "Soccer";
postData.league = "EPL";
postData.user = 1;
postData.home = "Chelsea";
postData.away = "Manchester United";
postData.start_time = "2020-02-04T18:33:00.000Z"
postData.whistle_start_time = "2020-02-04T18:45:00.000Z"
this.http.post(url + "start_game.php?" , postData, {headers}).map();
```
{% endtab %}
{% endtabs %}

**Database Operations**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Table</th>
      <th style="text-align:left">Operation</th>
      <th style="text-align:left">Response</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><em>events</em>
      </td>
      <td style="text-align:left">Add new event if this is the first game.</td>
      <td style="text-align:left">
        <p>200: Success</p>
        <p>400[472]: Failed to add new event</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>games</em>
      </td>
      <td style="text-align:left">Add new game</td>
      <td style="text-align:left">
        <p>200: Success</p>
        <p>400[474]: Failed to add new game</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>progress</em>
      </td>
      <td style="text-align:left">And new progress record. Set status to 0 (Not Started)</td>
      <td style="text-align:left">
        <p>200: Success</p>
        <p>400[472]: Failed to add progress</p>
      </td>
    </tr>
  </tbody>
</table>