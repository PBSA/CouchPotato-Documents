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

