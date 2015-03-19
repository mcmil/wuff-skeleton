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
        classpath 'org.akhikhl.wuff:wuff-plugin:0.0.13-efxclipse-alpha2'
    }
}

apply plugin: 'org.akhikhl.wuff.efxclipse-app'

wuff {
    filterManifest = true
    selectedEclipseVersion = 'efxclipse-1.2'
}
```

After checkouting or scaffolding the project simply run: `gradlew run`. To generate an executable `*.bat` run the `gradlew build` command. The `*.bat` will be generated in `wuff-skeleton\build\output\pl.cmil.wuff.skeleton-...` directory.

Remember to set a constant name for the root project in `settings.gradle`, e.g.:
```
rootProject.name='pl.cmil.wuff.skeleton'
```
Without it, the project may not start when moved to another directory.

  

