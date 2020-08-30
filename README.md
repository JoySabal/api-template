# MuleSoft API Project Template

This asset enables Dummy organization to implement integration uses cases for different systems, faster and easier ever before while guiding you to adopt best practices.

This API skeleton project is generated using maven archetype.

------

#### Pre-requisites

- From Anypoint Studio, access the Exchange using your Anypoint Platform credentials.
- From Anypoint Exchange window, browse api-template and download the latest version.
- From your local machine, go to API template project location.
- From the same level as api-template, create a file called archetype.properties and paste the following lines below and save the file

```
artifactId=artifactId
domain=domain
apiDescription=apiDescription
```

#### Maven archetype - create from a project

- Go to API template project directory and right click in api-template and open your Git bash
- Do a maven archetype from a project. From your Git bash under api-template directory, run below command.

```
mvn archetype:create-from-project -Darchetype.properties=../archetype.properties
```

- Go to archetype folder and do maven install. This will upload the artifact to your local .m2 repository

```
cd target/generated-sources/archetype
mvn install
```

#### Create empty packages under resources in Maven archetype

- From your Anypoint Studio, locate `archetype-metadata.xml` under `target/generated-sources/archetype/src/main/resources/META-INF/maven`
- Open `archetype-metadata.xml` and add the following lines inside `<fileSets>` and save it. This will include empty packages dwls, examples and schemas.

```
<fileSet filtered="true" encoding="UTF-8">
  <directory>src/main/resources/dwls</directory>
</fileSet>
<fileSet filtered="true" encoding="UTF-8">
      <directory>src/main/resources/examples</directory>
    </fileSet> 
    <fileSet filtered="true" encoding="UTF-8">
      <directory>src/main/resources/schemas</directory>
    </fileSet>
```

#### Maven archetype - Generate new Mule project

- Open your Git bash and make sure you are outside of your api-template project directory.
- Run below command.

```
mvn archetype:generate 
-DarchetypeGroupId=<Your Anypoint Platform Organization ID> 
-DarchetypeArtifactId=api-template-archetype
-DarchetypeVersion=1.0.0 
-Ddomain=<e.g. customers>
-DapiDescription=<It's important to surround your description with double quote if there are spaces e.g. "This API will retrieve customers details">
```

- It should run in interactive mode.

```
[INFO] Generating project in Interactive mode
[INFO] Archetype repository not defined. Using the one from [d761a7b1-1d1a-44fb-ad71-685ec9133636:api-template-archetype:1.0.0] found in catalog local
Define value for property 'groupId': com.joycompany
Define value for property 'artifactId': joy-sys-api
Define value for property 'version' 1.0-SNAPSHOT: :
Define value for property 'package' com.joycompany: :
```

- Once build successfully, import the newly created project into your Anypoint Studio.
