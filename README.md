# Maven
This repository covers Maven basics.

Maven Terminology
-----------------
1. archetype
2. groupId
3. artifactId
4. packaging

**archetype: It represent what type of project we want to create.**
1. maven-archetype-QuickStart: It represent java standalone application.
2. maven-archetype-webapp: It represent java web application.
Note: maven providing 1500+ archtype

**groupId: It represent company name or project name.**

**artifactId: It represent project name or project module name.**

**packaging: It represent how we want to package our java application (jar or war).**

Create standalone application using Maven:
------------------------------------------
mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.5


Create Web Application using Maven:
-----------------------------------
mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-webapp -DarchetypeVersion=1.5

Note:
SNAPSHOT = UNDER PRODUCTION
RELEASE = DEPLOY

How Maven will download dependencies
------------------------------------
Maven will download dependencies using repository.
In maven we have 3 types of repositories
1. **Central Repository:** Central repo is maintaining by Apache Organization.
2. **Remote Repository:** Every company will maintain their own remote repository.
3. **Local Repository:** Local repo will be created in our system (Location /home/ec2-user/.M2)

* When we add dependencies in pom.xml, maven will search for that dependencies in local repo. If it is availale it will add to project build path.
* If dependencies not available in local repo then maven will connect to central repo or remote repo based on our configuration.

--------------------------------------------------
Note: By default maven will connect with central repo. If we want to use remote repo then we need to configure remote repo details.

Note: Every software company will maintain their own remote repo (Ex. JFrog)


Maven Goals:
------------
To perform project build activities maven provided serveral goals.
1. Clean
2. Compile
3. Test
4. Package
5. Install
-------------------------------------------------------------------------------------------------------------------------
1. Clean goal is used to delete target folder maven.
2. Compile goal is used to compile project source code. Compiled code will stored in traget folder. 
3. Test goal is used to execute unit test code of our application based on packaging type available in pom.xml.
3. Package goal is used to generate jar or war file for our application based on packaging type available in pom.xml file.
4. Install goal is used to install our project as dependency in maven local repo.

Note: Every maven goal is associated with maven plugin. When we execute maven goal then respective maven plugin will execute to perform the operation.

Note: jar or war file will created in target folder.



