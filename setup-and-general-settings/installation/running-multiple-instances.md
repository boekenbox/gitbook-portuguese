# Rodando múltiplas instâncias

To run multiple instances of Gunbot, just make a copy of its folder for each instance and make sure the following settings parameters are unique for each instance:

* `port` - both in the GUI and ws section
* `clientport` - in the ws section
* `TOKEN` in the bot section

The GUI of each instance will be available on localhost through the specified port number.

{% hint style="info" %}
Use a text editor like Notepad++ to edit the `config.js` file to make the required changes described above.
{% endhint %}

