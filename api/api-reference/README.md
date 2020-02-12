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
* **`create_message`**: Object of type [create](objects-1.md#create-message)
{% endtab %}

{% tab title="Response" %}
* Success 
  * \`\`[Add Game Success Response](objects-1.md#add-game-success-response)
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
this.http.post(url + "add_game.php?" , postData, {headers}).map();
```
{% endtab %}
{% endtabs %}

## start\_game

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
* **`in_progress_message`**: Object of type [in\_progress](objects-1.md#in-progress-message)
{% endtab %}

{% tab title="Response" %}
* Success 
  *  [Start Game Success Response](objects-1.md#start-game-success-response)
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
postData.start_time = "2020-02-04T18:33:00.000Z";
postData.whistle_start_time = "2020-02-04T18:45:00.000Z";
postData.match_id: 24;
http.post(url + "start_game.php?" , postData, {headers}).map();
```
{% endtab %}
{% endtabs %}

## add\_score

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
* **`result_message`**: Object of type [result](objects-1.md#result)
{% endtab %}

{% tab title="Response" %}
* Success 
  *  [Add Score Success Response](objects-1.md#add-score-success-response)
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
postData.match_id: 24;
http.post(url + "add_score.php?" , postData, {headers}).map();
```
{% endtab %}
{% endtabs %}

## finish\_game

Finish a game

```http
POST /finish_game/:finish_game_message
```

**Header**

```http
{'Content-Type' : 'application/json'}
```

{% tabs %}
{% tab title="Parameters" %}
* **`finish_game_message`**: Object of type [finish](objects-1.md#finish)
{% endtab %}

{% tab title="Response" %}
* Success 
  *  [Finish game success response](objects-1.md#finish-game-success-response)
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
postData.match_id: 24;
http.post(url + "finish_game.php?" , postData, {headers}).map();
```
{% endtab %}
{% endtabs %}

## cancel\_game

Cancel a game

```http
POST /add_score/:cancel_game_message
```

**Header**

```http
{'Content-Type' : 'application/json'}
```

{% tabs %}
{% tab title="Parameters" %}
* **`cancel_game_message`**: Object of type [canceled](objects-1.md#canceled)
{% endtab %}

{% tab title="Response" %}
* Success 
  * [Cancel game success response](objects-1.md#cancel-game-success-response)
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
postData.match_id: 24;
http.post(url + "cancel_game.php" , postData, {headers}).map();
```
{% endtab %}
{% endtabs %}

## delete\_event

Delete an event according to the league and date.

```http
DELETE /delete_event/:date/:league
```

**Header**

```http
{'Content-Type' : 'application/x-www-form-urlencoded'}
```

{% tabs %}
{% tab title="Parameters" %}
* **`date`**: The date of the event. Format is YYYY-MM-DD \(UTC\)
* **`league`**: The name of the league
{% endtab %}

{% tab title="Response" %}
* Success 
  * 200
* Failure
  * `status`: 400: Bad Request
  * `subcode`:  
  * `title`: 
  * `message`: 
{% endtab %}

{% tab title="Example" %}
```typescript
var http: HttpClient;
var headers = new HttpHeaders({'Content-Type' : 'application/x-www-form-urlencoded'});
let httpParams = new HttpParams().set('date', '2020-02-29', 'league', 'EPL');
return this.http.delete(this.url + "delete_event.php", { 
        params: httpParams, headers: headers});
```
{% endtab %}
{% endtabs %}

## delete\_game

Delete an event according to the league and date.

```http
DELETE /delete_game/:game_id
```

**Header**

```http
{'Content-Type' : 'application/x-www-form-urlencoded'}
```

{% tabs %}
{% tab title="Parameters" %}
* **`game_id`**: The id of the game to be deleted.
{% endtab %}

{% tab title="Response" %}
* Success 
  * 200
* Failure
  * `status`: 400: Bad Request
  * `subcode`:  
  * `title`: 
  * `message`: 
{% endtab %}

{% tab title="Example" %}
```typescript
var http: HttpClient;
var headers = new HttpHeaders({'Content-Type' : 'application/x-www-form-urlencoded'});
let httpParams = new HttpParams().set('game_id', 24);
return this.http.delete(this.url + "delete_game.php", { 
        params: httpParams, headers: headers});
```
{% endtab %}
{% endtabs %}

## get\_all\_data\_by\_date\_range

Get all games data between a date range.

```http
GET /get_all_data_by_date_range/:start_date/:end_date
```

{% tabs %}
{% tab title="Parameters" %}
* **`start_date`**: The start of the date range. Format is YYYY-MM-DDTHH:MM:SS.000Z
* **`end_date`**: The end of the date range. Format is YYYY-MM-DDTHH:MM:SS.000Z
{% endtab %}

{% tab title="Response" %}
* Success 
  * 200 - List of all games between `start_date` and `end_date`
* Failure
  * `status`: 400: Bad Request
  * `subcode`:  
  * `title`: 
  * `message`: 
{% endtab %}

{% tab title="Example" %}
```typescript
this.http.get(this.url + "get_all_data_by_date_range.php", {
        params:{startdate: "2020-02-19T12:00:00.000Z", 
                enddate: "2020-02-29T12:00:00.000Z"}}).map();
```
{% endtab %}
{% endtabs %}

## get\_all\_games

Get all games.

```http
GET /get_all_games/
```

{% tabs %}
{% tab title="Response" %}
* Success 
  * 200 - List of all games
* Failure
  * `status`: 400: Bad Request
  * `subcode`:  
  * `title`: 
  * `message`: 
{% endtab %}

{% tab title="Example" %}
```typescript
this.http.get(this.url + "get_all_games.php").map()
```
{% endtab %}
{% endtabs %}

## get\_all\_sports

Get all sports.

```http
GET /get_all_sports/
```

{% tabs %}
{% tab title="Response" %}
* Success 
  * 200 - List of all sports
* Failure
  * `status`: 400: Bad Request
  * `subcode`:  
  * `title`: 
  * `message`: 
{% endtab %}

{% tab title="Example" %}
```typescript
this.http.get(this.url + "get_all_sports.php").map()
```
{% endtab %}
{% endtabs %}

## get\_games\_by\_league\_and\_date

Get all games data between a date range and for a league.

```http
GET /get_games_by_league_and_date/:league/:start_date/:end_date
```

{% tabs %}
{% tab title="Parameters" %}
* **`league:`** `The sport league (event group).`
* **`start_date`**: The start of the date range. Format is YYYY-MM-DDTHH:MM:SS.000Z.
* **`end_date`**: The end of the date range. Format is YYYY-MM-DDTHH:MM:SS.
{% endtab %}

{% tab title="Response" %}
* Success 
  * 200 - List of all games between `start_date` and `end_date`
* Failure
  * `status`: 400: Bad Request
  * `subcode`:  
  * `title`: 
  * `message`: 
{% endtab %}

{% tab title="Example" %}
```typescript
this.http.get(this.url + "get_games_by_league_and_date.php", {
        params:{league: "NFL",
                startdate: "2020-02-19T12:00:00.000Z", 
                enddate: "2020-02-29T12:00:00.000Z"}}).map();
```
{% endtab %}
{% endtabs %}

## get\_games\_by\_league

Get all games for a league.

```http
GET /get_games_by_league/:league
```

{% tabs %}
{% tab title="Parameters" %}
* **`league:`** `The league (event group).`
{% endtab %}

{% tab title="Response" %}
* Success 
  * 200 - List of all games for `league`
* Failure
  * `status`: 400: Bad Request
  * `subcode`:  
  * `title`: 
  * `message`: 
{% endtab %}

{% tab title="Example" %}
```typescript
this.http.get(this.url + "get_games_by_league.php", {
        params:{league: "NFL" }}).map();
```
{% endtab %}
{% endtabs %}

## get\_leagues\_by\_sport

Get all leagues from a league.

```http
GET /get_leagues_by_sport/:sport
```

{% tabs %}
{% tab title="Parameters" %}
* **`sport:`** The id of the sport.
{% endtab %}

{% tab title="Response" %}
* Success 
  * 200 - List of all leagues for `sport`
* Failure
  * `status`: 400: Bad Request
  * `subcode`:  
  * `title`: 
  * `message`: 
{% endtab %}

{% tab title="Example" %}
```typescript
this.http.get(this.url + "get_leagues_by_sport.php", {
        params:{sport: 0}}).map();
```
{% endtab %}
{% endtabs %}

## get\_sports\_and\_leagues



## get\_teams\_by\_league



## get\_user



## get\_witnesses



## last\_event\_id\_by\_date\_and\_league



## last\_event\_id



## last\_game\_id\_by\_date\_and\_league



## last\_game\_id



## last\_game



## run\_replay





