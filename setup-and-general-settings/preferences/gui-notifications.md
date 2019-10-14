---
description: Opções para notificações no interface do Browser.
---

# Notificações do GUI

## Parâmetros do GUI

O menu GUI Notifications permite alterar quais as notificações que são visíveis.

Para alterar, ir a **Settings** &gt; **GUI Notifications**.

![](../../.gitbook/assets/image-10.png)

## Descrição dos parâmetros

Abaixo irá encontrar descrições detalhados dos parâmetros disponiveis para o menu bot. Alguns parâmetros avançados apenas estão disponíveis através do ficheiro `config.js` .

### Mensagens de Callback

{% tabs %}
{% tab title="Descrição" %}
Definir como true para receber notificações callback no GUI.
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `callback`
{% endtab %}
{% endtabs %}

### Mensagens de Erro

{% tabs %}
{% tab title="Descrição" %}
Definir como true para receber notificações de erro no GUI.
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `error`
{% endtab %}
{% endtabs %}

### Messagens de Trade

{% tabs %}
{% tab title="Descrição" %}
Definir como true para receber notificações de trades no GUI.
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `trade`
{% endtab %}
{% endtabs %}

### Activo \(GUI\)

{% tabs %}
{% tab title="Descrição" %}
Definir como false para desactivar o GUI.
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `enabled`
{% endtab %}
{% endtabs %}

### Start

{% tabs %}
{% tab title="Descrição" %}
Quando definido como false, o Gunbot inicia o GUI \(Se activado\) mas não inicia o processamento de pares \(ciclos\) até o core ser iniciado através do GUI.

Só é activado após clickarem no botão "**START BOT CORE**" no GUI.

Caso não utilize o GUI, definir este parâmetro como true.
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nomes" %}
Nome do parâmetro em `config.js`: `start`
{% endtab %}
{% endtabs %}

### Port \(GUI\)

{% tabs %}
{% tab title="Descrição" %}
O número da porta do GUI.
{% endtab %}

{% tab title="Valores" %}
**Valores:** numérico - representa o número da porta.

**Valor por defeito:** 5000
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `port`
{% endtab %}
{% endtabs %}

### Https

{% tabs %}
{% tab title="Descrição" %}
Definir como true para correr o GUI somente via https.  
  
Requer uma chave privada e um certificado na pasta do Gunbot.
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `https`
{% endtab %}
{% endtabs %}

### Key

{% tabs %}
{% tab title="Descrição" %}
Define o nome do ficheiro da chave privada utilizada para correr o GUI via https.
{% endtab %}

{% tab title="Valores" %}
**Valores:** texto, representa um ficheiro.

**Valor por defeito**_**:**_ localhost.key
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `key`
{% endtab %}
{% endtabs %}

### Cert

{% tabs %}
{% tab title="Descrição" %}
Define o nome do ficheiro do certificado / chave pública utilizado para correr o GUI via https.
{% endtab %}

{% tab title="Valores" %}
**Valores:** texto, representa um ficheiro.

**Valor por defeito:** __localhost.cert
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `cert`
{% endtab %}
{% endtabs %}

### Networktraffic

{% tabs %}
{% tab title="Descrição" %}
Definir como true para visualizar no GUI pedidos de tráfego de rede dos logs do Gunbot.

Útil em caso de debug \(verificações ou erros\).
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `networktraffic`
{% endtab %}
{% endtabs %}

### Login

{% tabs %}
{% tab title="Descrição" %}
Definir como true para activar a autenticação com password. A password é definida no GUI.

Caso necessite de efectuar reset à password, definir como false.
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `login`
{% endtab %}
{% endtabs %}

### TwoFA

{% tabs %}
{% tab title="Descrição" %}
Definir como true para activar a autenticação com 2 factores \(2FA\). Este setup é feito no GUI.  
  
Caso necessite de efectuar reset ao 2FA, definir como false.
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `twoFA`
{% endtab %}
{% endtabs %}

