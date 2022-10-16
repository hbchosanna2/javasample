# nexus--maven-samples
Series of tutorial code snippets for use
#Maven publish tutorial steps
Publishing artifact to Nexus snapshot and release repo using maven.

1. Create a snapshot repo using nexus, or use default coming in out of the box.
2. Create a release repo using nexus, or use default coming out of the box.
3. Create a group repo having both release, snapshot and other third party repos. or use default coming out of the box.
4. Download spring initializer project
5. Go settings.xml under <MAVEN_INSTALL_LOCATION>\apache-maven-3.6.0\conf or C:\Users\<USER_NAME>\.m2
6. Create profiles named snapshot and release in settings.xml (can be done in pom.xml as well)
7. Add server user name and pwd in setting.xml (Encrypted recommended).
8. Edit pom.xml and add repository and snapshot repository in distribution management tag
9. Mark id should match in step 7 with server id of settings.xml
10. Run mvn clean deploy, this will publish to snapshot repo
11. Change the version from 1.0-Snapshot to 1.0
12. Run mvn clean deploy -P release, it will deploy it to release repo





To specify sonar custom settings
mvn clean sonar:sonar -Dsonar.host.url=http://192.168.56.101:9000 -Dsonar.login=admin -Dsonar.password=admin123

To get dependency tree of your project
mvn dependency:tree

To get all plugins used of your project
mvn -B dependency:resolve-plugins

To get latest version of plugin
mvn versions:display-plugin-updates

Assume you need to use different local repository
mvn install -Dmaven.repo.local=/alternate/repo/location

If you want to skip test cases
mvn clean install -Dmaven.test.skip=true 

