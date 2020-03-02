# Home Page

The home page will be the first page to load and from where the user will be able to login or create an account.

![](../../.gitbook/assets/screen-shot-2020-02-25-at-9.41.32-pm.png)

**Inputs**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Constraints</th>
      <th style="text-align:left">Placeholder Text</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">User Name</td>
      <td style="text-align:left">
        <p>Max Length: 24</p>
        <p>Min Length 8</p>
      </td>
      <td style="text-align:left">User name</td>
    </tr>
    <tr>
      <td style="text-align:left">Password</td>
      <td style="text-align:left">
        <p>Max Length: 40</p>
        <p>Min Length: 8</p>
      </td>
      <td style="text-align:left">Password</td>
    </tr>
  </tbody>
</table>**Actions**

| Caption | Type | Action |
| :--- | :--- | :--- |
| LOGIN | Button | Validate user name and password and then open the [Dashboard](dashboard.md) |
| Create Account | Text | Open the [Create Account](create-account.md) screen |

**Validation**

| **Exception** | Error Message |
| :--- | :--- |
| No user name | Username not entered |
| No password | Password not entered |
| Password or user name is invalid | Invalid username or password |

**Assets**

couch-potato-main.png

![](../../.gitbook/assets/couch-potato-main.png)

