Letter
===========

Medium performance Paper fork that aims to not [hang](https://github.com/PaperMC/Paper/issues/5980) by disabling async chunks while still providing the Paper API.


**Support and Project Discussion:**
None
 

How To (Server Admins)
------
Build from source. Letterclip isn't a thing yet :<

  * Documentation on using Letter (identical to Paper): [paper.readthedocs.io](https://paper.readthedocs.io/)

How To (Plugin Developers)
------
 * See our API patches [here](patches/api)
 * Chunk priority patch removed until [this issue is fixed](https://github.com/PaperMC/Paper/issues/5980)
 * Letter API javadocs here: [tildearrow.org/letterdocs](https://tildearrow.org/letterdocs/)
 * Maven Repo (for paper-api) (should be compatible):
```xml
<repository>
    <id>papermc</id>
    <url>https://papermc.io/repo/repository/maven-public/</url>
</repository>
```
 * Artifact Information:
```xml
<dependency>
    <groupId>io.papermc.paper</groupId>
    <artifactId>paper-api</artifactId>
    <version>1.17.1-R0.1-SNAPSHOT</version>
    <scope>provided</scope>
</dependency>
 ```

**Or alternatively, with Gradle:**

 * Repository:
```groovy
repositories {
    maven {
        url 'https://papermc.io/repo/repository/maven-public/'
    }
}
```
 * Artifact:
```groovy
dependencies {
    compileOnly 'io.papermc.paper:paper-api:1.17.1-R0.1-SNAPSHOT'
}
```

How To (Compiling Jar From Source)
------
To compile Letter, you need JDK 16 and an internet connection.

Clone this repo, run `./gradlew applyPatches`, then `./gradlew reobfJar` from your terminal. You can find the compiled jar in the `Paper-Server/build/libs` directory.

To get a full list of tasks, run `./gradlew tasks`.

How To (Pull Request)
------
Issue pull requests on the official Paper project. This fork is merely an interim workaround for 5980.

Special Thanks To:
-------------

**Primorior**

for finding the issue, and consistently reporting no improvement despite updating.

**Brokkonaut**

for investigating the issue and determining the potential root cause.

**All reporters involved in** [the bug report](https://github.com/PaperMC/Paper/issues/5980)

including countless duplicates and comments in efforts to bring the bug report to attention.

**PaperMC team**

for the server software. Spigot is a headache.
PlayerDeathEvent cancellation, PlayerAdvancementCriterionGrantEvent and EntityKnockbackByEntityEvent are a godsend.

No Thanks To:
-------------

**electronicboy**

for partially dismissing the issue, closing bug reports and not listening to users.

**mechoriet**

for the buggy [patch](https://github.com/PaperMC/Paper/pull/5829)

**PaperMC team**

for not marking the issue as **we must go deeper** despite it being a critical top-priority difficult bug.
