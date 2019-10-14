---
description: Instrucões para instalar Gunbot numa máquina macOS.
---

# Instalação em macOS

## Instruções

1. Descompactar o ficheiro .zip da release para uma pasta nova
2. Iniciar Gunbot com o seguinte comando num terminal na pasta do Gunbot:  `./gunthy-macos`. Mantenha esta janela de terminal aberta.
3. Abrir [localhost:5000](http://localhost:5000) no browser do mesmo sistema para aceder ao GUI do Gunbot \(Browsers modernos são recomendados, preferencialmente Chrome ou Firefox\)
4. Ter atenção para introduzir  [a sua carteira ERC-20 registada](../exchange-and-license-settings/gunthy-wallet/) \("Gunthy wallet"\) e a sua [chave API registada](../exchange-and-license-settings/connect-exchange/) no Gunbot antes de iniciar o bot core pela primeira vez.

{% hint style="info" %}
Dependendo das suas definições de sistema, poderá ter que adicionar uma regra na firewall para permitir tráfego de entrada na porta TCP 5000.
{% endhint %}

{% hint style="info" %}
### Nota para utilizadores core

A definição por defeito é que o GUI inicia automáticamente mas o processamento de pares não. Definir`"start": true,` na `config.js` para iniciar o processamento de pares \(cycling\).
{% endhint %}

{% hint style="danger" %}
### Aviso de Segurança

Gunbot está preparado para correr no seu sistema local. Colocar o Gunbot GUI disponível para redes externas é um risco inerente e só o faça à sua responsabilidade.

Esforços consideráveis foram realizados para tornar o GUI seguro mas, entenda que atingir 100% de segurança simplesmente não é realista.
{% endhint %}

## Video de instalação

{% embed url="https://youtu.be/W2dArdu8jus" caption="" %}

_O video acima foi feito com o Gunbot v10, no entanto, os passos básicos ainda se aplicam._[  
](https://gunbotbeta.gitbook.io/gunbot-beta/getting-started/installation/download)

