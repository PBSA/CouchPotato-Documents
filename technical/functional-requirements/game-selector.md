# Game Selector

The Game Selector is opened by clicking on the day cell of any calendar. The Game Selector is the engine behind all of the game incidents that are created and the posted to BOS.

![](../../.gitbook/assets/screen-shot-2020-03-09-at-9.47.48-am.png)

The Game Selector is both used for creating new games/matches and then moving each game through the following standard incident workflow of create -&gt; in\_progress -&gt; result -&gt; finished.

The selector can also be used to Cancel or Delete games.

## Add Game

To add new game use the input fields at the bottom of the screen and then click on the `ADD` button.

![](../../.gitbook/assets/screen-shot-2020-03-09-at-10.14.02-am.png)

**Captions**

| Text/Image | Type | Comments |
| :--- | :--- | :--- |
| Start | Static |   |
| Home Team | Static |   |
| Away Team | Static |  |

**Inputs**

| Name | Type | Constraints |
| :--- | :--- | :--- |
| Start | Date Selector |  Any valid date |
| Home Team | Drop Down selector | Drop down list of all teams associated with the selected sport and league. |
| Away  | Drop Down selector | Drop down list of all teams associated with the selected sport and league. |

**Actions**

| Caption | Type | Action |
| :--- | :--- | :--- |
| ADD +  | Button | Add the game to the list of created games. |

**Validation**

| **Exception** | Error Message |
| :--- | :--- |
| No start time | Start time not entered |
| Home Team | No home team selected |
| Away Team | No away team selected |
| Home Team and Away Team must be different | Teams must be different |

