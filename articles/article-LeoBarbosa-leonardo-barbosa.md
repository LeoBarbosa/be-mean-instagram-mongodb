# MongoDb - Artigo sobre Autentica��o no MongoDb
**Autor:** Leonardo Barbosa de Oliveira
**Data**  15/12/2015 00:10

## Qual a diferen�a entre Autentica��o e Autoriza��o?

Autentica��o - deve verificar se um usu�rio � ele mesmo atrav�s de valida��o de senhas e/ou certificados.
Autoriza��o - com base em um usu�rio identificado, as regras e os controles de permiss�o e acesso ser�o aplicadas na aplica��o/produto e seus recursos.


## Descreva aqui o passo-a-passo como criar um usu�rio administrador e um usu�rio comum.

Diferenca entre usu�rio comun e administrador s�o as roles. Um administrador tem role que s�o suas fun��es, seus papeis que voce pode tanto selecionar o papel de uma outra database ou so na propria database.


Usu�rio Administrador:
use dbUsers
{
 createUser:"LeonardoAdmin",
 pwd:"SenhaTeste@",
 roles:[{role:"userAdminAnyDataBase", db:"dbUsers"}]
}

Usu�rio Comum:
use dbUsers
{
 createUser:"LeonardoUser",
 pwd:"SenhaTesteUser@",
 role:[{db:"dbUsers"}]
}


## Explique cada papel listado em Cluster Administration Roles.

- ClusterAdmin
Fornece o maior acesso de gerenciamento de cluster. Este papel combina os privil�gios concedidos pelos pap�is clusterManager, clusterMonitor, e hostManager. Al�m disso, o papel proporciona a a��o de dropDatabase.

- ClusterManager
Fornece gerenciamento e a��es de monitoramento no cluster. Um usu�rio com essa fun��o pode acessar a configura��o e bancos de dados locais, que s�o usados em sharding e replica��o, respectivamente.

- ClusterMonitor
Fornece acesso somente leitura para ferramentas de monitoramento, como o agente de monitoramento Gerente MongoDB Cloud.

- HostManager
Fornece a capacidade de monitorar e gerenciar servidores.



## Explique todas as a��es de privil�gio listadas em Privilege Actions.

A��es de privil�gio definem as opera��es que um usu�rio pode executar em um recurso. 
Um privil�gio MongoDB disp�e de um recurso e as a��es permitidas.

MongoDB fornece fun��es integrados com combina��o de pr�-definidas de recursos e a��es permitidas. 

- A��es e Consultas

find
O usu�rio pode executar o m�todo db.collection.find (). Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

insert
O usu�rio pode executar o comando de inser��o. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

remove
O usu�rio pode executar o m�todo db.collection.remove (). Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

update
O usu�rio pode executar o comando update. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

- A��es Gerenciamento Banco de Dados

changeCustomData
O usu�rio pode alterar as informa��es de costume de qualquer usu�rio no banco de dados fornecido. Aplicar esta a��o para recursos de banco de dados.

changeOwnCustomData
Os usu�rios podem alterar suas pr�prias informa��es personalizadas. Aplicar esta a��o para recursos de banco de dados. Veja tamb�m alterar sua senha e dados personalizados.

changeOwnPassword
Os usu�rios podem alterar suas pr�prias senhas. Aplicar esta a��o para recursos de banco de dados. Veja tamb�m alterar sua senha e dados personalizados.

changePassword
O usu�rio pode alterar a senha de qualquer usu�rio no banco de dados fornecido. Aplicar esta a��o para recursos de banco de dados.

createCollection
O usu�rio pode executar o m�todo db.createCollection (). Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

CreateIndex
Fornece acesso ao m�todo db.collection.createIndex () eo comando createIndexes. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

CREATEROLE
O usu�rio pode criar novas fun��es no banco de dados fornecido. Aplicar esta a��o para recursos de banco de dados.

createUser
O usu�rio pode criar novos usu�rios no banco de dados fornecido. Aplicar esta a��o para recursos de banco de dados.

dropCollection
O usu�rio pode executar o m�todo db.collection.drop (). Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

dropRole
O usu�rio pode excluir qualquer papel do banco de dados fornecido. Aplicar esta a��o para recursos de banco de dados.

dropuser
O usu�rio pode remover qualquer usu�rio do banco de dados fornecido. Aplicar esta a��o para recursos de banco de dados.

