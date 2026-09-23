# Ellice

[Deutsche Version](README.md)

<img width="1672" height="941" alt="Ellice" src="https://github.com/user-attachments/assets/e615d317-7736-4a3c-bc90-270b4eb52b57" />

The short version: the original JAR was much easier to take apart than its obfuscation suggested. Plain-text shaders, manageable number “encryption,” and an obfuscator that apparently clocked out early. 💀

The result is more useful: a normal, buildable Fabric project with readable source code and dependencies resolved entirely through Gradle.

## Requirements

- JDK 25
- Git
- An internet connection for the first Gradle run

Check your Java version first:

```shell
java -version
```

## Run in development

```shell
git clone https://github.com/IchLadeKackeHoch/ellice-buildable.git
cd ellice-buildable
```

On Windows:

```powershell
.\gradlew.bat runClient
```

On Linux or macOS:

```shell
chmod +x gradlew
./gradlew runClient
```

On the first run, Gradle downloads Minecraft, Fabric, and the required libraries. It then opens a development client whose files are stored in the `run` directory.

## Build

On Windows:

```powershell
.\gradlew.bat build
```

On Linux or macOS:

```shell
./gradlew build
```

The finished mod is written to `build/libs/ellice-1.3.0.jar`. The file containing `-sources` is only the source archive.

## Install in Minecraft

1. Install Fabric Loader `0.19.2` for Minecraft `26.1.2`.
2. Install a compatible Fabric API version.
3. Copy `build/libs/ellice-1.3.0.jar` into your Minecraft `mods` directory.
4. Start the Fabric profile.

The remaining runtime libraries are embedded during the build, so no separate `libs` directory is required.

## Setup problems

If Gradle reports the wrong Java version, `JAVA_HOME` still points to an older JDK. For incomplete downloads, refresh the dependencies:

```powershell
.\gradlew.bat --refresh-dependencies
```
