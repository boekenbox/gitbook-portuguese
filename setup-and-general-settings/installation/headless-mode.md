---
description: Informação como executar o Gunbot em modo Headless.
---

# Modo Headless

{% hint style="info" %}
Este artigo é destinado a Power users que querem executar o Gunbot sem utilizar o GUI.

Esta não é uma overview exaustiva de todos os parâmetros disponíveis, mas sim uma rápida overview sobre como trabalhar manualmente com o ficheiro de configuração. Para detalhes e descrições detalhadas sobre os parâmetros, consulte outras áreas deste Wiki.
{% endhint %}

## Ficheiro de configuração do sistema

Todos os parâmetros do Gunbot estão definidos num único ficheiro chamado `config.js`. Aqui é onde se configura as suas chaves de API, adição de pares e definição das suas estratégias, entre outros.

Pode consultar o ficheiro  `config-js-example.txt` para ter um exemplo duma configuração com pares definidos correctamente e todos os parâmetros necessários para adicionar um exchange. Ao longo deste Wiki encontrará descrições detalhadas para cada parâmetro disponível no ficheiro de configuração.

Quando o ficheiro de configuração é copiado por cima \(ao salvar por exemplo\) quando o Gunbot está a correr, as alterações serão carregadas automáticamente.

Garanta que nenhum parâmetro é removido quando está a configurar o ficheiro. Garanta também que o formato JSON permanece intácto. Se tem dúvidas sobre o seu ficheiro de configuração, pode validá-lo em [https://jsonlint.com](https://jsonlint.com) \(ou num validador JSON do seu agrado\).

As única acções que são necessárias utilizando o GUI são:

* Actualização de master keys
* Actualização do endereço da GUNTHY wallet 
* Transferência da licença de software para terceiros

## Desactivando o GUI

Para desactivar o GUI completamente, faça a alteração na secção GUI de `config.js`:

```text
"GUI": {
        "enabled": false,
```

## Adicionar exchanges

Para adicionar um exchange, adicionar os parâmetros necessários na secção exchange de`config.js`.

Como exemplo:

```text
"binance": {
            "masterkey": "registered_api_key",
            "mastersecret": "secret_for_registered_api_key",
            "key": "trading_api_key",
            "secret": "secret_for_trading_api_key",
            "delay": 1,
            "type": "binance"
        },
```

De notar que pode usar uma chave de API diferente para trading daquela que se encontra registada.   
Se não usa uma chave secundária, basta introduzir a chave resgistada no parâmetro `key` .

## Estratégias

Uma estratégia é definida através de um nome único e adicionada na secção `strategies` do ficheiro de configurações. Esta estratégia pode ser atribuída a um ou mais pares.

Como exemplo:

```text
"custom-strategy": {
            "BUY_METHOD": "tssl",
            "BUY_ENABLED": true,
            "SELL_METHOD": "tssl",
            "SELL_ENABLED": true,
            "BUY_LEVEL": 1,
            "GAIN": 0.5,

(many lines cut out to keep this page clean)

            "SL_DISABLE_BUY": false,
            "COUNT_SELL": 9999,
            "TRADES_TIMEOUT": 0
        },
```

## Definição de pares e substituições \(overrides\)

Na secção `pairs` do ficheiro de configuração, pode adicionar um ou mais pares dentro dum bloco, especificando o exchange onde os pares vão correr.

A cada par terá que ter atribuída uma estratégia já existente e terá que ser especificado se o par esta activo ou não.

Como exemplo:

```text
"Binance": {
            "BTC-LTC": {
                "strategy": "SMACROSS",
                "enabled": true,
                "override": {
                    "TRADING_LIMIT": 1000
                }
            }
        },
```

A secção de overrides permite modificações especificas para cada par, sobre a estratégia atribuída. Qualquer parâmetro de estratégia pode ser utilizado como override.

No exemplo acima, o par irá utilizar a estratégia SMACROSS, com um limite de trade \(`TRADING_LIMIT`\) diferente do que está definido na estratégia em si.

