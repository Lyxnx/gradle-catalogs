# Gradle Catalogs

This repo contains some useful gradle versions to be used as a version catalog

The `bleeding` branch receives version updates as soon as they are available. Versions can be overridden in `settings.gradle.kts` though

The `master` branch receives fewer version updates but is more stable

## Using

Version catalogs are created within the `dependencyResolutionManagement` block of the `settings.gradle.kts` file:

```kotlin
dependencyResolutionManagement {
    versionCatalogs {
        create("CATALOGNAME") {
            from(file("gradle-catalogs/libs.versions.toml"))
            // If a different version is required, it can be overridden:
            version("kotlin", "1.7.20")
        }
    }
}
```

Either clone or submodule this repository to the root of the project and reference it in `settings.gradle.kts`
