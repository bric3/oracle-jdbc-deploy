# Oracle JDBC Deploy

Deploys Oracle JDBC artifacts to your private maven repository so that they are
easily consumed by your other projects.

## How to use

1. Download the Oracle artifacts from [OTN][1]:

    * javadoc.zip
    * ojdbc6dms_g.jar
    * ojdbc6dms.jar
    * ojdbc6_g.jar
    * ojdbc6.jar
    * ojdbc7dms_g.jar
    * ojdbc7dms.jar
    * ojdbc7_g.jar
    * ojdbc7.jar
    * ons.jar
    * orai18n.jar
    * simplefan.jar
    * ucp.jar
    * ucp_javadoc.zip
    * xdb6.jar

2. Execute:

        mvn \
          -Doracle.dir=/my/Downloads \
          -DrepositoryId=myRepo \
          -Durl=http://example.com/nexus/content/repositories/thirdparty/ \
          deploy

    Where:

    * `oracle.dir` - the directory where Oracle artifacts were saved.
    * `repositoryId` - Server Id to map on the `<id>` under `<server>` section
        of **settings.xml**. In most cases, this parameter will be required
        for authentication.
    * `url` - URL where the artifact will be deployed.

[1]: http://www.oracle.com/technetwork/database/features/jdbc/default-2280470.html
