[![Donation](https://img.shields.io/badge/donate-please-brightgreen.svg)](https://www.paypal.me/janrabe) [![About Jan Rabe](https://img.shields.io/badge/about-me-green.svg)](https://about.me/janrabe) 
# UrlShortener [![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-UrlShortener-brightgreen.svg?style=flat)](https://android-arsenal.com/details/1/4819) [![](https://jitpack.io/v/kibotu/UrlShortener.svg)](https://jitpack.io/#kibotu/UrlShortener) [![Javadoc](https://img.shields.io/badge/javadoc-SNAPSHOT-green.svg)](https://jitpack.io/com/github/kibotu/UrlShortener/master-SNAPSHOT/javadoc/index.html) [![Build Status](https://travis-ci.org/kibotu/UrlShortener.svg?branch=master)](https://travis-ci.org/kibotu/UrlShortener) [![API](https://img.shields.io/badge/API-15%2B-brightgreen.svg?style=flat)](https://android-arsenal.com/api?level=15)  [![Gradle Version](https://img.shields.io/badge/gradle-3.2.1-green.svg)](https://docs.gradle.org/current/release-notes) [![Retrolambda](https://img.shields.io/badge/java-8-green.svg)](https://github.com/evant/gradle-retrolambda) [![Licence](https://img.shields.io/badge/licence-Apache%202-blue.svg)](https://raw.githubusercontent.com/kibotu/UrlShortener/master/LICENSE)

## Introduction

Shortens url using [google shortener service](https://developers.google.com/url-shortener/).

## How to use

1) Update [Google Api Key](https://developers.google.com/url-shortener/v1/getting_started#APIKey) in your [string.xml](https://github.com/kibotu/UrlShortener/blob/master/lib/src/main/res/values/strings.xml)

       <string name="google_api_key">my-google-api-key</string>

2) [Request shortened url](https://github.com/kibotu/UrlShortener/blob/master/app/src/main/java/net/kibotu/urlshortener/app/MainActivity.java#L21-L26)

       UrlShortener.shortenUrl(this, "http://www.google.com")
                    .subscribeOn(Schedulers.newThread())
                    .observeOn(AndroidSchedulers.mainThread())
                    .subscribe(response -> {
                        Log.v(TAG, "shortened url=" + response.id);
                    }, Throwable::printStackTrace);


## How to install

    compile 'com.github.kibotu:UrlShortener:-SNAPSHOT'

## How to build

    graldew clean build
    
### CI 
    
    gradlew clean assembleRelease test javadoc
    
#### Build Requirements

- JDK7, JDK8
- Android Build Tools 25.0.1
- Android SDK 25

## Contributors

[Jan Rabe](jan.rabe@kibotu.net)

###License
<pre>
Copyright 2016 Jan Rabe

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
</pre>
