---
description: 'Aprenda a executar trades com o Gunbot, baseado em alertas enviados por email.'
---

# TradingView

TradingView é a rede social mais activa para investidores e tradeer. Permite aos utilizadores criar e partilhar análises técnicas e estratégias avançadas de trading nos seus gráficos \(charts\) interactivos.

Com o add-on de TradingView para o Gunbot, pode efectuar trading baseado em alertas enviados de estratégias costumizados em TradingView, gerindo apenas a sua estratégia de tradingview. O Gunbot recebe um sinal de trade através de email e executa de acordo com a ordem recebida..

{% hint style="info" %}
Este é um add-on pago e a sua disponibilidade depende do tipo de licença adquirido.
{% endhint %}

## Video de configuração

Antes de iniciar a configuração dos seus alertas, é necessário:

* Os dados de IMAP para o endereço de email pelo qual irá receber os alertas do TradingView.
* Uma subscrição do tipo PRO do TradingView \(funciona com trial também\). Contas gratuitas estão limitadas a apenas um alerta.

{% embed url="https://www.youtube.com/watch?v=H2EybuYxc3Y" caption="Video feito com uma versão mais antiga do Gunbot.Os passos de configuração básica ainda se aplicam." %}



[Script utilizado no exemplo: Finn's Microprofit Strategy](https://gunthy.org/forum/index.php/topic,1548.0.html)

{% page-ref page="imap-listener.md" %}

## Conteúdo das mensagens de alerta

As mensagens de alerta têm que estar no seguinte formato de modo a que o Gunbot possa executar baseado nos alertas. Os alertas seguem o mesmo formato standard da syntax de pares, aplicado também no uso normal do Gunbot.

Limites de trading pode somente ser especificados nos alertas do tipo buy/long. Para outros alertas ou alertas sem montantes especificados, os limites considerados são os definidos no parâmetros do TradingView..

_Substituir_ `EXCHANGE` _com o nome do seu exchange._

\_\_

#### For all spot exchanges

| Alert message | Action |
| :--- | :--- |
| BUY\_EXCHANGE\_BTC-ETH | Buy ETH using BTC |
| BUY\_EXCHANGE\_BTC-ETH\_0.1 | Buy ETH using BTC with a trading limit of 0.1 BTC |
| SELL\_EXCHANGE\_USDT-BTC | Sell BTC for USDT |
| STOPLOSS\_EXCHANGE\_BTC-ETH | Sell ETH for BTC if stoploss is triggered |

#### Alerts for margin trading  on Bitmex and Bitfinex

| Alert message | Action |
| :--- | :--- |
| SHORT\_EXCHANGE\_XBT-USD | Short order for XBT-USD |
| LONG\_EXCHANGE\_XBT-USD | Long order for XBT-USD |
| SHORT\_EXCHANGE\_XBT-USD\_amount | Short order for XBT-USD with a specified trading limit |
| LONG\_EXCHANGE\_XBT-USD\_amount | Long order for XBT-USD with a specified trading limit |
| CLOSELONG\_EXCHANGE\_XBT-USD | Closes a long position for XBT-USD |
| CLOSESHORT\_EXCHANGE\_XBT-USD | Closes a short position for XBT-USD |

{% hint style="info" %}
**Note about trading limits on Bitmex and Bitfinex**

On Bitmex, every setting related to trading limits for margin trading must be specified in contracts.

On Bitfinex, every setting related to margin trading limits must be specified in amounts of quote currency.
{% endhint %}

#### Alerts for margin trading at Kraken, Poloniex and Huobi.

| Alert message | Action |
| :--- | :--- |
| SHORT\_EXCHANGE\_BTC-ETH | Short order for BTC-ETH |
| LONG\_EXCHANGE\_BTC-ETH | Long order for BTC-ETH |
| LONG\_EXCHANGE\_BTC-ETH\_0.1 | Long order for BTC-ETH with a trading limit of 0.1 BTC |
| CLOSE\_EXCHANGE\_BTC-ETH | Close an open margin position for BTC-ETH |

## TradingView settings

To run Gunbot with the TradingView add-on, the following are the only relevant settings. Normal Gunbot strategy and pair settings are not relevant and not used unless `TV_GB` is enabled.

Open the settings by going to **Settings** &gt; **TradingView.**

![Settings options for the TradingView add-on](../../.gitbook/assets/image-40.png)

Trading limits for buy orders are set in the configuration settings, optionally you can override these by specifying the trading limit in the alert message contents.

Orders placed by the TradingView add-on are placed as market orders to ensure they will get filled.

{% hint style="info" %}
Be sure to add one pair for any exchange you want to execute alerts on.

This can be any pair, it will not be used by the add-on.
{% endhint %}

### Gain

{% tabs %}
{% tab title="Description" %}
Set a minimum gain in % that trades initiated by TradingView must comply to when `TV_PROTECTION` is enabled.

When TradingView sell alerts are sent that would have a lower gain than this value, Gunbot will not place the order. Use this to prevent selling at loss.

{% hint style="warning" %}
**Only works for spot trading.**
{% endhint %}
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represents a percentage.

**Default value:** 0.6
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TV_GAIN`
{% endtab %}
{% endtabs %}

### Trading Limit Buy

{% tabs %}
{% tab title="Description" %}
This value defines the trading limit for each buy order placed through the add-on.

The default value of 0.002 would place orders of 0.002 BTC when used on a BTC-x pair.

When not using `TV_PYRAMID`, a sell alert will place a sell order for the full quote balance held.

{% hint style="info" %}
**Bitmex**: enter the desired number of contracts

**Bitfinex margin:** enter an amount in quote currency
{% endhint %}
{% endtab %}

{% tab title="Values" %}
**Values:** numerical – represents an amount in base currency.

**Default value:** 0.002
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TV_TRADING_LIMIT_BUY`
{% endtab %}
{% endtabs %}

### Trading Limit Buy Pyramid

{% tabs %}
{% tab title="Description" %}
This value defines the trading limit for each pyramid buy order placed through the add-on.

The default value of 0.002 would place orders of 0.002 BTC when used on a BTC-x pair.

{% hint style="info" %}
**Bitmex**: enter the desired number of contracts

**Bitfinex margin:** enter an amount in quote currency
{% endhint %}
{% endtab %}

{% tab title="Values" %}
**Values:** numerical – represents an amount in base currency.

**Default value:** 0.002
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TV_TRADING_LIMIT_BUY_PYRAMID`
{% endtab %}
{% endtabs %}

### Pyramid

{% tabs %}
{% tab title="Description" %}
Setting this to true enables pyramid trading, the amount for each pyramid order is defined by `TV_TRADING_LIMIT_SELL` or `TV_TRADING_LIMIT_BUY_PYRAMID`.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** false
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TV_PYRAMID`
{% endtab %}
{% endtabs %}

### Trading Limit Sell

{% tabs %}
{% tab title="Description" %}
This value defines the trading limit for sell orders when `TV_PYRAMID` is enabled.

The default value of 0.002 would place orders of 0.002 BTC when used on a BTC-x pair.

{% hint style="info" %}
**Bitmex**: enter the desired number of contracts

**Bitfinex margin:** enter an amount in quote currency
{% endhint %}
{% endtab %}

{% tab title="Values" %}
**Values:** numerical – represents an amount in base currency.

**Default value:** 0.002
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TV_TRADING_LIMIT_SELL`
{% endtab %}
{% endtabs %}

### Protection

{% tabs %}
{% tab title="Description" %}
When set to true Gunbot will check if there is an overall profit before selling, as specified in `TV_GAIN`.

When set to false, Gunbot will execute all TradingView alerts without interfering with a custom strategy.

{% hint style="warning" %}
**Only works for spot trading.**
{% endhint %}
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** false
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TV_PROTECTION`
{% endtab %}
{% endtabs %}

### Trading Limit Cap

{% tabs %}
{% tab title="Description" %}
The maximum amount of base currency to be invested in a pair.

{% hint style="warning" %}
**Only works for spot trading.**
{% endhint %}
{% endtab %}

{% tab title="Values" %}
**Values:** numerical – represents an amount in base currency.

**Default value:** 0.0001
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TV_TRADING_LIMIT_CAP`
{% endtab %}
{% endtabs %}

### Stoploss Percentage

{% tabs %}
{% tab title="Description" %}
Percentage below average bought price at which a sell signal should override `TV_PROTECTION` and sell in a stop-loss manner.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical – represents a percentage.

**Default value:** 60
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TV_STOPLOSS_PERCENTAGE`
{% endtab %}
{% endtabs %}

### Trading Limit All-In

{% tabs %}
{% tab title="Description" %}
When set to true, each buy order will use all available base currency balance.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** false
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TV_TRADING_LIMIT_ALLIN`
{% endtab %}
{% endtabs %}

### Retry Order

{% tabs %}
{% tab title="Description" %}
Enable this when you have problems receiving multiple alerts.

Gunbot will retry processing orders for 15 minutes.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** false
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `RETRY_TV_ORDER`
{% endtab %}
{% endtabs %}

### TV MVTS

{% tabs %}
{% tab title="Description" %}
Sets a threshold for sell orders, If you own less than the set amount, sell orders will not be placed and the bot goes into buying mode again.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical – represents the total value of a coins holdings in base currency.

**Default value:** 0.001
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TV_MVTS`
{% endtab %}
{% endtabs %}

### TV GB

{% tabs %}
{% tab title="Description" %}
Enable this to run Gunbot strategies simultaneously with the TradingView add-on. This way buying and selling with Gunbot strategies or TradingView alerts can be mixed.

The IMAP listener needs to be enabled to use this option.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** false
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TV_GB`
{% endtab %}
{% endtabs %}

### TV Leverage

{% tabs %}
{% tab title="Description" %}
For margin trading only. Sets the leverage for opening any position. Setting 0 places the order with cross margin, if your exchange supports cross leverage.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical – between 0 and 100

**Default value:** 0
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TV_LEVERAGE`
{% endtab %}
{% endtabs %}

