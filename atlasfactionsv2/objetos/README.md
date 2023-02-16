---
description: Lista de todos os objetos disponíveis no AtlasFactionsV2.
---

# Objetos

## Informações gerais

Os objetos principais (main objects) que são os que são salvos no datastorage configurado na config.yml sempre implementam a interface _Storable_&#x20;

```java
package com.atlasplugins.atlasfactionsv2.storager.interfaces;

public interface Storable {

	public String getKey();

}

```

na qual como você pode ver acima, sempre existe o método getKey() para obter a chave do banco de dados (chave/valor)

## Exemplo de utilização

Para uma melhor performance, sempre prefira utilizar variáveis ao invés de sempre efetuar calls e chamadas na API.

Aqui vai alguns exemplos de códigos:

{% hint style="danger" %}
Exemplo de código mal feito e mal elaborado que efetua várias calls
{% endhint %}

```java
// Bad code
@EventHandler
public void onPlayerInteract(PlayerInteractEvent event){
    if(event.getAction().equals(Action.RIGHT_CLICK_BLOCK)){
        if(!factionsHandler.getAtlasUser(event.getPlayer()).get().getFaction().isPresent()) return;
        String facTag = factionsHandler.getAtlasUser(event.getPlayer()).get().getFaction().get().getTag();
        String facName = factionsHandler.getAtlasUser(event.getPlayer()).get().getFaction().get().getName();
    }
}
```

{% hint style="success" %}
Exemplo de um código bem elaborado e bem feito
{% endhint %}

```java
// Good code
@EventHandler
public void onPlayerInteract(PlayerInteractEvent event){
    if(!event.getAction().equals(Action.RIGHT_CLICK_BLOCK)) return;
    Player player = event.getPlayer();
    AtlasFactionUser factionUser = factionsHandler.getAtlasUser(player).get();
    Optional<AtlasFaction> optional = factionUser.getFaction();
    if(!optional.isPresent()) return;
    AtlasFaction faction = optional.get();
    String facTag = faction.getTag(), facName = faction.getName();
}
```
