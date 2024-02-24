This is an opinionated template for creating kotlin multi platform library projects.

This works for me and might help you bootstrap your kotlin projects.

## Batteries included

- Gradle wrapper
- [Refresh versions plugin](https://splitties.github.io/refreshVersions/) - Great way to manage dependencies.
- [kotlin4example](https://github.com/jillesvangurp/kotlin4example) integrated to generate the readme and any other documentation you are going to write. This is all driven via the tests.
- Some dependencies for testing (junit, kotest-assertions, etc.) and test setup for junit
- generic publish script that tags and publishes 
- Github action that builds your stuff generated using [github-workflows-kt](https://github.com/typesafegithub/github-workflows-kt). Setup to cache gradle and konan related files to speed up your builds.
- LICENSE file (MIT)

## Gradle

This library is published to our own maven repository.

```kotlin
repositories {
    mavenCentral()
    maven("https://maven.tryformation.com/releases") {
        // optional but it speeds up the gradle dependency resolution
        content {
            includeGroup("com.jillesvangurp")
            includeGroup("com.tryformation")
        }
    }
}
```

And then you can add the dependency:

```kotlin
    // check the latest release tag for the latest version
    implementation("com.jillesvangurp:json-dsl:1.x.y")
```
