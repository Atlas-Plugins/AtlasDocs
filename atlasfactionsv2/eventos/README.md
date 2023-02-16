---
description: Lista de todos os eventos disponíveis na API do AtlasFactionsV2.
---

# Eventos

## Informações gerais

Alguns eventos implementam a classe _Cancellable_ no qual deixa disponível sempre os métodos:

```java
public boolean isCancelled();
public boolean setCancelled(boolean cancel);
```

Estes métodos verificam / setam informações no evento, então você pode cancelar os eventos que implementarem a classe _Cancellable_ .

## Exemplo de utilização

Aqui vai um exemplo básico de utilização de um evento de nosso plugin.

```java
@EventHandler
public void onActiveSpecialItem(AtlasPlayerSpecialItemActiveEvent event) {
   // Jogador que ativou o item
   Player player = event.getPlayer(); 
   
   // Item que o jogador ativou
   SpecialItem item = event.getSpecialItem();
   
   // Verifica se o evento foi cancelado por outro plugin e cancela todo o resto do código abaixo.
   if(event.isCancelled()) return;
   
   // Envia um simples broadcast
   Bukkit.broadcastMessage("O jogador " + player.getName() + " ativou o item " + item.getItem().getItemMeta().getDisplayName());
}
```
