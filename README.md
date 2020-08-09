# Implementation of Quartz using AdoJobStore in Clustered Environment

## Config for the AdoJobStore is the following, refer to quartz.config

`quartz.jobStore.type = Quartz.Impl.AdoJobStore.JobStoreTX, Quartz`
`quartz.jobStore.tablePrefix = QRTZ_`
`quartz.jobStore.dataSource = myDS`
`quartz.jobStore.lockHandler.type = Quartz.Impl.AdoJobStore.UpdateLockRowSemaphore, Quartz`
`quartz.jobStore.driverDelegateType = Quartz.Impl.AdoJobStore.SqlServerDelegate, Quartz`
`quartz.dataSource.myDS.connectionString = Server=localhost; Database= quartz; Integrated Security=True;`
`quartz.dataSource.myDS.provider = SqlServer`
`quartz.jobStore.useProperties = true`
`quartz.serializer.type = binary`

## Config for the Clustering are the following

`quartz.jobStore.clustered = true`
`quartz.jobStore.clusterCheckinInterval = 15000`
`quartz.scheduler.instanceId = AUTO`

## Managing the thread counts can be done using following way

`quartz.threadPool.threadCount = 10`

## Pre-configuration

Please update the database connection string path in `quartz.dataSource.myDS.connectionString` of `quartz.config`

Next create a database and execute the following file

`https://github.com/patravishek/quartz-clustering/blob/master/QuartzHostedService/Database/tables_quartz.sql`
