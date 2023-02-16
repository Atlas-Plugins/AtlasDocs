---
description: >-
  Objeto principal que fica encarregado de guardar todas as informações sobre um
  usuário dentro do servidor.
---

# AtlasFactionUser.class

## Métodos disponíveis:

Todos estes métodos estão disponíveis para serem utilizados com a classe AtlasFactionUser.class

```java
    public ItemStack getHead();
    
    public boolean canSeeMap();
    
    public List<AtlasInvite> getInvitations();
    
    public void addInvitation(final UUID uuid);
    
    public void acceptInvitation(final AtlasFaction faction);
    
    public AtlasInvite getInvitation(final UUID uuid);
    
    public void removeInvitation(final UUID uuid);
    
    public boolean hasInviteFrom(final UUID uuid);
    
    public double getKDR();
    
    public int getTotalDeaths();
    
    public int getTotalKills();
    
    public void losePower();
    
    public void recoverPower();
    
    public void addMaxPower();
    
    public void setFaction(final AtlasFaction faction);
    
    public FactionRole getFactionRole();
    
    public Player getPlayer();
    
    public boolean isOnline();
    
    public Optional<AtlasFaction> getFaction();
    
    public boolean hasFaction();
    
    @Override
    public String getKey();
    
    public String getUsername();
    
    public UUID getFactionId();
    
    public FactionRegion getLastRegion();
    
    public long getLastRegionChange();
    
    public int getPower();
    
    public int getMaxPower();
    
    public int getWonWars();
    
    public long getLastLogin();
    
    public long getLastDeath();
    
    public void setLastRegion(final FactionRegion region);
    
    public void setLastRegionChange(final long millis);
    
    public void setPower(final int power);
    
    public void setMaxPower(final int maxPower);
    
    public void setWonWars(final int wonWars);
    
    public void setLastLogin(final long lastLogin);
    
    public void setLastDeath(final long lastDeath);
```

## Observações:

Esta classe extende a classe _AtlasEntity.class_ que é responsável por tomar conta de variaveis de contagem de kills / deaths / informações booleanas como ativar "/f mapa" e ativar "/f verchunks", portanto os métodos desta classe também são acessíveis a partir da classe _AtlasFactionUser.class_

### Métodos disponíveis:

```java
    public void resetKDR();
    
    public void addEnemyDeath();
    
    public void addEnemyKills();
    
    public void addNeutralKills();
    
    public void addNeutralDeaths();
    
    public void addCivilKills();
    
    public void addCivilDeaths();
    
    public int getEnemyKills();
    
    public int getEnemyDeaths();
    
    public int getNeutralKills();
    
    public int getNeutralDeaths();
    
    public int getCivilKills();
    
    public int getCivilDeaths();
    
    public boolean isViewMap();
    
    public boolean isViewChunks();
    
    public void setEnemyKills(final int enemyKills);
    
    public void setEnemyDeaths(final int enemyDeaths);
    
    public void setNeutralKills(final int neutralKills);
    
    public void setNeutralDeaths(final int neutralDeaths);
    
    public void setCivilKills(final int civilKills);
    
    public void setCivilDeaths(final int civilDeaths);
    
    public void setViewMap(final boolean viewMap);
    
    public void setViewChunks(final boolean viewChunks);
    
    @Override
    public boolean equals(final Object object);
    
    protected boolean canEqual(final Object object);
    
    @Override
    public int hashCode();
    
    @Override
    public String toString();
```
