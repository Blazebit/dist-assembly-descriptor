Distribution Assembly Descriptor
================================
The distribution assembly descriptor for all Blazebit Community Projects.

What is it?
===========

The Distribution Assembly Descriptor provides default configuration for Blazebit Maven builds.
 
* Include all dependencies of the project in folder libs
* Include all generated jars of the Maven build
* Include pom.xml, LINCENSE, README and NOTICE files

How to use it?
==============

Start out by adding the assembly plugin to your pom in the build/plugins section.

	<plugin>
		<groupId>org.apache.maven.plugins</groupId>
		<artifactId>maven-assembly-plugin</artifactId>
		<dependencies>
			<dependency>
				<groupId>com.blazebit</groupId>
				<artifactId>dist-assembly-descriptor</artifactId>
				<version>1.0</version>
			</dependency>
		</dependencies>
		<executions>
			<execution>
				<id>assemble-zip</id>
				<phase>package</phase>
				<goals>
					<goal>single</goal>
				</goals>
				<configuration>
					<descriptorRefs>
						<descriptorRef>dist</descriptorRef>
					</descriptorRefs>
				</configuration>
			</execution>
		</executions>
	</plugin>

When you try to build the project now, the distribution should be generated.

Licensing
=========

This distribution, as a whole, is licensed under the terms of the Apache
License, Version 2.0 (see LICENSE.txt).