emptycapped
O usu�rio pode executar o comando emptycapped. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

enableProfiler
O usu�rio pode executar o m�todo db.setProfilingLevel (). Aplicar esta a��o para recursos de banco de dados.

grantRole
O usu�rio pode conceder qualquer papel no banco de dados para qualquer usu�rio de qualquer banco de dados no sistema. Aplicar esta a��o para recursos de banco de dados.

killCursors
O usu�rio pode matar os cursores no conjunto de destino.

revokeRole
O usu�rio pode remover qualquer papel de qualquer usu�rio a partir de qualquer banco de dados no sistema. Aplicar esta a��o para recursos de banco de dados.

unlock
O usu�rio pode executar o m�todo db.fsyncUnlock (). Aplicar esta a��o para o recurso de cluster.

viewRole
O usu�rio pode visualizar informa��es sobre qualquer fun��o no banco de dados fornecido. Aplicar esta a��o para recursos de banco de dados.

viewUser
O usu�rio pode visualizar as informa��es de qualquer usu�rio no banco de dados fornecido. Aplicar esta a��o para recursos de banco de dados.

A��es de gerenciamento de implanta��o

authSchemaUpgrade
O usu�rio pode executar o comando authSchemaUpgrade. Aplicar esta a��o para o recurso de cluster.

cleanupOrphaned
O usu�rio pode executar o comando cleanupOrphaned. Aplicar esta a��o para o recurso de cluster.

cpuProfiler
O usu�rio pode ativar e usar o profiler CPU. Aplicar esta a��o para o recurso de cluster.

inprog
O usu�rio pode usar o m�todo db.currentOp () para retornar pendentes e ativos opera��es. Aplicar esta a��o para o recurso de cluster.

invalidateUserCache
Fornece acesso ao comando invalidateUserCache. Aplicar esta a��o para o recurso de cluster.

killop
O usu�rio pode executar o m�todo db.killOp (). Aplicar esta a��o para o recurso de cluster.

planCacheRead
O usu�rio pode executar as planCacheListPlans e comandos planCacheListQueryShapes e os m�todos PlanCache.getPlansByQuery () e PlanCache.listQueryShapes (). Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

planCacheWrite
O usu�rio pode executar o comando planCacheClear eo PlanCache.clear () e PlanCache.clearPlansByQuery () m�todos. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

storageDetails
O usu�rio pode executar o comando storageDetails. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

- A��es de replica��o

appendOplogNote
Usu�rio pode acrescentar notas � oplog. Aplicar esta a��o para o recurso de cluster.

replSetConfigure
O usu�rio pode configurar um conjunto de r�plicas. Aplicar esta a��o para o recurso de cluster.

replSetGetStatus
O usu�rio pode executar o comando replSetGetStatus. Aplicar esta a��o para o recurso de cluster.

replSetHeartbeat
O usu�rio pode executar o comando replSetHeartbeat. Aplicar esta a��o para o recurso de cluster.

replSetStateChange
O usu�rio pode alterar o estado de um conjunto de r�plicas atrav�s da replSetFreeze, comandos replSetMaintenance, replSetStepDown, e replSetSyncFrom. Aplicar esta a��o para o recurso de cluster.

resync
O usu�rio pode executar o comando de ressincroniza��o. Aplicar esta a��o para o recurso de cluster.

- A��es Sharding

addShard
O usu�rio pode executar o comando addShard. Aplicar esta a��o para o recurso de cluster.

enableSharding
O usu�rio pode habilitar sharding em um banco de dados usando o comando enableSharding e pode caco uma cole��o usando o comando shardCollection. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

flushRouterConfig
O usu�rio pode executar o comando flushRouterConfig. Aplicar esta a��o para o recurso de cluster.

getShardMap
O usu�rio pode executar o comando getShardMap. Aplicar esta a��o para o recurso de cluster.

getShardVersion
O usu�rio pode executar o comando getShardVersion. Aplicar esta a��o para recursos de banco de dados.

listShards
O usu�rio pode executar o comando listShards. Aplicar esta a��o para o recurso de cluster.

moveChunk
O usu�rio pode executar o comando moveChunk. Al�m disso, o utilizador pode executar o comando movePrimary desde que o privil�gio � aplicado a um recurso base de dados apropriada. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

