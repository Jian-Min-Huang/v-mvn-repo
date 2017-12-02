# v-mvn-repo 

# upload
suppose you have another project (ex. v-util)

run these maven command for uploading artifacts to this repository
```sh
$ mvn clean deploy -DaltDeploymentRepository=release-repo::default::file:~/GitHub/v-mvn-repo/releases
$ mvn clean deploy -DaltDeploymentRepository=snapshot-repo::default::file:~/GitHub/v-mvn-repo/snapshots
```

# import artifact in other project
Add following block in your pom.xml

* maven
```xml
<repositories>
	<repository>
		<id>release-repo</id>
		<url>https://github.com/Jian-Min-Huang/v-mvn-repo/raw/master/releases</url>
	</repository>
</repositories>


<dependencies>
	<dependency>
		<groupId>${groupId}</groupId>
		<artifactId>${artifactId}</artifactId>
		<version>${version}</version>
	</dependency>
</dependencies>
```

* gradle
```groovy

```


