---
description: Instruções para executar múltiplas instâncias de Gunbot na mesma máquina.
---

# Executar múltiplas instâncias

Para executar multiplas instâncias de Gunbot, basta criar um cópia da pasta do Gunbot para cada instância e garantir que os seguintes parâmetros são únicos para cada instância:

* `port` - Tanto no GUI como na secção ws
* `clientport` - na secção ws 
* `TOKEN` na secção bot  \(Este é o token para as notificações de Telegram\)

O GUI de cada instância estará disponível no localhost através da número especificado em `port`

{% hint style="info" %}
Utilize um editor como o Notepad++ para editar o ficheiro `config.js` para criar as alterações descritas acima.
{% endhint %}

