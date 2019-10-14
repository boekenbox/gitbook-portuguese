---
description: >-
  O Gunbot incluí um robô do Telegram que pode ser utilizado para receber
  notificações de trade, estatisticas e controlar algumas opções do Gunbot,
  através do cliente do Telegram.
---

# Telegram notifications

{% hint style="info" %}
O robô do Telegram \(anteriormente conhecido como CryptoSight\) está completamente integrado com o Gunbot. Tudo o que necessita de fazer é iniciar o robô do Telegram e activar as notificações de Telegram nas definições do Gunbot.
{% endhint %}

{% hint style="info" %}
Depois da configuração, escrever`/start` no seu robô para abrir o menu.
{% endhint %}

## Video de demonstração

{% embed url="https://www.youtube.com/watch?v=11fHq22nNFo" caption="" %}

## Iniciar

Para configurar, ir a **Settings** &gt; **Telegram**.

![Op&#xE7;&#xF5;es dos par&#xE2;metros para o rob&#xF4; do Telegram](../../.gitbook/assets/image-34.png)

## Passos para criar um robô do Telegram

As notificações funcionam criando primeiro um robô pessoal do Telegram. O Gunbot liga-se a este robô para enviar as notificações para si.

Os passos para criar o robô são os seguintes:

1. Falar com [@botfather](https://telegram.me/botfather). Criar um novo robô com o comando /newbot e escolher nome e username para o robô. Guardar o token mostrado.
2. Falar com [@myidbot](https://telegram.me/myidbot) para visualizar o Chat ID. Guarde-o.
3. Activar as notificações do Telegram no Gunbot e, introduzir o token e o ID que foram gerados. Utilize o ID para ambos os campos user e admin ID. Desta forma garante que apenas você pode interagir com o robô do Telegram. _Em alternativa, pode definir uma lista separada por vírgulas para o campo Admin ID, especificando múltiplos ID que podem interagir com o robô._
4. Iniciar um chat com o username que escolheu para o robô e clickar no botão de start. Se não visualizar um botão de start, escrever "/start" e clickar no botão que irá surgir.

## Descrições dos parâmetros

Abaixo as descrições detalhadas de todos os parâmetros disponiveis para as notificações do Telegram.

### Enabled

{% tabs %}
{% tab title="Descrição" %}
Activar este parâmetro para que o gunbot envie notificações de trade através do Telegram.
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `TELEGRAM_ENABLED`
{% endtab %}
{% endtabs %}

### Bot Nickname

{% tabs %}
{% tab title="Descrição" %}
Cada notificação de trade começa com o nome definido neste parâmetro.

Utilizar para facilmente se identificar qual a instação do robô que enviou as notificações.
{% endtab %}

{% tab title="Valores" %}
**Valores:** texto

**Valor por defeito:** Gunbot
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `TELEGRAM_NICK`
{% endtab %}
{% endtabs %}

### Token

{% tabs %}
{% tab title="Descrição" %}
O token de Telegram do robô.
{% endtab %}

{% tab title="Valores" %}
**Valores:** texto

**Valor por defeito:** YOURTOKEN
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `TOKEN`
{% endtab %}
{% endtabs %}

### Chat ID

{% tabs %}
{% tab title="Descrição" %}
O Chat ID do robô para o qual o Gunbot envia as mensagens.

**Opções válidas:**

_**"12345"**_

Um número positivo, para enviar mensagens directamente a utilizador de Telegram. Utilizar este método quando apenas quer receber notificações para uso pessoal.

Para descobrir o seu Telegram ID, enviar "/start" para @MyTelegramID\_bot que este responderá com o seu ID.

_**"-12345"**_

Um número negativo, para enviar mensagens para um chat de grupo.

A maneira mais fácil para obter o ID do grupo é abrindo o [https://web.telegram.org](https://web.telegram.org) , efectuar o login e navegar para o grupo. Olhando com atenção ao URL \(endereço\), verá algo do tipo [https://web.telegram.org/\#/im?p=g12345](https://web.telegram.org/#/im?p=g12345) - o número após o "p=" é o ID do grupo.

Terá que ser listado com um id com o símbolo "-" antes do número, neste caso "-12345"
{% endtab %}

{% tab title="Valores" %}
**Valores:** texto

**Valor por defeito:** 123456789
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `chat_id`
{% endtab %}
{% endtabs %}

### Admin ID

{% tabs %}
{% tab title="Descrição" %}
Define quais os IDs de utilizadores que são permitidos interagir com o robô. Devem ser usados a seguir ao Chat ID.

Quando este campo é deixado vazio, todos os utilizadores do Telegram conseguem interagir com o seu robô de Telegram.

Múltiplos IDs podem ser introduzidos, separados por vírgula.
{% endtab %}

{% tab title="Valores" %}
**Valores:** texto

**Valor por defeito:** vazio
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `admin_id`
{% endtab %}
{% endtabs %}

### TG PL Only

{% tabs %}
{% tab title="Descrição" %}
Quando activado, apenas as notificações de ordens de venda da estratégia serão enviadas.
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `TG_PL_ONLY`
{% endtab %}
{% endtabs %}

### Telegram Order Timeout

{% tabs %}
{% tab title="Descrição" %}
Quando definido acima de 0, receberá um diálogo do Telegram para manualmente permitir ou negar cada ordem que o Gunbot irá colocar.

Durante o número definido de segundos, poderá escolher permitir a ordem \(que será imediatamente colocada\). 

Após o tempo definido em timeout expirar sem resposta, a ordem será colocada no exchange.
{% endtab %}

{% tab title="Valores" %}
**Valores:** númerico, representa tempo em segundos.

**Valor por defeito:** 0
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `TG_ORDER_TIMEOUT`
{% endtab %}
{% endtabs %}

### TG Test

{% tabs %}
{% tab title="Descrição" %}
Activar este parâmetro para testar se o robô de Telegram está a funcionar correctamente.

Uma mensagem de teste será enviada no primeiro ciclo para cada par processado. Desactivar após verificar o bom funcionamento do seu robô.

{% hint style="info" %}
Esta opção encontra-se temporáriamente indisponivel. Será novamente activada num próximo update do Gunbot.
{% endhint %}
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `TG_TEST`
{% endtab %}
{% endtabs %}

