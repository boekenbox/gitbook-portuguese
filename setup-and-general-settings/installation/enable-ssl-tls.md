---
description: Instruções para correr o GUI do Gunbot no browser com ligação segura.
---

# Como Activar SSL/TLS

## Executar o GUI em https com um certificado do tipo self-signed

Para executar o GUI em https é necessário um certificado. De seguida, as instruções para gerar um certificado do tipo self-signed, para Windows, Mac e Linux.

{% hint style="info" %}
Certificados de fabricantes conhecidos de SSL funcionam também. Apenas é necessário garantir que os ficheiros são renomeados e as extensões alteradas para .crt \(certificado\) e .key \(chave privada\) .Posteriormente bastará colocar os ficheiros na pasta do Gunbot.
{% endhint %}

Garantir que o parâmetro `https` no ficheiro `config.js` está como `true` para habilitar o https após a criação do certificado e a sua cópia para a mesma pasta do Gunbot.

Quando se abre o GUI pela primeira vez, provavelmente encontrará um aviso do browser acerca do certificado devido a este ser do tipo self-signed. Para não voltar a visualizar o aviso no mesmo browser, criar uma excepção permanente.

### **Windows**

1. [Download](https://slproweb.com/products/Win32OpenSSL.html) e instalar OpenSSL para windows.
2. Ir para a seguinte pasta: C:\OpenSSL-Win64\bin\
3. Clickar com o botão direito do rato em  "openssl" e escolher a opção executar como Administrador, uma janela de terminal irá abrir.
4. Executar o seguinte comando: `req -newkey rsa:2048 -nodes -keyout localhost.key -x509 -days 365 -out localhost.crt` \(Serão pedidos vários detalhes para serem preenchidos, pode preencher ou deixar em branco, bastando para tal ir carregando em enter para avançar\)
5. Copiar `localhost.key` e `localhost.crt` de C:\OpenSSL-Win64\bin para a pasta do Gunbot

### **Mac**

1. Abrir uma janela de terminal e navegar até à pasta do Gunbot
2. Executar o seguinte comando: `openssl req -newkey rsa:2048 -nodes -keyout localhost.key -x509 -days 365 -out localhost.crt` e garantir que introduz o campo do código do país \(country code field\). O resto pode ficar em branco.

### **Linux**

1. Abrir uma janela de terminal e navegar até à pasta do Gunbot. Poderá ter que instalar primeiro o openssl através do package manager do linux.
2. Executar o seguinte comando: 

   `openssl req -newkey rsa:2048 -nodes -keyout localhost.key -x509 -days 365 -out localhost.crt` 

   e garantir que introduz o campo do código do país \(country code field\). O resto pode ficar em branco.

