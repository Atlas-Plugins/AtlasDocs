---
description: Comandos do AtlasLicense para o gerenciamento dos seus plugins comprados.
---

# Comandos e features extras

Este plugin possui apenas o comando `/atlas`, responsável pelo gerenciamento dos plugins.

{% hint style="info" %}
É necessário possuir a permissão **atlasplugins.admin** para utilizar este comando.
{% endhint %}

### Funções do comando

* `/atlas enable <plugin>`: Inicia um plugin da Atlas desabilitado.
* `/atlas disable <plugin>`: Desliga um plugin da Atlas que está rodando.
* `/atlas reload <plugin>`: Reinicia um plugin da Atlas que está rodando.

{% hint style="warning" %}
Atenção: Estes comandos podem prejudicar o funcionamento do plugin em questão, opte sempre por reiniciar o servidor com /stop.
{% endhint %}
