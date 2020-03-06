# Replay

The replay screen is displayed by clicking on the `REPLAY` button on the Dashboard header.

![](../../../.gitbook/assets/screen-shot-2020-03-06-at-11.09.22-am.png)

The purpose of the Replay feature is to give the user a manual way to send, or re-send, game create incidents to all of the BOS endpoints if for any reason they weren't correctly sent before.

Normally this feature shouldn't need to be used very often as a create incident is automatically sent every time a game is created. But there could be occasions when the application correctly records a game as being created but the information is recording by the BOS nodes. If that happened then running a Replay will 'flush' all the games between the start and end dates and send create incidents to the BOS nodes a second time.

{% hint style="danger" %}
**Important**: The Replay feature can only be used for games that are not yet started. Once a game is started a new create incident would be ignored.
{% endhint %}





