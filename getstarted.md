---
layout: page
title: "Getting Started"
description: ""
---
{% include JB/setup %}

<iframe width="840" height="610" src="//www.youtube.com/embed/D0TrW9ht2Qo" frameborder="0" allowfullscreen></iframe>

ND4J requires Java 7.

* First, test which version of Java you have (and whether you have it at all), by typing the following into the command line:

		java -version

* If you don't have Java 7 installed on your machine, download the [Java Development Kit (JDK) here](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html). The download will vary by operating system. For newer Macs, you'll want the file on the first line to mention Mac OS X (the number after *jdk-7u* increments with each update). It will look something like this:

		Mac OS X x64 185.94 MB -  jdk-7u67-macosx-x71.dmg

### Github

* Download Github for [Mac](https://mac.github.com/), [Windows](https://windows.github.com/), etc. Then enter this command into your terminal (Mac) or Git Shell (Windows):

      git clone https://github.com/SkymindIO/nd4j

## Maven

You can install both ND4J and Deeplearning4j separately via Maven, a build automation tool used for Java projects. Instructions to install [Maven are here](https://maven.apache.org/download.cgi). 

To see if Maven is on your machine, enter the following into the command line:

		mvn --version

If you don't have it, then download the compressed file containing Maven's latest stable version, following the instructions that pertain to your operating system; e.g. *"Unix-based Operating Systems (Linux, Solaris and Mac OS X)."* 

Maven installations of third-party software like ours require you to: 

You can install both ND4J and Deeplearning4j separately via [Maven](https://maven.apache.org/download.cgi), a build automation tool used for Java projects. Using Maven to install other software requires you to: 

* Go to your root directory; e.g. nd4j or deeplearning4j.
* Make sure the pom.xml files within that directory and each major subdirectory are properly configured. 
* Add dependencies and other information to that POM file (see below).
* Choose your IDE -- [Eclipse](http://books.sonatype.com/m2eclipse-book/reference/creating-sect-importing-projects.html), [IntelliJ](https://www.jetbrains.com/idea/help/importing-project-from-maven-model.html) or [Netbeans](http://wiki.netbeans.org/MavenBestPractices) -- and import the ND4J project via Maven.

###Dependencies

For your POM, you need to specify two dependencies, which are detailed in the [Readme](https://github.com/SkymindIO/nd4j/blob/master/README.md). 

The API, for one:

	 <dependency>
	   <groupId>org.nd4j</groupId>
	   <artifactId>nd4j-api</artifactId>
	   <version>${nd4j.version}</version>
	 </dependency>

You can copy all the dependencies from [one text file](../pomtext.txt), paste them into your POM, and simply comment them in or out.

ND4J-API is the core implementation that handles most of the interop. You'll also need to specify a backend dependency. 

ND4J supports several backends, ranging from Cuda to different native implementations. While there are several Blas implementations on the JVM, none of them support a Matlab/Numpy-like interface, so we had to make one. 

See our [downloads](http://nd4j.org/downloads.html) page for a more thorough explanation on the backends available.
    
### Jblas

	 <dependency>
	   <groupId>org.nd4j</groupId>
	   <artifactId>nd4j-jblas</artifactId>
	   <version>${nd4j.version}</version>
	 </dependency>
  
### Netlib Blas
 
	 <dependency>
	   <groupId>org.nd4j</groupId>
	   <artifactId>nd4j-api</artifactId>
	   <version>${nd4j.version}</version>
	 </dependency>

### Jcublas (Cuda/GPUs)

	 <dependency>
	   <groupId>org.nd4j</groupId>
	   <artifactId>nd4j-jcublas</artifactId>
	   <version>${nd4j.version}</version>
	 </dependency>

## Bypassing Maven With Downloads

See our [downloads](http://nd4j.org/downloads.html) page.

You can then manually import the jar files in to [Eclipse](http://stackoverflow.com/questions/3280353/how-to-import-a-jar-in-eclipse), [Intellij](http://stackoverflow.com/questions/1051640/correct-way-to-add-lib-jar-to-an-intellij-idea-project) or [Netbeans](http://gpraveenkumar.wordpress.com/2009/06/17/abc-to-import-a-jar-file-in-netbeans-6-5/).

## Working with Source (Github)

If you want to develop for ND4J, just *git clone* the software and run this Maven command within the ND4J directory:

    mvn clean install -DskipTests -Dmaven.javadoc.skip=true

## Next Steps

Now you're ready to run the examples cited in our [documentation](../elementwise.html).

Here's our [Github repo](https://github.com/SkymindIO/nd4j). You can access the core through [Maven](http://maven.apache.org/download.cgi).