# Ellice

Buildable Fabric mod source for Minecraft 26.1.2.

## Requirements

- JDK 25
- Git

## Run

```shell
git clone https://github.com/IchLadeKackeHoch/ellice-buildable.git
cd ellice-buildable
```

Windows:

```powershell
.\gradlew.bat runClient
```

Linux or macOS:

```shell
chmod +x gradlew
./gradlew runClient
```

Gradle downloads Minecraft, Fabric, and all required libraries automatically.

## Build

```powershell
.\gradlew.bat build
```

On Linux or macOS, use `./gradlew build`. The finished mod is written to `build/libs/ellice-1.3.0.jar`.

## Why?

The original JAR looked more protected than it was: plain-text shaders, trivial number wrapping, and an obfuscator that apparently clocked out early. This repository turns it into a normal, readable, buildable Fabric project. 💀
