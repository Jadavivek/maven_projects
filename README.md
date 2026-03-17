<persistence xmlns="https://jakarta.ee/xml/ns/persistence" version="3.0">

    <persistence-unit name="myPU">

        <properties>
            <property name="jakarta.persistence.jdbc.driver" value="com.mysql.cj.jdbc.Driver"/>
            <property name="jakarta.persistence.jdbc.url" value="jdbc:mysql://localhost:3306/jada"/>
            <property name="jakarta.persistence.jdbc.user" value="root"/>
            <property name="jakarta.persistence.jdbc.password" value="root"/>

            <property name="hibernate.hbm2ddl.auto" value="update"/>
            <property name="hibernate.show_sql" value="true"/>
        </properties>

    </persistence-unit>

</persistence>
Mar 17, 2026 8:00:56 PM org.hibernate.jpa.internal.util.LogHelper logPersistenceUnitInformation
INFO: HHH000204: Processing PersistenceUnitInfo [name: myPU]
Mar 17, 2026 8:00:56 PM org.hibernate.Version logVersion
INFO: HHH000412: Hibernate ORM core version 6.4.4.Final
Mar 17, 2026 8:00:56 PM org.hibernate.cache.internal.RegionFactoryInitiator initiateService
INFO: HHH000026: Second-level cache disabled
Mar 17, 2026 8:00:57 PM org.hibernate.engine.jdbc.connections.internal.DriverManagerConnectionProviderImpl configure
WARN: HHH10001002: Using built-in connection pool (not intended for production use)
Mar 17, 2026 8:00:57 PM org.hibernate.engine.jdbc.connections.internal.DriverManagerConnectionProviderImpl buildCreator
INFO: HHH10001005: Loaded JDBC driver class: com.mysql.cj.jdbc.Driver
Mar 17, 2026 8:00:57 PM org.hibernate.engine.jdbc.connections.internal.DriverManagerConnectionProviderImpl buildCreator
INFO: HHH10001012: Connecting with JDBC URL [jdbc:mysql://localhost:3306/jada]
Mar 17, 2026 8:00:57 PM org.hibernate.engine.jdbc.connections.internal.DriverManagerConnectionProviderImpl buildCreator
INFO: HHH10001001: Connection properties: {password=****, user=root}
Mar 17, 2026 8:00:57 PM org.hibernate.engine.jdbc.connections.internal.DriverManagerConnectionProviderImpl buildCreator
INFO: HHH10001003: Autocommit mode: false
Mar 17, 2026 8:00:57 PM org.hibernate.engine.jdbc.connections.internal.DriverManagerConnectionProviderImpl$PooledConnections <init>
INFO: HHH10001115: Connection pool size: 20 (min=1)
Mar 17, 2026 8:00:58 PM org.hibernate.engine.jdbc.env.internal.JdbcEnvironmentInitiator getJdbcEnvironmentUsingJdbcMetadata
WARN: HHH000342: Could not obtain connection to query metadata
java.lang.IllegalStateException: Cannot get a connection as the driver manager is not properly initialized
	at org.hibernate.engine.jdbc.connections.internal.DriverManagerConnectionProviderImpl.getConnection(DriverManagerConnectionProviderImpl.java:259)
	at org.hibernate.engine.jdbc.env.internal.JdbcEnvironmentInitiator$ConnectionProviderJdbcConnectionAccess.obtainConnection(JdbcEnvironmentInitiator.java:428)
	at org.hibernate.resource.transaction.backend.jdbc.internal.JdbcIsolationDelegate.delegateWork(JdbcIsolationDelegate.java:61)
	at org.hibernate.engine.jdbc.env.internal.JdbcEnvironmentInitiator.getJdbcEnvironmentUsingJdbcMetadata(JdbcEnvironmentInitiator.java:276)
	at org.hibernate.engine.jdbc.env.internal.JdbcEnvironmentInitiator.initiateService(JdbcEnvironmentInitiator.java:107)
	at org.hibernate.engine.jdbc.env.internal.JdbcEnvironmentInitiator.initiateService(JdbcEnvironmentInitiator.java:68)
	at org.hibernate.boot.registry.internal.StandardServiceRegistryImpl.initiateService(StandardServiceRegistryImpl.java:130)
	at org.hibernate.service.internal.AbstractServiceRegistryImpl.createService(AbstractServiceRegistryImpl.java:263)
	at org.hibernate.service.internal.AbstractServiceRegistryImpl.initializeService(AbstractServiceRegistryImpl.java:238)
	at org.hibernate.service.internal.AbstractServiceRegistryImpl.getService(AbstractServiceRegistryImpl.java:215)
	at org.hibernate.engine.jdbc.internal.JdbcServicesImpl.configure(JdbcServicesImpl.java:52)
	at org.hibernate.boot.registry.internal.StandardServiceRegistryImpl.configureService(StandardServiceRegistryImpl.java:136)
	at org.hibernate.service.internal.AbstractServiceRegistryImpl.initializeService(AbstractServiceRegistryImpl.java:247)
	at org.hibernate.service.internal.AbstractServiceRegistryImpl.getService(AbstractServiceRegistryImpl.java:215)
	at org.hibernate.engine.jdbc.connections.internal.BasicConnectionCreator.convertSqlException(BasicConnectionCreator.java:132)
	at org.hibernate.engine.jdbc.connections.internal.DriverConnectionCreator.makeConnection(DriverConnectionCreator.java:43)
	at org.hibernate.engine.jdbc.connections.internal.BasicConnectionCreator.createConnection(BasicConnectionCreator.java:61)
	at org.hibernate.engine.jdbc.connections.internal.DriverManagerConnectionProviderImpl$PooledConnections.addConnections(DriverManagerConnectionProviderImpl.java:499)
	at org.hibernate.engine.jdbc.connections.internal.DriverManagerConnectionProviderImpl$PooledConnections.<init>(DriverManagerConnectionProviderImpl.java:372)
	at org.hibernate.engine.jdbc.connections.internal.DriverManagerConnectionProviderImpl$PooledConnections$Builder.build(DriverManagerConnectionProviderImpl.java:550)
	at org.hibernate.engine.jdbc.connections.internal.DriverManagerConnectionProviderImpl.buildPool(DriverManagerConnectionProviderImpl.java:102)
	at org.hibernate.engine.jdbc.connections.internal.DriverManagerConnectionProviderImpl.configure(DriverManagerConnectionProviderImpl.java:82)
	at org.hibernate.boot.registry.internal.StandardServiceRegistryImpl.configureService(StandardServiceRegistryImpl.java:136)
	at org.hibernate.service.internal.AbstractServiceRegistryImpl.initializeService(AbstractServiceRegistryImpl.java:247)
	at org.hibernate.service.internal.AbstractServiceRegistryImpl.getService(AbstractServiceRegistryImpl.java:215)
	at org.hibernate.engine.jdbc.env.internal.JdbcEnvironmentInitiator.buildJdbcConnectionAccess(JdbcEnvironmentInitiator.java:395)
	at org.hibernate.engine.jdbc.env.internal.JdbcEnvironmentInitiator.getJdbcEnvironmentUsingJdbcMetadata(JdbcEnvironmentInitiator.java:262)
	at org.hibernate.engine.jdbc.env.internal.JdbcEnvironmentInitiator.initiateService(JdbcEnvironmentInitiator.java:107)
	at org.hibernate.engine.jdbc.env.internal.JdbcEnvironmentInitiator.initiateService(JdbcEnvironmentInitiator.java:68)
	at org.hibernate.boot.registry.internal.StandardServiceRegistryImpl.initiateService(StandardServiceRegistryImpl.java:130)
	at org.hibernate.service.internal.AbstractServiceRegistryImpl.createService(AbstractServiceRegistryImpl.java:263)
	at org.hibernate.service.internal.AbstractServiceRegistryImpl.initializeService(AbstractServiceRegistryImpl.java:238)
	at org.hibernate.service.internal.AbstractServiceRegistryImpl.getService(AbstractServiceRegistryImpl.java:215)
	at org.hibernate.boot.model.relational.Database.<init>(Database.java:45)
	at org.hibernate.boot.internal.InFlightMetadataCollectorImpl.getDatabase(InFlightMetadataCollectorImpl.java:223)
	at org.hibernate.boot.internal.InFlightMetadataCollectorImpl.<init>(InFlightMetadataCollectorImpl.java:191)
	at org.hibernate.boot.model.process.spi.MetadataBuildingProcess.complete(MetadataBuildingProcess.java:170)
	at org.hibernate.jpa.boot.internal.EntityManagerFactoryBuilderImpl.metadata(EntityManagerFactoryBuilderImpl.java:1432)
	at org.hibernate.jpa.boot.internal.EntityManagerFactoryBuilderImpl.build(EntityManagerFactoryBuilderImpl.java:1503)
	at org.hibernate.jpa.HibernatePersistenceProvider.createEntityManagerFactory(HibernatePersistenceProvider.java:55)
	at jakarta.persistence.Persistence.createEntityManagerFactory(Persistence.java:80)
	at jakarta.persistence.Persistence.createEntityManagerFactory(Persistence.java:55)
	at com.seed.util.JPAUtil.<clinit>(JPAUtil.java:8)
	at com.seed.dao.MovieDAO.<init>(MovieDAO.java:10)
	at com.seed.App.main(App.java:70)

Exception in thread "main" java.lang.ExceptionInInitializerError
	at com.seed.dao.MovieDAO.<init>(MovieDAO.java:10)
	at com.seed.App.main(App.java:70)
Caused by: org.hibernate.service.spi.ServiceException: Unable to create requested service [org.hibernate.engine.jdbc.env.spi.JdbcEnvironment] due to: Error calling Driver#connect [null]
	at org.hibernate.service.internal.AbstractServiceRegistryImpl.createService(AbstractServiceRegistryImpl.java:276)
	at org.hibernate.service.internal.AbstractServiceRegistryImpl.initializeService(AbstractServiceRegistryImpl.java:238)
	at org.hibernate.service.internal.AbstractServiceRegistryImpl.getService(AbstractServiceRegistryImpl.java:215)
	at org.hibernate.boot.model.relational.Database.<init>(Database.java:45)
	at org.hibernate.boot.internal.InFlightMetadataCollectorImpl.getDatabase(InFlightMetadataCollectorImpl.java:223)
	at org.hibernate.boot.internal.InFlightMetadataCollectorImpl.<init>(InFlightMetadataCollectorImpl.java:191)
	at org.hibernate.boot.model.process.spi.MetadataBuildingProcess.complete(MetadataBuildingProcess.java:170)
	at org.hibernate.jpa.boot.internal.EntityManagerFactoryBuilderImpl.metadata(EntityManagerFactoryBuilderImpl.java:1432)
	at org.hibernate.jpa.boot.internal.EntityManagerFactoryBuilderImpl.build(EntityManagerFactoryBuilderImpl.java:1503)
	at org.hibernate.jpa.HibernatePersistenceProvider.createEntityManagerFactory(HibernatePersistenceProvider.java:55)
	at jakarta.persistence.Persistence.createEntityManagerFactory(Persistence.java:80)
	at jakarta.persistence.Persistence.createEntityManagerFactory(Persistence.java:55)
	at com.seed.util.JPAUtil.<clinit>(JPAUtil.java:8)
	... 2 more
Caused by: org.hibernate.exception.SQLGrammarException: Error calling Driver#connect [null]
	at org.hibernate.exception.internal.SQLStateConversionDelegate.convert(SQLStateConversionDelegate.java:91)
	at org.hibernate.engine.jdbc.connections.internal.BasicConnectionCreator$1.convert(BasicConnectionCreator.java:118)
	at org.hibernate.engine.jdbc.connections.internal.BasicConnectionCreator.convertSqlException(BasicConnectionCreator.java:143)
	at org.hibernate.engine.jdbc.connections.internal.DriverConnectionCreator.makeConnection(DriverConnectionCreator.java:43)
	at org.hibernate.engine.jdbc.connections.internal.BasicConnectionCreator.createConnection(BasicConnectionCreator.java:61)
	at org.hibernate.engine.jdbc.connections.internal.DriverManagerConnectionProviderImpl$PooledConnections.addConnections(DriverManagerConnectionProviderImpl.java:499)
	at org.hibernate.engine.jdbc.connections.internal.DriverManagerConnectionProviderImpl$PooledConnections.<init>(DriverManagerConnectionProviderImpl.java:372)
	at org.hibernate.engine.jdbc.connections.internal.DriverManagerConnectionProviderImpl$PooledConnections$Builder.build(DriverManagerConnectionProviderImpl.java:550)
	at org.hibernate.engine.jdbc.connections.internal.DriverManagerConnectionProviderImpl.buildPool(DriverManagerConnectionProviderImpl.java:102)
	at org.hibernate.engine.jdbc.connections.internal.DriverManagerConnectionProviderImpl.configure(DriverManagerConnectionProviderImpl.java:82)
	at org.hibernate.boot.registry.internal.StandardServiceRegistryImpl.configureService(StandardServiceRegistryImpl.java:136)
	at org.hibernate.service.internal.AbstractServiceRegistryImpl.initializeService(AbstractServiceRegistryImpl.java:247)
	at org.hibernate.service.internal.AbstractServiceRegistryImpl.getService(AbstractServiceRegistryImpl.java:215)
	at org.hibernate.engine.jdbc.env.internal.JdbcEnvironmentInitiator.buildJdbcConnectionAccess(JdbcEnvironmentInitiator.java:395)
	at org.hibernate.engine.jdbc.env.internal.JdbcEnvironmentInitiator.getJdbcEnvironmentUsingJdbcMetadata(JdbcEnvironmentInitiator.java:262)
	at org.hibernate.engine.jdbc.env.internal.JdbcEnvironmentInitiator.initiateService(JdbcEnvironmentInitiator.java:107)
	at org.hibernate.engine.jdbc.env.internal.JdbcEnvironmentInitiator.initiateService(JdbcEnvironmentInitiator.java:68)
	at org.hibernate.boot.registry.internal.StandardServiceRegistryImpl.initiateService(StandardServiceRegistryImpl.java:130)
	at org.hibernate.service.internal.AbstractServiceRegistryImpl.createService(AbstractServiceRegistryImpl.java:263)
	... 14 more
Caused by: java.sql.SQLSyntaxErrorException: Unknown database 'jada'
	at com.mysql.cj.jdbc.exceptions.SQLError.createSQLException(SQLError.java:121)
	at com.mysql.cj.jdbc.exceptions.SQLExceptionsMapping.translateException(SQLExceptionsMapping.java:122)
	at com.mysql.cj.jdbc.ConnectionImpl.createNewIO(ConnectionImpl.java:815)
	at com.mysql.cj.jdbc.ConnectionImpl.<init>(ConnectionImpl.java:438)
	at com.mysql.cj.jdbc.ConnectionImpl.getInstance(ConnectionImpl.java:241)
	at com.mysql.cj.jdbc.NonRegisteringDriver.connect(NonRegisteringDriver.java:189)
	at org.hibernate.engine.jdbc.connections.internal.DriverConnectionCreator.makeConnection(DriverConnectionCreator.java:40)
	... 29 more
