---
description: >-
  Eis uma breve descrição das alterações mais importantes introduzidas no Gunbot
  v12.
---

# Novidades na v12

## Lista de Correcções da release v12.9.1

* Correcção do comportamento de não triggering de: `SL_DISABLE_BUY`, `RT_ONCE`, `RT_ONCE_AND_CONTINUE` e `COUNT_SELL`
* Correcção nos montantes das ordens do tipo long no Bitmex, quando utilizando `MARKET_BUY` ou alertas de TradingView.

Se utiliza algumas das funcionalidades mencionadas acima, este é um upgrade recomendado.

Para instalar, basta efectuar o [download](../../setup-and-general-settings/installation/download.md) da versão e sobrepôr o ficheiro executavel gunthy na pasta existente do Gunbot.

## Novas funcionalidades / alterações na v12

* **Suporte para Bitmex:** Gunbot agora suporta trading to tipo leveraged no Bitmex e Bitmex Testnet. A nova função `PRE_ORDER` permite colocar a ordem à frente do livro de ordens para aumentar as chances das ordens limit serem preenchidas. Com `MAKER_FEES` todas as trades podem ser colocadas como tipo post only orders, permitindo ao gunbot agir como Criador de mercado \(Market Maker\)!
* **Estratégias de trading do tipo margin:** Estratégias para bitmex oferecem triggers com opção long, short, stop e close no ROE desejado - ou trail ROE para mais!
* **Verificação de licença via Blockchain**: Utilizando tokens GUNTHY, agora já é possivel ao utilizador gerir as suas APIs de graça. 
* **Melhorias ichimoku:** Tanto a versão regular como margin da estratégia ichimoku estão muito mais poderosas. Pode agora escolher iniciar ou fechar trades utilizando Tenkan-Sen, Kumo ou Kijun-Sen.
* **Ordens do tipo Market:** Opção de utilizar ordens do tipo mercado em vez de ordens do tipo limit, customizável para todo o tipo de ordens. Funciona nos Exchange que suportam ordens do tipo market: Binance, Bitfinex, Bitmex, Coinbase Pro, Kraken e Poloniex.
* **Vista em lista no dashboard do GUI**: Novo tipo de vista de listagem para pares no dashboard: Toda a informação relevante numa rápida overview, que melhora os tempos de carregamento, especialmente para configurações com muitos pares.
* **Melhorias nos Gráficos \(Chart\)** : O GUI pode agora mostrar todos os indicadores suportados pelo Gunbot no Gráfico. Objectivos de trading são agora visualizados no gráfico.
* **Velas Renko:** Pode agora usar as velas Renko em vez das velas do tipo regular \(De momento só funciona para trading do tipo margin com ichimoku\).
* **Remoção de**  `CANCEL_ORDERS_CYCLE_CAP` **excepto quando se utiliza** `MAKER_FEES`: as ordens agora só são canceladas automáticamente se o bid/ask estiverem acima/abaixo do order rate.
* **Reter acesso ao GUI mesmo com erros no arranque**: o Gunbot para automáticamente quando corrido sem pares. Se um erro no arranque ocorrer, uma notificação do Telegram é enviada e o Gunbot fica parado.
* **Tema do tipo Dark para a página de definições**: A página definições no GUI é agora do tipo dark.
* **Renomeação de executáveis**: Os executáveis principais foram renomenados para permitir maior coêrencia entre sistemas operativos.
* **Várias pequenas alterações**

## **Correcções**

Muitos problemas críticos foram corrigidos na release v11. -Many critical issues were already patched in the bugfix releases for v11. Melhoras e correcções mais importantes:

* Correcção duma situação em que algumas alterações feitas no GUI não eram gravadas.
* Correcção para binance do "minPrice" / "maxPrice" reportando 0.
* Melhoria na utilização de PAX & TUSD como base currency.
* Melhoria nas ordens de venda no Binance.
* Correcções no SMACROSS, MACD e MACDH que não possibilitavam trades em condições especificas.
* Correcção no "RSI undefined" callback.
* Garantir que um par é mesmo vendido antes de desabilitar o `COUNT_SELL` .
* Correcção no suporte para TUSD como base currency no Binance.
* Correcção das livrarias para suporte para Raspberry Pi.
* Redução da utilização dos dados/recursos para o GUI.
* Workaround para uma situação onde Bitfinex não aceitava fecho de ordens.
* Correcção duma situação em que era feito o reset ao DU count com uma ordem parcialmente vendida.
* Correcção duma situação com trading do tipo margin através do TV add-on no Huobi.
* Várias pequenas correcções.

## **Actualização**

Efectuar o download do update e descomprimir para uma pasta nova. Copiar os ficheiros `config.js` e `gunbotgui.db` da versão anterior v11 para a nova pasta para manter as suas definições. Na eventualidade de ter utilizado https para aceder ao GUI, garantir que copia os ficheiros, quer do certificado, quer da chave do certificado para a nova pasta. 

Se tem pares que já estejam em estado DU ou RT, copiar também a pasta /json da v11 para a v12.

Os novos parametros de estratégia da v12 serão adicionados automáticamente pelo GUI na primeira vez que actualizar a estratégia. Isto acontece a cada estratégia actualizada.

_Devido à utilização de novas livrarias, não se pode simplesmente copiar por cima o executável para esta versão._

