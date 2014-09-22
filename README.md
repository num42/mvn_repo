# How to use in your app

* the MVN_REPO environment variable must reference this directory (see http://stackoverflow.com/questions/135688/setting-environment-variables-in-os-x)
* in your app apply the pull.gradle file (apply from: 'https://bitbucket.org/api/1.0/repositories/dengler/mvn_repo/raw/master/pull.gradle')

# How to use if you want to publish a library

* the MVN_REPO environment variable must reference this directory (see http://stackoverflow.com/questions/135688/setting-environment-variables-in-os-x)
* in your library apply the publish.gradle file (apply from: 'https://bitbucket.org/api/1.0/repositories/dengler/mvn_repo/raw/master/publish.gradle')
* use the version field to specify your version you want to upload (see below)

def versionMajor = 0
def versionMinor = 0
def versionPatch = 1

version = "${versionMajor}.${versionMinor}.${versionPatch}"

android {
    defaultConfig {
        versionCode versionMajor * 10000 + versionMinor * 1000 + versionPatch * 100
        versionName = project.version
    }
)

* use the gradle task addArchivesToMavenRepo to add it locally
* use the gradle task publishArchives to push all local archives to the remote repository