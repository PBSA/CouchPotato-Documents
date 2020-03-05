# League Tabs

The leagues tab runs vertically down the left side of the dashboard and displays one tab for each league that is configured for the selected sport. The tabs are dynamic and configured through the MySql database [`Leagues`](../../../database/objects/tables.md#leagues) table. 

![](../../../.gitbook/assets/screen-shot-2020-03-02-at-4.06.55-pm.png)

The order the leagues tabs are displayed in is defined by their `id` value in the [`Leagues`](../../../database/objects/tables.md#leagues) table.

There is no limit on the number of sports tabs that can be created. If the tabs reach the vertical limit of the application then they will stack in to multiple columns. Realistically there should never be so many leagues enabled at any one time to cause the tabs to be stacked.

{% hint style="danger" %}
**Important**: The leagues tabs must be 100% configurable through the database only. Leagues must be added or removed without any code changes.
{% endhint %}

Clicking on any unselected tab will change the calendar display to show only events for the selected sport and league.

### **Captions**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Text</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Comments</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">[league name]</td>
      <td style="text-align:left">Dynamic</td>
      <td style="text-align:left">Value set in <a href="../../../database/objects/tables.md#leagues"><code>Leagues</code></a> table.</td>
    </tr>
    <tr>
      <td style="text-align:left">[icon]</td>
      <td style="text-align:left">Dynamic</td>
      <td style="text-align:left">
        <p>Path and name defined in the <code>icon</code> column of the <a href="../../../database/objects/tables.md#leagues"><code>Leagues</code></a> table.</p>
        <p>The icon itself must exist in the corresponding <code>asset/imgs/leagues</code> folder
          in the application.</p>
      </td>
    </tr>
  </tbody>
</table>### **Actions**

| Caption | Type | Action |
| :--- | :--- | :--- |
| \[League\] | Text | Change calendar to the selected league of the selected sport. |

