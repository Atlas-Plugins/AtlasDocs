---
description: Classe principal para manusear as funcionalidades do AtlasFactionsV2.
---

# AtlasFactionsAPI.class

## Métodos disponíveis:

* getFactionsHandler() - Retorna o Handler Main que cuida do gerenciamento da parte das facções.
* getClaimHandler() - Retorna o Handler Main que cuida do gerenciamento da parte dos claims.
* getRankingHandler() - Retorna o Handler Main que cuida do gerenciamento da parte de rankings.
* getScoreboardHandler() - Retorna o Handler Main que cuida da parte de scoreboard.

## FactionsHandler.class

Esta classe é responsável por cuidar das facções criadas no servidor e também é responsável por cuidar do objeto do usuário [AtlasFactionUser.class](https://docs.atlasplugins.com/atlasfactionsv2/objetos/atlasfactionuser.class).

{% hint style="danger" %}
Atenção: alguns métodos não podem ser chamados na main thread.
{% endhint %}

**Métodos disponíveis:**

* Você pode utilizar o método **getAtlasUser(Player player) ou getAtlasUser(String username)** para obter o [AtlasFactionUser.class](https://docs.atlasplugins.com/atlasfactionsv2/objetos/atlasfactionuser.class), no qual é o objeto que armazena todas as informações do player passado como parâmetro.
* Você pode utilizar o método **getFactionByUUID(UUID uuid)** ou **getFactionByUUID(String uuid)** para obter a classe [AtlasFaction.class](https://docs.atlasplugins.com/atlasfactionsv2/objetos/atlasfaction.class), no qual é o objeto que armazena todas as informações da facção.
* **needCoinsToCreateFaction() -** Verifica se o dono do plugin configurou no arquivo config.yml se é necessário coins para a criação de novas facções dentro do servidor.
* **existsFaction(String tagOrFactionName) ou existsFaction(UUID uuid) -** Verifica passando como parâmetro a TAG ou o nome completo ou o UUID da facção se a facção passada como parâmetro existe no servidor ou não.
* **isSlimeChunking(Player player) -** Verifica se um jogador ativou a procura por slimechunks pelo comando (/slimechunk)
* **isFactionUnderAttack(AtlasFaction faction) -** Verifica se uma facção está sob ataque.
* **getPlayerRelation(AtlasFactionUser playerOne, AtlasFactionUser playerTwo) -** Verifica a relação por meio da enum _PlayerRelation(SAME\_FACTION, ENEMY, ALLY, NEUTRAL)_ a relação entre dois jogadores dentro do servidor.
* **saveAll() -** Salva todas as facções do servidor no datastorage configurado na config.yml **(ESTE MÉTODO NÃO DEVE SER CHAMADO NA MAIN THREAD)**
* **getAllFactions() -** Retorna todas as facções do servidor **(ESTE MÉTODO NÃO DEVE SER CHAMADO NA MAIN THREAD)**
* **getAllUsers() -** Retorna todos os usuários do servidor **(ESTE MÉTODO NÃO DEVE SER CHAMADO NA MAIN THREAD)**

## ClaimHandler.class

Esta classe é responsável por cuidar dos claims de todos os mundos de todas as facções do servidor.

**Métodos disponíveis:**

* **canClaim(AtlasFaction faction, Chunk chunk, boolean temporary) -** Retorna a enum _ClaimResult(CHUNK\_IS\_OUTSIDE\_OF\_BORDER, CHUNK\_IS\_NOT\_CONNECTED, CHUNK\_IS\_PROTECTED\_ZONE, CHUNK\_IS\_NEARBY\_PROTECTED\_ZONE, CHUNK\_IS\_NEARBY\_OTHER\_CLAIM, CHUNK\_IS\_NEARBY\_CLAIMS\_FACTION\_USER, CHUNK\_ALREADY\_CLAIMED, CHUNK\_ALREADY\_CLAIMED\_BY\_FACTION\_USER, MAX\_TEMPORARY\_CLAIMS\_REACHED, INSUFFICIENT\_POWER, SUCCESSFULLY, SUCCESSFULLY\_PROTECTED)_ passando como parâmetro a facção a chunk que o usuário gostaria de claimar e o parâmetro boolean temporary indicando se é um terreno temporário ou não.
* **getClaim(Chunk chunk) getClaim(World world, int x, int z) ou getClaim(String world, long uuid) -** Retorna um _Optional\<AtlasClaim>_ onde você pode verificar se existe o claim ou não utilizando o _Optional#isPresent_ e se existir você pode utilizar o _Optional#get_ para obter o objeto _AtlasClaim.class_ armazenado dentro do _Optional_
* **claim(AtlasFaction faction, Chunk chunk, String claimer, boolean temporary) -** Adiciona um claim para a facção na Chunk passada como parâmetro.
* **isClaimed(Chunk chunk) -** Verifica se a chunk passada como parâmetro está claimada por uma facção ou não.
* **getCurrentFactionRegion(AtlasFactionUser factionUser, int x, int z, World world) -** Retorna a enum _FactionRegion(ALLY\_ZONE, ENEMY\_ZONE, YOUR\_FACTION\_ZONE, WILDERNESS\_ZONE, PROTECTED\_ZONE, WAR\_ZONE, NEUTRAL\_ZONE, UNDER\_ATTACK\_ZONE, TEMPORARY\_ZONE, OUTSIDE\_BORDER)_ indicando em qual tipo de região o jogador passado como parâmetro se encontra nas coordenadas passadas como parâmetro. _(Curiosidade: Este método é utilizando na scoreboard para a atualização da placeholder @region)_

## RankingHandler.class

Esta classe é responsável por cuidar dos rankings de facções dentro do servidor.

{% hint style="danger" %}
Atenção: alguns métodos não podem ser chamados na main thread.
{% endhint %}

**Métodos disponíveis:**

* **getFactionPosition(RankingType ranking, AtlasFaction faction) -** Retorna a posição da facção no ranking passado como parâmetro. _(Obs: o rankingtype do tipo VALUE é o ranking geral)_.
* **openRanking(Player player, RankingType ranking) -** Abre o scroller _(inventário com rolagem por arrows)_ para o jogador passado como parâmetro.
* **update() -** Força a atualização de todos os rankings do servidor **(Atenção: Este método não deve ser chamado na main thread)**

## ScoreboardHandler.class

Esta classe é responsável por cuidar do gerenciamento das scoreboards dentro do servidor. Utilizamos uma library pública de scoreboards chamada [FastBoard](https://github.com/MrMicky-FR/FastBoard).

* **forceUpdate(Player player) -** Força a atualização da scoreboard para o jogador passado como parâmetro.
* **updateRegion(Player player, Chunk newChunk) -** Atualiza o title da scoreboard subscrevendo a placeholder @region pela região atual do jogador.
* **updateScore(ScoreboardPlayer scoreboardPlayer) -** Atualiza a scoreboard passando o objeto ScoreboardPlayer como parâmetro.
* **addReplacements(Player player, FactionRegion region, AtlasFactionUser factionUser, Chunk to, String string) -** Subescreve as placeholders configuradas no arquivo config.yml.
* **buildScore(Player player, AtlasFactionUser factionUser) -** Cria a scoreboard para o jogador _(Este método é chamado ao jogador entrar no servidor)_

