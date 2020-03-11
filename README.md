# bintray
bintray help gradle

## Pre
先阅读这篇文章，名单jcenter是什么和如何注册账号
https://inthecheesefactory.com/blog/how-to-upload-library-to-jcenter-maven-central-as-dependency/en


## Java Configuration

在根目录的build.gradle添加依赖
```Groovy
classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.8.4'
```

在local.properties里添加bintray配置
```Groovy
bintray.user=
bintray.key=
bintray.gpg.password=
```

在项目的build.gradle添加配置

```Groovy
ext {
    GROUP_ID = ''
    ARTIFACT_ID = ""
    ARTIFACT_VERSION = version

    DEVELOPER_ID = 'forkliu'
    DEVELOPER_NAME = 'Liu Jun'
    DEVELOPER_EMAIL = 'liujun@forkliu.com'

    PROJECT_URL = 'https://github.com/vforkliu/LearnGradle'
    PROJECT_NAME = 'Venus Math Library'
    PROJECT_DESC = 'This is a simple math library'
    SCM_URL = 'https://github.com/vforkliu/LearnGradle.git'

    BINTRAY_VERSION_DESC = 'Some small change'
    BINTRAY_REPO = 'forkliu'
    BINTRAY_NAME = ARTIFACT_ID
}

apply from: "https://github.com/vforkliu/bintray/raw/master/bintray-java.gradle"
```

## Android Library
```Groovy
ext {
    GROUP_ID = group
    ARTIFACT_ID = "venus-base"
    ARTIFACT_VERSION = version

    DEVELOPER_ID = 'forkliu'
    DEVELOPER_NAME = 'Liu Jun'
    DEVELOPER_EMAIL = 'liujun@forkliu.com'

    PROJECT_URL = 'https://github.com/vforkliu/LearnGradle'
    PROJECT_NAME = 'Venus Base Library'
    PROJECT_DESC = 'This is a base code library'
    SCM_URL = 'https://github.com/vforkliu/LearnGradle.git'

    BINTRAY_VERSION_DESC = 'Some small changge'
    BINTRAY_REPO = 'forkliu'
    BINTRAY_NAME = ARTIFACT_ID
}
apply from: "https://github.com/vforkliu/bintray/raw/master/bintray-android.gradle"
```
