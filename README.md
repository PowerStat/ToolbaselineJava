# PowerStat's Toolbaseline for Java

This is my [ToolbaselineJava](https://www.powerstat.de/ToolbaselineJava.html).

## Installation

Because this library is only useful for developers the installation depends on your build environment.

For example when using Apache Maven you could add the following dependency to your project:

    <dependency>
      <groupId>de.powerstat.toolbaseline</groupId>
      <artifactId>tbljava</artifactId>
      <version>17.2.0</version>
    </dependency>

Also please copy the `checkstyle-config.xml` and `PMD.xml` into your project.
Please add the following entry to your maven `settings.xml`:

    <server>
      <id>nvd</id>
      <password>nvd api-key</password>
    </server>

The API-Key could be requested here: [National Vulnerability Database](https://nvd.nist.gov/developers/request-an-api-key)


Other build tools like gradle will work analogous.

To compile this project yourself you could use:

    mvn clean install site
    
or simply:

     mvn clean install

or for native image creation:

On windows Visual Studio 2022 is required and you have to call:

    "C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Auxiliary\Build\vcvars64.bat" > nul

Compile and build image:

    mvn clean -Pnative package
    
Run the image:

    ./target/[imagename]

To find newer dependencies:

    mvn versions:display-dependency-updates
    
To find newer plugins:

    mvn versions:display-plugin-updates
    
To make a new release:

    set MAVEN_GPG_PASSPHRASE=TopSecret
    mvn --batch-mode release:clean release:prepare release:perform
    git push -–tags
    git push origin master
        
To run toolchain:

    mvn toolchains:toolchain
    
If you use a sonar server:

    mvn sonar:sonar -Dsonar.token=<token>


## Usage

For usage in your own projects please read the Doc's.

## Contributing

If you would like to contribute to this project please read [How to contribute](CONTRIBUTING.md).

## License

This code is licensed under the [Apache License Version 2.0](LICENSE.md).
