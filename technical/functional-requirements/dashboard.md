# Dashboard

The dashboard is the main screen and is opened from the [Home Page](home-page.md) once the user enters correct account credentials \(username and password\).

![](../../.gitbook/assets/screen-shot-2020-03-02-at-2.50.48-pm.png)

The components of the dashboard are:

## Sports Tabs

The sports tab runs vertically across the dashboard and displays one tab for each sport that is enabled. The tabs are dynamic and configured through the MySql database [`Sports`](../../database/objects/tables.md#sports) table. 

{% hint style="danger" %}
**Important**: The sports tabs must be 100% configurable through the database only. Sports must be added or removed without any code changes.
{% endhint %}

**Captions**

| Text | Type | Comments |
| :--- | :--- | :--- |
| \[sports name\] | Dynamic | Value set in [`Sports`](../../database/objects/tables.md#sports) table |
| \*Required fields | Static |   |

## Leagues Tabs



## Calendar

## Notifications



## Replay



## Account Menu

