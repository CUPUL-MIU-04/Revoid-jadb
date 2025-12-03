# JADB - ReVoid Fork #
ADB client implemented in pure Java. **Fork maintained by ReVoid project**.

The Android Debug Bridge (ADB) is a client-server architecture used to communicate with Android devices (install APKs, debug apps, etc).

The Android SDK Tools are available for the major platforms (Mac, Windows & Linux) and include the `adb` command line tool which implements the ADB protocol.

This fork of JADB is maintained by the ReVoid project team with custom modifications and improvements.

![Build Status](https://github.com/CUPUL-MIU-04/Revoid-jadb/actions/workflows/maven.yml/badge.svg)
[![GitHub Packages](https://img.shields.io/badge/GitHub-Packages-blue?logo=github)](https://github.com/CUPUL-MIU-04/Revoid-jadb/packages)
[![Java Version](https://img.shields.io/badge/Java-11%2B-orange)](https://openjdk.org/)
[![License](https://img.shields.io/badge/License-Apache%202.0-green.svg)](https://opensource.org/licenses/Apache-2.0)

## Original Project ##
This is a fork of the original JADB project by [vidstige](https://github.com/vidstige/jadb). 
Original source code and documentation available at: https://github.com/vidstige/jadb

## Features in this Fork ##
- Custom modifications for ReVoid project requirements
- GitHub Packages integration for Maven distribution
- Continuous integration via GitHub Actions
- Backward compatible with original JADB API

## Example ##
Usage cannot be simpler. Just create a `JadbConnection` and off you go.

```java
JadbConnection jadb = new JadbConnection();
List<JadbDevice> devices = jadb.getDevices();
```

Make sure the adb server is running. You can start it by running adb once from the command line.

It's very easy to send and receive files from your android device, for example as below.

```java
JadbDevice device = ...
device.pull(new RemoteFile("/path/to/file.txt"), new File("file.txt"));
```

Some high level operations such as installing and uninstalling packages are also available.

```java
JadbDevice device = ...
new PackageManager(device).install(new File("/path/to/my.apk"));
```

Using in your Maven project

Add GitHub Packages repository and dependency to your pom.xml:

```xml
<repositories>
    <repository>
        <id>github</id>
        <name>GitHub Packages</name>
        <url>https://maven.pkg.github.com/CUPUL-MIU-04/Revoid-jadb</url>
    </repository>
</repositories>

<dependencies>
    <dependency>
        <groupId>com.revoid</groupId>
        <artifactId>jadb</artifactId>
        <version>1.2.1.2</version>
    </dependency>
</dependencies>
```

Authentication

For GitHub Packages authentication, you need to:

1. Generate a GitHub Personal Access Token with read:packages scope
2. Add to your Maven settings.xml:

```xml
<servers>
    <server>
        <id>github</id>
        <username>YOUR_GITHUB_USERNAME</username>
        <password>YOUR_GITHUB_TOKEN</password>
    </server>
</servers>
```

Development

Building from source

```bash
# Clone the repository
git clone https://github.com/CUPUL-MIU-04/Revoid-jadb.git
cd Revoid-jadb

# Build the project
mvn clean install

# Run tests
mvn test
```

Publishing

The project uses GitHub Actions for CI/CD. Every push to main branch triggers:

1. Automatic versioning
2. Build and test execution
3. Deployment to GitHub Packages

Troubleshooting

If you cannot connect to your device check the following.

· Your adb server is running by issuing adb start-server
· You can see the device using adb adb devices

If you see the device in adb but not in jadb please file an issue on https://github.com/CUPUL-MIU-04/Revoid-jadb/issues.

Workaround for Unix Sockets Adb Server

Install socat and issue the following to forward port 5037 to the unix domain socket.

```bash
socat TCP-LISTEN:5037,reuseaddr,fork UNIX-CONNECT:/tmp/5037
```

Contributing

This fork is maintained by the ReVoid team. Contributions are welcome!
Please read throughCONTRIBUTING.md for guidelines.

License

This project is released under the Apache License Version 2.0, see LICENSE.md for more information.

Acknowledgements

· Original JADB project by Samuel Carlsson
· All contributors to the original project
· ReVoid project team for maintaining this fork
