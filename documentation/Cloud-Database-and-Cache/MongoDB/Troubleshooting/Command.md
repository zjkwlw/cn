# 云数据库 MongoDB 限制了哪些命令？

## 问题描述

云数据库 MongoDB 限制了哪些命令?

## 问题处理
云数据库 MongoDB 支持与限制的命令情况如下：

命令	支持	不支持
Aggregates Commands	        • aggregate	
	        • distinct
	        • count
	        • group
	        • mapReduce
Authentication	        • logout	
	        • authenticate
	        • getnonce
	        • authSchemaUpgrade
	        • copydbgetnonce
Diagnostic Commands	        • explain	
	        • listDatabases
	        • dbHash
	        • listCommands
	        • availableQueryOptions
	        • buildInfo
	        • collStats
	        • dbStats
	        • cursorInfo
	        • dataSize
	        • ping
	        • profile
	        • top
	        • whatsmyuri
	        • serverStatus
	        • features
	        • isSelf
	        • validate
Geospatial Commands	        • geoNear	
	        • geoSearch
Instance Administration Commands	        • renameCollection	
	        • dropDatabase
	        • listCollections
	        • drop
	        • create
	        • cloneCollection
	        • cloneCollectionAsCapped
	        • convertToCapped
	        • filemd5
	        • createIndexes
	        • listIndexes
	        • dropIndexes
	        • fsync
	        • connectionStatus
	        • collMod
	        • reIndex
	        • touch
	        • getParameter
	        • compact
	        • copydb
	        • clone
	        • clean
	        • shutdown
	        • logRotate
	        • repairDatabase
	        • repairCursor
	        • setParameter
	        • connPoolSync
	        • setReadonly
	        • cloneCollection
Query and Write Operation Commands	        • insert	
	        • update
	        • delete
	        • findAndModify
	        • getLastError
	        • getPrevError
	        • resetError
	        • parallelCollectionScan
	        • eval
Query Plan Cache Commands	        • planCacheListFilters	
	        • planCacheSetFilter
	        • planCacheClearFilters
	        • planCacheListQueryShapes
	        • planCacheListPlans
	        • planCacheClear
Replication Commands		        • replSetInitiate
		        • replSetFreeze
		        • replSetMaintenance
		        • replSetGetConfig
		        • replSetRequestVotes
		        • replSetReconfig
		        • replSetStepDown
		        • replSetSyncFrom
		        • replSetElect
		        • replSetUpdatePosition
		        • resync
		        • appendOplogNote
Replication Commands Diagnostic	        • isMaster	
	        • applyOps
Role Management Commands	        • createRole	
	        • updateRole
	        • dropRole
	        • dropAllRolesFromDatabase
	        • grantPrivilegesToRole
	        • revokePrivilegesFromRole
	        • grantRolesToRole
	        • revokeRolesFromRole
	        • rolesInfo
	        • invalidateUserCache
Sharding Commands		        • addShard
		        • removeShard
		        • getShardVersion
		        • setShardVersion
		        • unsetSharding
		        • checkShardingIndex
User Management Commands	        • createUser	
	        • updateUser
	        • dropUser
	        • dropAllUsersFromDatabase
	        • grantRolesToUser
	        • revokeRolesFromUser
	        • usersInfo
