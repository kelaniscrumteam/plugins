Prototype : EMDK for Android SDK to pull from build.gradle

How to pull EMDK SDK from GIT Hub to compile your application:

1. To pull from EMDK from EMDK GIT Repository, add the below URL to Project level build.gradle.

allprojects {
    repositories {
        jcenter()

        //EMDK SDK URL
        maven {
            url 'https://raw.githubusercontent.com/Zebra/emdk_lib/mvn-repo/'
        }
    }
}

2. Add the EMDK SDK as dependancy in the Module level build.gradle as shown below. Make sure to specify the version of EMDK interested in to compile your app.

dependencies {
    compile fileTree(include: ['*.jar'], dir: 'libs')

    //The below line pull the EMDK SDK from the Zebra EMDK SDK repository which is mentioned in the project level build.gradle
    //provided group:'com.symbol.emdk', name:'emdk', version:'5.0.0'
    provided group:'com.symbol.emdk', name:'emdk', version:'6.0'
}

3. Sync and rebuild project


Note: The gradle will download the EMDK jar only for the speicified version and stores locally on the your computer.
The path on Windows is:
C:\Users\<<user>>\.gradle\caches\modules-2\files-2.1\com.symbol.emdk