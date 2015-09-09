Kitchensink on DeployDock
=========================

This is the kitchensink JBoss quickstart app.  You can find more info @ http://www.jboss.org/jdf/quickstarts/jboss-as-quickstart/guide/KitchensinkQuickstart/

Running on DeployDock
--------------------

Create an account at https://www.deploydock.com

Create a jbossas-7 application

    dk app create kitchensink jbossas-7 --from-code git://github.com/Meros-io/kitchensink-example.git

That's it, you can now checkout your application at:

    http://kitchensink-$namespace.apps.deploydock.io

PostgreSQL as a backend
-----------------------
By default, this quickstart uses H2 as the backend, but you may use
PostgreSQL.

To do this, add PostgreSQL cartridge to your application:

    rhc cartridge add postgresql-8.4 -a kitchensink

Edit `src/main/resources/META-INF/persistence.xml` so that the data
source points to `java:jboss/datasources/PostgreSQLDS`:

    <jta-data-source>java:jboss/datasources/PostgreSQLDS</jta-data-source>

Commit this change, and push.
