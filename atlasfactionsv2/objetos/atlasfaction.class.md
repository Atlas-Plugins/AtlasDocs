---
description: >-
  Objeto principal que fica encarregado de guardar todas as informações sobre
  uma facção.
---

# AtlasFaction.class

## Métodos disponíveis:

Todos estes métodos estão disponíveis para serem utilizados na classe AtlasFaction.class

```java
    public void flush();
    
    public void flushClaims();
    
    public void transferLeadership(final AtlasFactionUser p0);
    
    public boolean hasDiscordSynchronized();
    
    public void setSpawn(@NonNull final EntityType p0, @NonNull final Location p1);
    
    public void addMaxMembers();
    
    public boolean isMember(final Player p0);
    
    public boolean isMember(final String p0);
    
    public boolean reachedMaxMembers();
    
    public void acceptMember(final AtlasFactionUser p0);
    
    public boolean kickMember(final AtlasFactionUser p0);
    
    public boolean exitMember(final AtlasFactionUser p0);
    
    public ItemStack getEmptyBanner();
    
    public ItemStack getBanner();
    
    public int getTotalDeaths();
    
    public int getTotalKills();
    
    public Set<Player> getOnlineMembers();
    
    public FactionRelation getFactionRelation(final AtlasFaction p0);
    
    public boolean canRelationMemberInteract(final AtlasFactionUser p0, final Block p1);
    
    public int getTotalRelations();
    
    public boolean hasPendingRelationRequests();
    
    public boolean hasPendingRelationRequestFrom(final AtlasFaction p0);
    
    public List<AtlasRelationRequest> getRelationsRequests();
    
    public void removeAllRelationsWith(final AtlasFaction p0);
    
    public Optional<AtlasRelationRequest> getRelationRequest(final UUID p0);
    
    public void acceptRelationRequest(final AtlasRelationRequest p0, final AtlasFaction p1);
    
    public void declineRelationRequest(final AtlasRelationRequest p0, final AtlasFaction p1);
    
    public boolean hasRelation(final FactionRelation p0, final AtlasFaction p1);
    
    public boolean hasAnyRelation(final FactionRelation p0);
    
    public int getRelationAmount(final FactionRelation p0);
    
    public AtlasRelationship getRelations(final FactionRelation p0);
    
    public boolean hasMemberPermission(final FactionPermission p0, final Player p1);
    
    public boolean hasMemberPermission(final FactionPermission p0, final String p1);
    
    public boolean hasClaims();
    
    public void unClaim(final AtlasClaim p0);
    
    public void unClaim(final String p0, final long p1);
    
    public int unClaimAll();
    
    public boolean hasMembersOnline();
    
    public List<String> getAllMembers();
    
    public Optional<AtlasFactionMember> getMember(final String p0);
    
    public Optional<AtlasClaim> getRandomClaim();
    
    public int getTotalMembers();
    
    public int getTotalClaims();
    
    public List<AtlasClaim> getTemporaryClaims();
    
    public List<AtlasClaim> getClaims();
    
    public void addClaim(final String p0, final AtlasClaim p1);
    
    public boolean isUnderAttack();
    
    public int getUnderAttackClaims();
    
    public Future<List<CreatureSpawner>> getSpawnersInClaims(final List<Chunk> p0);
    
    public List<AtlasFactionMember> getMembersByPriority();
    
    public FactionRole getMemberRole(final String p0);
    
    public double getTotalCoins();
    
    public AtlasFaction calculateWorth();
    
    public double getSpawnersWorth();
    
    public double getWorth();
    
    public double getKDR();
    
    public int getPower();
    
    public int getMaxPower();
    
    @Override
    public String getKey();
    
    public Stream<AtlasClaim> getClaimsStream();
    
    @Override
    public int hashCode();
    
    @Override
    public boolean equals(final Object p0);
    
    public UUID getFactionId();
    
    public String getName();
    
    public String getTag();
    
    public String getOwner();
    
    public Location getBase();
    
    public int getMaxMembers();
    
    public int getWonWars();
    
    public AtlasSpawnersStorage getSpawnersStorage();
    
    public AtlasMembersMap getMembers();
    
    public AtlasFactionChest getChest();
    
    public AtlasRelationship getAllies();
    
    public AtlasRelationship getEnemies();
    
    public AtlasRelationship getNeutral();
    
    public Map<EntityType, Location> getSpawnLocations();
    
    public int getEnemyKills();
    
    public int getEnemyDeaths();
    
    public int getCivilKills();
    
    public int getCivilDeaths();
    
    public int getNeutralKills();
    
    public int getNeutralDeaths();
    
    public long getDiscordChannel();
    
    public long getCreatedAt();
    
    public long getLastPowerUpdate();
    
    public long getLastKDRUpdate();
    
    public long getLastKillsUpdate();
    
    public long getLastDeathsUpdate();
    
    public int getStoragedAmount();
    
    public int getInClaimsAmount();
    
    public Map<EntityType, Integer> getSpawnersCache();
    
    public void setBase(final Location p0);
    
    public void setMaxMembers(final int p0);
    
    public void setWonWars(final int p0);
    
    public void setDiscordChannel(final long p0);
```

