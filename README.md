# Ellice

[English version](README_EN.md)

<img width="1672" height="941" alt="Ellice" src="https://github.com/user-attachments/assets/e615d317-7736-4a3c-bc90-270b4eb52b57" />

Die kurze Version: Die ursprüngliche JAR war deutlich leichter auseinanderzunehmen, als ihre Obfuscation vermuten ließ. Shader im Klartext, überschaubare Number-„Encryption“ und ein Obfuscator, der offenbar vor Feierabend schon Feierabend gemacht hat. 💀

Viel interessanter ist aber das Ergebnis: ein normales, buildbares Fabric-Projekt mit lesbarem Source und vollständig über Gradle aufgelösten Abhängigkeiten.

## Voraussetzungen

- JDK 25
- Git
- Internetzugang beim ersten Gradle-Lauf

Prüfe zuerst deine Java-Version:

```shell
java -version
```

## Im Entwicklungsmodus starten

```shell
git clone https://github.com/IchLadeKackeHoch/ellice-buildable.git
cd ellice-buildable
```

Unter Windows:

```powershell
.\gradlew.bat runClient
```

Unter Linux oder macOS:

```shell
chmod +x gradlew
./gradlew runClient
```

Beim ersten Start lädt Gradle Minecraft, Fabric und die benötigten Libraries. Anschließend öffnet sich ein Entwicklungs-Client. Dessen Dateien liegen im Ordner `run`.

## Bauen

Unter Windows:

```powershell
.\gradlew.bat build
```

Unter Linux oder macOS:

```shell
./gradlew build
```

Die fertige Mod liegt danach unter `build/libs/ellice-1.3.0.jar`. Die Datei mit `-sources` im Namen ist nur das Source-Archiv.

## In Minecraft verwenden

1. Installiere Fabric Loader `0.19.2` für Minecraft `26.1.2`.
2. Installiere eine passende Fabric-API-Version.
3. Kopiere `build/libs/ellice-1.3.0.jar` in deinen Minecraft-Ordner unter `mods`.
4. Starte das Fabric-Profil.

Die übrigen Laufzeitbibliotheken werden beim Build in die Mod eingebunden; ein separater `libs`-Ordner ist nicht nötig.

## Probleme beim Setup

Wenn Gradle eine falsche Java-Version meldet, zeigt `JAVA_HOME` noch auf ein älteres JDK. Bei unvollständigen Downloads hilft meist:

```powershell
.\gradlew.bat --refresh-dependencies
```
