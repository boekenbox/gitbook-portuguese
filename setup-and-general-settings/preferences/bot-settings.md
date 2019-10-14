---
description: Informação acerca de parâmetros globais do Bot.
---

# Parâmetros Bot

O menu de parâmetros do Bot permite-lhe alterar definições globais que afectam todos os pares de trading.

Para alterar basta ir a **Settings** &gt; **Bot Settings**.

![Defini&#xE7;&#xF5;es globais do Bot](../../.gitbook/assets/image-46.png)

## Descrição dos parâmetros

Abaixo irá encontrar descrições detalhados dos parâmetros disponiveis para o menu bot. Alguns parâmetros avançados apenas estão disponíveis através do ficheiro `config.js` .

### Watch Mode

{% tabs %}
{% tab title="Descrição" %}
Quando habilitado para true, o Gunbot irá processar os pares configurados  mas não colocará nenhuma ordem real, quer de compra, quer de venda. Bom para testes.
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `WATCH_MODE`
{% endtab %}
{% endtabs %}

### Multiple Base

{% tabs %}
{% tab title="Descrição" %}
Usar esta opção para fazer trade com pares que tenham cruzamento entre quote e base \(por exemplo BTC-ETH e ETH-ADA\).

Quanto activo, o gunbot não irá vender todas as unidades de quote disponiveis. Em vez disso, irá apenas vender o que foi investido \(como definido no limite de trade - trading limit\). Afecta o add-on do TradingView.

Activar apenas quando fôr mesmo necessário.
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `MULTIPLE_BASE`
{% endtab %}
{% endtabs %}

### Debug

{% tabs %}
{% tab title="Descrição" %}
Utilizado para visualizar mensagens de depuração/erro no bot, quando definido como true. Utilizar apenas se necessário para verificar alguma situação.
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `debug`
{% endtab %}
{% endtabs %}

### Verbose

{% tabs %}
{% tab title="Descrição" %}
Activando este parâmetro para true, fornecerá informação mais detalhada na consola.
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `VERBOSE`
{% endtab %}
{% endtabs %}

### Reserve Pile Up

{% tabs %}
{% tab title="Descrição" %}
Activando este parâmetro para true, os ganhos de trading, serão automáticamente adicionados ao fundo de reserva e não serão utilizados em mais trading
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `RESERVE_PILE_UP`
{% endtab %}
{% endtabs %}

### Bot Delay

{% tabs %}
{% tab title="Descrição" %}
O bot atrasará o processamento de um novo par pelo valor definido, em segundos.

Útil para quando o Gunbot requisita dados mais rápido do que a API do Exchange permite. Como o valor de atraso necessário depende do número de pares e a velocidade do sistema, não existe um valor recomendado

Esta é uma definição global para o atraso do bot. É ignorado quando existe um atraso definido especificamente nas definições do exchange.
{% endtab %}

{% tab title="Valores" %}
**Valores:** numérico – representa tempo em segundos.

**Valor por defeito:** 1
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `BOT_DELAY`
{% endtab %}
{% endtabs %}

### Bot CClean

{% tabs %}
{% tab title="Descrição" %}
Este parâmetro força a limpeza da cache do Gunbot, obrigando o re-inicio do bot a cada x horas. Este parâmetro não influencia o trigger de `TRADES_TIMEOUT`.

Apenas definir este parâmetro para um valor baixo quando o bot tem problemas reais e não efectua trading após um longo período de uso.
{% endtab %}

{% tab title="Valores" %}
**Valores:** numérico – representa tempo em horas.

**Valor por defeito:** 2
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `BOT_CCLEAN`
{% endtab %}
{% endtabs %}

### Interval Ticker Update

{% tabs %}
{% tab title="Descrição" %}
Descontinuado
{% endtab %}

{% tab title="Valores" %}

{% endtab %}

{% tab title="Nome" %}

{% endtab %}
{% endtabs %}

### Period Storage Ticker

{% tabs %}
{% tab title="Descrição" %}
Descontinuado
{% endtab %}

{% tab title="Valores" %}

{% endtab %}

{% tab title="Nome" %}

{% endtab %}
{% endtabs %}

### Timeout Buy

{% tabs %}
{% tab title="Descrição" %}
Este é um timeout interno que previne que o bot compre outra vez, no espaço definido em milisegundos, após uma ordem de compra ter sido colocada.
{% endtab %}

{% tab title="Valores" %}
**Valores:** numérico – representa tempo em milisegundos.

**Valor por defeito:** 59000
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `timeout_buy`
{% endtab %}
{% endtabs %}

### Timeout Sell

{% tabs %}
{% tab title="Descrição" %}
Este é um timeout interno que previne que o bot venda outra vez, no espaço definido em milisegundos, após uma ordem de venda ter sido colocada.
{% endtab %}

{% tab title="Valores" %}
**Valores:** numérico – representa tempo em milisegundos.

**Valor por defeito:** 60000
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `timeout_sell`
{% endtab %}
{% endtabs %}

### Cancel Orders Enabled

{% tabs %}
{% tab title="Descrição" %}
Quando definido como true, o bot cancela ordens não preenchidas ou parcialmente preenchidas quando o preço se afastar do valor de compra ou venda.

Definir como false se também efectuar trades manuais, para impedir que o bot cancele as suas ordens manuais em aberto.

**Simulated Fill Or Kill \(FOK\)**

Quando uma ordem não é completada ou é parcialmente preenchida, e é cancelada, o Gunbot tentará preencher essa ordem, actualizando o valor para o actual bid/ask.

Para ordens de compra isto significa que, ordens FOK são enviadas como tipo long por enquanto o número de unidades seguradas valerem menos que o `TRADING_LIMIT` e a diferença for maior que o `MIN_VOLUME_TO_BUY`.

Para ordens de venda isto que significa que, ordens FOK são enviadas como tipo long por enquanto o número de unidades seguradas \(menos `KEEP_QUOTE`, se utilizado\) valerem mais que  `MIN_VOLUME_TO_SELL` e o preço \(bid\) for maior que o ponto de break-even.
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `CANCEL_ORDERS_ENABLED`
{% endtab %}
{% endtabs %}

### Cancel Orders Cycle Cap

{% tabs %}
{% tab title="Descrição" %}
Apenas se aplica quando se utiliza `MAKER_FEES` ou `CANCEL_ONCAP`.

Define o número de ciclos que as ordens pendentes podem estar em aberto. Após este número definido de ciclos passar, o Gunbot cancela a ordem pendente..
{% endtab %}

{% tab title="Valores" %}
**Valores:** numérico - representa o número de ciclos.

**Valor por defeito:** 10
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `CANCEL_ORDERS_CYCLE_CAP`
{% endtab %}
{% endtabs %}

### Cancel Orders Oncap

{% tabs %}
{% tab title="Descrição" %}
Activando este parâmetro, altera o comportamento do cancelamento de ordens: as ordens são imediatamente canceladas após a passagem do valor definido em  `CANCEL_ORDERS_CYCLE_CAP` .
{% endtab %}

{% tab title="Valores" %}
**Valores:** true ou false

**Valor por defeito:** false
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `CANCEL_ONCAP`
{% endtab %}
{% endtabs %}

### Withdraw Threshold

{% tabs %}
{% tab title="Descrição" %}
Define o montante de BTC a ser acumulado com `RESERVE_PILE_UP` antes de um levantamento automático ser executado.
{% endtab %}

{% tab title="Valores" %}
**Valores:** numérico - representa uma montante em BTC

**Valor por defeito:** 0.5
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `withdraw_threshold`
{% endtab %}
{% endtabs %}

### Withdraw Address

{% tabs %}
{% tab title="Descrição" %}
Define um endereço de BTC wallet que permita o levantamento automático quando o limite definido é atingido \(threshold\).

Por favor, use esta funcionalidade à sua responsabilidade.
{% endtab %}

{% tab title="Valores" %}
**Valor:** string

**Valor por defeito:** YOURBTCADDRESSHERE
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `withdraw_address`
{% endtab %}
{% endtabs %}

### Json\_output

{% tabs %}
{% tab title="Descrição" %}
Define o caminho para guardar os ficheiros .json.  Estes ficheiros são onde o Gunbot guardar a informação de trading.
{% endtab %}

{% tab title="Valores" %}
**Valores:** texto, representa uma localização de pasta.

**Valor por defei**_**to:** ./json_
{% endtab %}

{% tab title="Nome" %}
Nome do parâmetro em `config.js`: `json_output`
{% endtab %}
{% endtabs %}

