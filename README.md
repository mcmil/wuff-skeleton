# wuff-skeleton
Skeleton Wuff application based on e(fx)clipse. Currently this sample is running on an experimental e(fx)clipse support in Wuff. 
The code in this repository can be generated from this `build.gradle` file, by simply running `gradlew scaffold` in the same directory. 

```gradle
buildscript {
    repositories {
		jcenter()
		maven { url 'http://dl.bintray.com/mcmil/maven' }
		maven { url 'http://oss.jfrog.org/artifactory/oss-snapshot-local' }
    }

    dependencies {
        classpath 'org.akhikhl.wuff:wuff-plugin:0.0.13-efxclipse-alpha'
    }
}

apply plugin: 'org.akhikhl.wuff.efxclipse-app'

wuff {
    filterManifest = true
    selectedEclipseVersion = 'efxclipse-1.2'
}
```

After checkouting or scaffolding the project simply run: `gradlew run`

