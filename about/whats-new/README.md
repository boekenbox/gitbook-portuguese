---
description: >-
  Eis uma breve descrição das novidades mais importantes introduzidas com o
  Gunbot v13.
---

# Novidades na v13

Gunbot v13 foca-se na melhoria da experiência de utilizador e na correcção de erros \(bugfixes\).   
Por isso desta vez, não existe uma lista longa de novas funcionalidades mas sim uma lista longa de melhoramentos. 

## **Actualização \(Upgrading\)**

[Efectuar o Download](../../setup-and-general-settings/installation/download.md) da actualização e descompactar para uma pasta nova. Copiar os ficheiros `config.js` e `gunbotgui.db`da sua pasta da versão anterior v12 para a nova pasta para manter as suas definições.

* Esvaziar a cache do seu browser para aceder ao GUI do Gunbot \(Com CTRL+F5 por exemplo\).
* Na eventualidade de ter utilizado https para aceder ao GUI, garantir que copia os ficheiros, quer do certificado, quer da chave do certificado para a nova pasta.
* Se tem pares que já estejam em estado DU ou RT, copiar também a pasta /json da v12 para a v13.
* Os novos parametros de estratégia da v13 serão adicionados automáticamente pelo GUI na primeira vez que actualizar a estratégia. Isto acontece a cada estratégia actualizada.
* Garanta que define o novo Admin ID to Telegram, para melhorar a privacidade.
* Quando utilizar alertas de email, garantir que[ a syntax dos seus alertas](../../setup-and-general-settings/preferences/tradingview-add-on.md#alert-message-contents) está correcta
* Se quiser migrar as suas definições do Robot do Telegram, copie o ficheiro `tgconfig.json` para a sua nova pasta também.

_Devido à utilização de novas livrarias, não se pode simplesmente copiar por cima o executável para esta versão._

\*\*\*\*

## Novas funcionalidades / alterações na v13

* **Novos Exchanges: Gunbot** suporta agora trading no Idax e Cobinhood. De notar que Cobinhood utiliza somente chave de API, sem segredo - por uma questão de segurança adicional, utilizar uma restrição de IP para a chave de API.
* **Restrição de compra com `SMACROSS`** : Já é possível restringir `SMACROSS`para colocar somente uma ordem de compra, em vez de comprar em cada cruzamento para cima \(cross up\). Basta definir `SINGLE_BUY`como verdadeiro, para permitir apenas uma ordem de compra
* **Melhoria de privacidade para Cryptosight :** Restringir a quem é permitido visualizar e interagir com o seu robô de Telegram. Utilize a definição `admin_id`para especificar um ou mais IDs de utilizadores que são permitidos com o seu robô de Telegram.
* **Melhoria da Base de GUI:** Optimizado para utilização com Telemóvel/Celular, com diferentes esquemas de cores e suporte para costumização de cores de alto contraste.
* **Alterações ao "margin trading" no Bitfinex \(TV add-on\):** Todos os montantes devem ser agora especificados em quote.
* **Diferente syntax nos alertas para "closing positions" no Bitmex \(TV add-on\):** "longs" são agora fechados com CLOSELONG\_, "shorts" com CLOSESHORT\_ ao invês de CLOSE\_ para ambos. 
* **Novo caminho para ficheiros de logs:** Cada par e seus logs são agora guardados na pasta /gunbot\_logs.

\*\*\*\*

{% hint style="warning" %}
**Aviso para utilizadores Bitmex**

É fortemente aconselhado utilizar a partir de agora `STOP_BUY` e `STOP_SELL`em vez de`STOP_LIMIT.`

Desabilite`STOP_LIMIT` definindo o valor para 99999, para prevenir triggers acidentais.
{% endhint %}



## **Gunbot e correcções de erros**

Correcções principais:

* Melhor suporte nas novas moedas no Kraken. Qualquer moeda \(shitcoin\) que será listada, Gunbot estará pronto sem precisar de actualização
* Correcção na listagem de ordens revertida no Bittrex e Huobi
* Correcção numa situação que causava multiplas compras no Binance
* Correcção numa situação que calculava mal o mapa de valores de trades no Binance
* Melhoria na retro compatibilidade dos cálculos de ABP \(Preço médio de compra\)
* Correcção no ABP no Huobi
* Correcção do erro "lowerCase of undefined"
* Melhoria no comporamento SMACROSS
* Cancelamento de todas as ordens de Stop se o ROE é alcançado, no Bitmex
* Várias correcções para ordens manuais feitas através do GUI
* Correcção das ordens de stop compra/venda no bitmex, para ordens de market ou limit
* Correcção no STOP\_LIMIT que por vezes não funcionava no kraken
* Correcção nas ordens de stop que despolevata "waiting for open orders"
* Correcção TI\_ALLIN para ordens do tipo long no Bitmex
* Correcção no display de MACD-H na estratégia do tipo custom 
* Correcção no erro "toLowerCase"
* Fundos Disponíveis agora são apenas usados após um RT\_SELL
* Correcção no FUNDS\_RESERVE que não era respeitado
* Correcção do problema clientid no KuCoin 
* Se uma compra é cancelada, colocar no estado false o "Double Buy Protection"
* Correcção de um erro que por vezes causava cancelamento de ordens demasiado cedo
* Melhoria no triggering das ordens do DU
* Correçcão no triggering RT\_SELL e RT\_BUY
* Correcção do "just bought"
* Correcção da precisão de preço no Coinbase Pro

## TradingView add-on correcção de erros

* Correcção nos montantes das ordens LONG do TV plugin
* Correcção nas ordens TV Buy, no Bittrex
* Correcção da situação que impossibilitava algumas ordens de compra no Bitfinex utilizando o TV plugin
* Correcção de CLOSELONG e CLOSESHORT no Bitfinex. Todos os montantes para Bitfinex margin são agora definidos em quote.
* Melhor respeito dos montantes de ordens em alertas LONG e SHORT, no Bitfinex
* Correcção de erros ocasionais para LONG, SHORT, CLOSELONG e CLOSESHORT, no Bitmex

## Alterações no GUI

Correcções Principais e alterações ao GUI:

* Novo estilo e botões de dropdown com pesquisa
* Adição de Escolha de Cor do tema no GUI
* Correcção da barra de navegação na tab activa
* Correcção dos balões de sugestão \(tooltips\) de imap
* Adição de temas para mobile
* Adição de Painel de notificação para mobile
* Actualização de jquery cdn
* Grandes alterações e melhorias gráficas
* Melhoria do layout em mobile
* Redesenho da página de login
* Actualização de todas as secções de definições
* Melhoria nos textos de tooltips
* Esconder/Desabilitar de ROE\_CLOSE para estratégias que não utilizam esta função



## Alterações no Telegram

Alterações Principais para o robô de Telegram:

* Correcção na notificação da percentagem de lucro
* Esconder a informação errada no âmbito geral com base múltipla
* Capacidade de restringir o acesso ao Cryptosight a um ou mais utilizadores do Telegram
* Correcção na criar/apagar dos pares. Alteração são agora guardadas depois de regressar ao menu principal
* Mostrar contratos e preço de liquidação para margin



## 

{% page-ref page="../../setup-and-general-settings/installation/download.md" %}