removeShard
O usu�rio pode executar o comando removeShard. Aplicar esta a��o para o recurso de cluster.

shardingState
O usu�rio pode executar o comando shardingState. Aplicar esta a��o para o recurso de cluster.

splitChunk
O usu�rio pode executar o comando splitChunk. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

splitVector
O usu�rio pode executar o comando splitVector. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

A��es de Administra��o de Servidor

applicationMessage
O usu�rio pode executar o comando logApplicationMessage. Aplicar esta a��o para o recurso de cluster.

closeAllDatabases
O usu�rio pode executar o comando closeAllDatabases. Aplicar esta a��o para o recurso de cluster.

collMod
O usu�rio pode executar o comando collMod. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

compactar
O usu�rio pode executar o comando compacto. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

connPoolSync
O usu�rio pode executar o comando connPoolSync. Aplicar esta a��o para o recurso de cluster.

convertToCapped
O usu�rio pode executar o comando convertToCapped. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

dropDatabase
O usu�rio pode executar o comando dropDatabase. Aplicar esta a��o para recursos de banco de dados.

dropIndex
O usu�rio pode executar o comando dropIndexes. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

fsync
O usu�rio pode executar o comando fsync. Aplicar esta a��o para o recurso de cluster.

getParameter
O usu�rio pode executar o comando getParameter. Aplicar esta a��o para o recurso de cluster.

hostInfo
Fornece informa��es sobre o servidor a inst�ncia MongoDB � executado. Aplicar esta a��o para o recurso de cluster.

logrotate
O usu�rio pode executar o comando logrotate. Aplicar esta a��o para o recurso de cluster.

reindexar
O usu�rio pode executar o comando REINDEX. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

renameCollectionSameDB
Permite que o usu�rio renomear cole��es no banco de dados atual usando o comando renameCollection. Aplicar esta a��o para recursos de banco de dados.

Al�m disso, o usu�rio deve ter encontrar na cole��o de origem ou n�o t�m encontrar na cole��o de destino.

Se uma cole��o com o novo nome j� existir, o usu�rio tamb�m deve ter a a��o dropCollection na cole��o de destino.

RepairDatabase
O usu�rio pode executar o comando RepairDatabase. Aplicar esta a��o para recursos de banco de dados.

setParameter
O usu�rio pode executar o comando setParameter. Aplicar esta a��o para o recurso de cluster.

shutdown
O usu�rio pode executar o comando de desligamento. Aplicar esta a��o para o recurso de cluster.

touch
O usu�rio pode executar o comando touch. Aplicar esta a��o para o recurso de cluster.

A��es de diagn�stico

collStats
O usu�rio pode executar o comando collStats. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

connPoolStats
O usu�rio pode executar as connPoolStats e comandos shardConnPoolStats. Aplicar esta a��o para o recurso de cluster.

cursorInfo
O usu�rio pode executar o comando cursorInfo. Aplicar esta a��o para o recurso de cluster.

dbHash
O usu�rio pode executar o comando dbHash. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

dbStats
O usu�rio pode executar o comando dbStats. Aplicar esta a��o para recursos de banco de dados.

diagLogging
O usu�rio pode executar o comando diagLogging. Aplicar esta a��o para o recurso de cluster.

getCmdLineOpts
O usu�rio pode executar o comando getCmdLineOpts. Aplicar esta a��o para o recurso de cluster.

getLog
O usu�rio pode executar o comando getLog. Aplicar esta a��o para o recurso de cluster.

indexStats
O usu�rio pode executar o comando indexStats. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

listDatabases
O usu�rio pode executar o comando listDatabases. Aplicar esta a��o para o recurso de cluster.

netstat
O usu�rio pode executar o comando netstat. Aplicar esta a��o para o recurso de cluster.

serverStatus
O usu�rio pode executar o comando serverStatus. Aplicar esta a��o para o recurso de cluster.

validar
O usu�rio pode executar o comando validate. Aplicar esta a��o para banco de dados ou de cobran�a de recursos.

topo
O usu�rio pode executar o comando top. Aplicar esta a��o para o recurso de cluster.

- A��es Internas

anyAction
Permite que qualquer a��o em um recurso. N�o atribua essa a��o, exceto em circunst�ncias excepcionais.

internal
Permite a��es internas. N�o atribua essa a��o, exceto em circunst�ncias excepcionais.



