---
description: 'Definições de porta de Websocket, só necessário para programadores (devs).'
---

# Websockets

O Gunbot fornece certa data através dos websockets. Documentação limitada para esta funcionalidade está disponível no seguinte repositório: [https://github.com/GuntharDeNiro/Gunthy/\#webgui-informations-for-devs-](https://github.com/GuntharDeNiro/Gunthy/#webgui-informations-for-devs-)

Para alterar os parâmetros de websockets ir a **Settings** &gt; **Websocket**.

![](../../.gitbook/assets/image-37.png)

## Descrição de parâmetros

Abaixo encontrará descrições detalhadas dos parâmetros disponíveis para websockets.

### Port \(WS\)

{% tabs %}
{% tab title="Descrição" %}
Define a porta utilizada para websockets.
{% endtab %}

{% tab title="Valores" %}
**Valores:** numérico - representa o número da porta.

**Valor por defeito:** 5001
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `port`
{% endtab %}
{% endtabs %}

### Client Port

{% tabs %}
{% tab title="Descrição" %}
Pode alterar a porta de cliente para interfaces web de terceiros.
{% endtab %}

{% tab title="Valores" %}
**Valores:** numérico - representa o número da porta.

**Valor por defeito:** 3000
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `clientport`
{% endtab %}
{% endtabs %}

### Hostname

{% tabs %}
{% tab title="Descrição" %}
O Endereço de IP ou nome da máquina \(hostname\) utilizado para websockets. Por defeito é "localhost". Pode ser definido também um IP externo.
{% endtab %}

{% tab title="Valores" %}
**Valores:** texto, representa um endereço ip ou hostname

**Valor por defeito:** 127.0.0.1
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `hostname`
{% endtab %}
{% endtabs %}

