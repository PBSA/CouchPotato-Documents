# Notifications

The notifications panel is displayed on the right side of the dashboard and is where all notifications \(reminders\) will be posted for all games about to start or finish.

![](../../../.gitbook/assets/screen-shot-2020-03-06-at-9.49.06-am.png)

The notifications will be refreshed at a configurable millisecond interval set in `config-dataproxy.json`. The default will be 3,000 \(3 seconds\).

Each notification will take the form of a 'note' which will have the following information:

### Colour

The colour of the notes is very important and must be visibly obvious. The colour of the note is set by the following criteria:

**Green**

* Any game that is in the range 30 - 15 minutes to it's scheduled start time.
* Any game that is in the range 30 - 15 minutes from it's predicted end time.

![](../../../.gitbook/assets/screen-shot-2020-03-04-at-8.02.09-pm.png)

**Amber**

* Any game that is in the range 1 - 14 minutes to it's scheduled start time.
* Any game that is in the range 1 - 14 minutes from it's predicted end time.

![](../../../.gitbook/assets/screen-shot-2020-03-04-at-7.53.24-pm.png)

**Red**

* Any game that should have started according to its scheduled start time.
* Any game that is in the range 30 - 15 minutes to it's predicted end time.

![](../../../.gitbook/assets/screen-shot-2020-03-04-at-8.02.20-pm.png)

### Start and End Times

The notifications rely on the start and end times of each game. The start time is taken as the time entered for any game when it was created, this is the only value that can be used.

The end time is more complicated because for many sports it's very hard to predict when a game ends because of time-outs, extra-time etc. For example, a game of soccer is much more predictable because the clock doesn't stop during play. So a game is likely to be two halves of 45 minutes, 15 minutes of half-time and perhaps 5 minutes of extra time, so 45+45+15+5 = 110 minutes.

