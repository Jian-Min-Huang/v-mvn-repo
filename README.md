# v-mvn-repo

Vincent personal maven repository hosted on GitHub repository

# upload
suppose you have another project (ex. v-util)

run these maven command for deploying artifacts to this repository

commit and push to GitHub repository
```sh
$ mvn clean deploy -DaltDeploymentRepository=release-repo::default::file:~/GitHub/v-mvn-repo/releases
$ mvn clean deploy -DaltDeploymentRepository=snapshot-repo::default::file:~/GitHub/v-mvn-repo/snapshots

$ git commit -m "message"
$ git push
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
repositories {
    maven { url "https://github.com/Jian-Min-Huang/v-mvn-repo/raw/master/releases" }
}

dependencies {
    compile group: '${group}', name: '${name}', version: '${version}'
}
```


