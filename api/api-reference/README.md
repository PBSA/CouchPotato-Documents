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
* `create_message`: Object of type [create](objects-1.md#create-message)
{% endtab %}

{% tab title="Response" %}
* Success 
  * `status`: 200
  * `title`: Game added
  * `message`[: Add Game Success Response](objects-1.md#add-game-success-response)
* Failure
  * `status`: 400: Bad Request
  * `subcode`:  One of **`Error Objects`**
  * `title`: One of ``**`Error Objects`**
  * `message`: One of **`Error Objects`**

**`Error Objects`**

* [BOS Errors](error-codes.md#bos-errors)
* [General Errors](error-codes.md#general-errors)
* [Add Game Errors](error-codes.md#add-game-errors)
{% endtab %}

{% tab title="Example" %}
```typescript
var http: HttpClient;
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
        <p>400<a href="error-codes.md#472-failed-to-add-new-event">[472]: Failed to add new event</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>games</em>
      </td>
      <td style="text-align:left">Add new game</td>
      <td style="text-align:left">
        <p>200: Success</p>
        <p>400<a href="error-codes.md#474-failed-to-add-new-game">[474]: Failed to add new game</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>progress</em>
      </td>
      <td style="text-align:left">And new progress record. Set <code>status</code> to 0 (Not Started)</td>
      <td
      style="text-align:left">
        <p>200: Success</p>
        <p>400<a href="error-codes.md#476-failed-to-update-game-progress">[476]: Failed to add  progress</a>
        </p>
        </td>
    </tr>
  </tbody>
</table>## start\_game

Starts an existing game and sends an in\_progress incident message to BOS.

```http
POST /start_game/:in_progress_message
```

**Header**

```http
{'Content-Type' : 'application/json'}
```

{% tabs %}
{% tab title="Parameters" %}
* `in_progress_message`: Object of type [in\_progress](objects-1.md#in-progress-message)
{% endtab %}

{% tab title="Response" %}
* Success 
  * `status`: 200
  * `title`: Game added
  * `message`: [Start Game Success Response](objects-1.md#start-game-success-response)
* Failure
  * `status`: 400: Bad Request
  * `subcode`:  One of **`Error Objects`**
  * `title`: One of ``**`Error Objects`**
  * `message`: One of **`Error Objects`**

**`Error Objects`**

* [BOS Errors](error-codes.md#bos-errors)
* [General Errors](error-codes.md#general-errors)
* [Start Game Errors](error-codes.md#start-game-errors)
{% endtab %}

{% tab title="Example" %}
```typescript
var http: HttpClient;
var headers = new HttpHeaders({'Content-Type' : 'application/json'});
var postData:any = {};
postData.sport = "Soccer";
postData.league = "EPL";
postData.user = 1;
postData.home = "Chelsea";
postData.away = "Manchester United";
postData.start_time = "2020-02-04T18:33:00.000Z"
postData.whistle_start_time = "2020-02-04T18:45:00.000Z"
http.post(url + "start_game.php?" , postData, {headers}).map();
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
      <td style="text-align:left"><em>progress</em>
      </td>
      <td style="text-align:left">Update progress record. Set <code>status</code> to 1 (In Progress)</td>
      <td
      style="text-align:left">
        <p>200: Success</p>
        <p>400[<a href="error-codes.md#482-failed-to-update-game-progress">483] Failed to update progress record.</a>
        </p>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>games</em>
      </td>
      <td style="text-align:left">Add whistle start time to <code>whistle_start_time</code>
      </td>
      <td style="text-align:left">
        <p>200: Success</p>
        <p>400[<a href="error-codes.md#482-failed-to-update-game-progress">482]</a> Failed
          to add whistle start time.</p>
      </td>
    </tr>
  </tbody>
</table>## add\_score

Add scores to a game.

```http
POST /add_score/:result_message
```

**Header**

```http
{'Content-Type' : 'application/json'}
```

{% tabs %}
{% tab title="Parameters" %}
* `result_message`: Object of type [result](objects-1.md#result)
{% endtab %}

{% tab title="Response" %}
* Success 
  * `status`: 200
  * `title`: Game added
  * `message`: [Add Score Success Response](objects-1.md#add-score-success-response)
* Failure
  * `status`: 400: Bad Request
  * `subcode`:  One of **`Error Objects`**
  * `title`: One of ``**`Error Objects`**
  * `message`: One of **`Error Objects`**

**`Error Objects`**

* [BOS Errors](error-codes.md#bos-errors)
* [General Errors](error-codes.md#general-errors)
* [Add Game Errors](error-codes.md#add-game-errors)
{% endtab %}

{% tab title="Example" %}
```typescript
var http: HttpClient;
var headers = new HttpHeaders({'Content-Type' : 'application/json'});
var postData:any = {};
postData.sport = "Soccer";
postData.league = "EPL";
postData.user = 1;
postData.home = "Chelsea";
postData.away = "Manchester United";
postData.start_time = "2020-02-04T18:33:00.000Z";
postData.home_score = 4;
postData.away_score = 2;
http.post(url + "add_score.php?" , postData, {headers}).map();
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
      <td style="text-align:left"><em>games</em>
      </td>
      <td style="text-align:left">Adds the posted scores to the <code>home_score and away_score fields.</code>
      </td>
      <td style="text-align:left">
        <p>200: Success</p>
        <p>400<a href="error-codes.md#487-failed-to-add-scores">[487]: Failed to add score.</a>
          <br
          />
        </p>
      </td>
    </tr>
  </tbody>
</table>## finish\_game

Finish a game

```http
POST /add_score/:finish_game
```

**Header**

```http
{'Content-Type' : 'application/json'}
```

{% tabs %}
{% tab title="Parameters" %}
* `finish_game_message`: Object of type [finish](objects-1.md#finish)
{% endtab %}

{% tab title="Response" %}
* Success 
  * `status`: 200
  * `title`: Game finished
  * `message`: [Finish game success response](objects-1.md#finish-game-success-response)
* Failure
  * `status`: 400: Bad Request
  * `subcode`:  One of **`Error Objects`**
  * `title`: One of ``**`Error Objects`**
  * `message`: One of **`Error Objects`**

**`Error Objects`**

* [BOS Errors](error-codes.md#bos-errors)
* [General Errors](error-codes.md#general-errors)
* [Add Game Errors](error-codes.md#add-game-errors)
{% endtab %}

{% tab title="Example" %}
```typescript
var http: HttpClient;
var headers = new HttpHeaders({'Content-Type' : 'application/json'});
var postData:any = {};
postData.sport = "Soccer";
postData.league = "EPL";
postData.user = 1;
postData.home = "Chelsea";
postData.away = "Manchester United";
postData.start_time = "2020-02-04T18:33:00.000Z";
postData.whistle_end_time = "2020-02-04T20:33:00.000Z";
http.post(url + "add_score.php?" , postData, {headers}).map();
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
      <td style="text-align:left"><em>games</em>
      </td>
      <td style="text-align:left">Add whistle end time to <code>whistle_end_time</code>
      </td>
      <td style="text-align:left">
        <p>200: Success</p>
        <p>400[492]: Failed to add whistle end time</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>progress</em>
      </td>
      <td style="text-align:left">Update progress record. Set <code>status</code> to 4 (Finished)</td>
      <td
      style="text-align:left">
        <p>200: Success</p>
        <p>400[493]: Failed to update progress record
          <br />
        </p>
        </td>
    </tr>
  </tbody>
</table>