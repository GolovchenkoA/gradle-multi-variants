The project demonstrates Gradle features "variants" and "capabilities"


To see [project outgoing variants](https://docs.gradle.org/current/userguide/variant_model.html#sec:variant-visual) and capabilities execute:

```cmd
gradlew lib:outgoingVariants
```

Publishing:
```cmd
gradlew build publishToMavenLocal
```

In a consumer project update build.gradle(.kts):

```
repositories {
   mavenLocal()
   ...
}


dependencies {
   implementation("org.example:gradle-multi-variants:0.0.1-SNAPSHOT") {
      capabilities {
         requireCapability("org.example:capability-one:0.0.1-SNAPSHOT")
         //requireCapability("org.example:capability-two:0.0.1-SNAPSHOT")
      }
   }
}
```




Links:

[Understanding Gradle #17 – Feature Variants](https://www.youtube.com/watch?v=XCzyUESaBHQ)

[Understanding Gradle #11 – Capability Conflicts](https://www.youtube.com/watch?v=5g20kbbqBFk&list=PLWQK2ZdV4Yl2k2OmC_gsjDpdIBTN0qqkE&index=11)

[Understanding Gradle Module Metadata](https://docs.gradle.org/current/userguide/publishing_gradle_module_metadata.html)

[Customizing publishing](https://docs.gradle.org/current/userguide/publishing_customization.html)
