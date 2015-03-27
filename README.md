# wuff-skeleton
This project is a skeleton for an application based on e(fx)clipse. Currently this sample is running on an experimental [e(fx)clipse branch in Wuff] (https://github.com/mcmil/wuff/tree/efxclipse). 

Please note that the sample works on  Linux and Windows machines only. Java 8 is required.

There are two ways to use this skeleton:

##Out-of-the-box
Checkout the project (or download and extract the [zip](https://github.com/mcmil/wuff-skeleton/archive/master.zip) file) to a directory of your choice. In that directory, execute the  `gradlew run` command to start the application. The script will download and install gradle in that directory and, after that, it will start downloading the efxclipse update site. This is done only once and can take several minutes (normally around 3-5). 

To generate an executable `*.bat` run the `gradlew build` command. The `*.bat` will be generated in `wuff-skeleton\build\output\pl.cmil.wuff.skeleton-...` directory.

##From scratch
This approach is only valid if you already have gradle or a gradle wrapper. 

The scaffolding code in this repository can be generated from this `build.gradle` file:

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
Remember to set a constant name for the root project in `settings.gradle`, e.g.:
```
rootProject.name='pl.cmil.wuff.skeleton'
```
Without it, the project may not start when moved to another directory.

After those files are created, run  `gradle scaffold` in the same directory. I twil create an `Application.e4xmi` file, standard maven-like directory structure an a `plugin.xml`. At this point you can simply run `gradle run`

##Notes

There is a known issue with cleaning the project - the build is cleared but an error is thrown. It does not happen in a multimodular one. 

The sample can be imported to any IDE - Eclipse, IntelliJ Idea or you can stick to VIM if you like.

  

