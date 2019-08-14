# GDG Pune DevFest App [![Build Status](https://travis-ci.org/PatilShreyas/GDG-Pune-DevFest-App.svg?branch=master)](https://travis-ci.org/PatilShreyas/GDG-Pune-DevFest-App) [![Codemagic build status](https://api.codemagic.io/apps/5d541cd5bab5d9000f119d02/5d541cd5bab5d9000f119d01/status_badge.svg)](https://codemagic.io/apps/5d541cd5bab5d9000f119d02/5d541cd5bab5d9000f119d01/latest_build)

<p align="center">
<img width="800px"  src="https://i.imgur.com/P21Hk0u.png">
</p>

## Overview
This is official app for event DevFest 2019 organised by GDG Pune (Google Developers Group).

## Technology Stack

- Flutter
- Flutter Bloc
- Firebase (Upcoming)

## Getting Started

1. [Fork repository](https://github.com/iampawan/GDG-DevFest-App/fork) and clone your fork locally
1. Install [Flutter 1.7.8](https://flutter.dev/docs/get-started/install)
1. Install [Android Studio / IntelliJ / VSCode](https://flutter.dev/docs/development/tools/android-studio)
1. [Preparing Release for Android](https://flutter.dev/docs/deployment/android)
1. [Preparing Release for iOS](https://flutter.dev/docs/deployment/ios)

## Building the project

### Missing Key.Properties file

If you try to build the project straight away, you'll get an error complaining that a `key.properties` file is missing and Exit code 1 from: /GDG-DevFest-App-master/android/gradlew app:properties:. To resolve that,

1.  Open [GDG-DevFest-App-master\android\app\build.gradle](https://github.com/iampawan/GDG-DevFest-App/blob/master/android/app/build.gradle) file and comment following lines-

    ```
    //keystoreProperties.load(new FileInputStream(keystorePropertiesFile))

    signingConfigs {
    // release {
    // keyAlias keystoreProperties['keyAlias']
    // keyPassword keystoreProperties['keyPassword']
    // storeFile file(keystoreProperties['storeFile'])
    // storePassword keystoreProperties['storePassword']
    // }
    }
    buildTypes {
    // release {
    // signingConfig signingConfigs.release
    // }
    }
    ```

1.  Open [GDG-DevFest-App-master\lib\utils\devfest.dart](https://github.com/iampawan/GDG-DevFest-App/blob/master/lib/utils/devfest.dart) file and customise the texts according to your needs. Eg-

    ```
        static const String app_name = “Devfest”;
        static const String app_version = “Version 1.0.0”;
        static const int app_version_code = 1;

        //*  Texts
        static const String welcomeText = “Welcome to GDG DevFest”;
        static const String descText =
            ‘’’DevFests are community-led, developer events hosted by GDG chapters around the globe focused on community building & learning about Google’s technologies. Each DevFest is inspired by and uniquely tailored to the needs of the developer community and region that hosts it.’’’;

        //* ActionTexts
        static const String agenda_text = “Agenda”;
        static const String speakers_text = “Speakers”;
        static const String team_text = “Team”;
        static const String sponsor_text = “Sponsors”;
        static const String faq_text = “FAQ”;
        static const String map_text = “Locate Us”;
    ```

1.  Open [GDG-DevFest-App-master\lib\home\session.dart](https://github.com/iampawan/GDG-DevFest-App/blob/master/lib/home/session.dart) file and customise the sessions according to your needs. Eg-

    ```
        List<Session> sessions = [
            Session(
                sessionId: “1”,
                sessionStartTime: “9:00 AM”,
                sessionTotalTime: “30 Mins”,
                sessionTitle: “DevByte: From Zero to ML on Google Cloud Platform”,
                speakerImage:
                    “https://avatars1.githubusercontent.com/u/12619420?s=400&u=eac38b075e4e4463edfb0f0a8972825cf7803d4c&v=4”,
                speakerName: “Max Saltonstall”,
                speakerDesc: “Cloud Developer Advocate, Google DevByte speaker”,
                track: "cloud"
            ),
        ]
    ```

1.  Open [GDG-DevFest-App-master\lib\home\speaker.dart](https://github.com/iampawan/GDG-DevFest-App/blob/master/lib/home/speaker.dart) file and customise the speakers according to your needs. Eg-

    ```
        List<Speaker> speakers = [
            Speaker(
                speakerImage:
                    “https://avatars1.githubusercontent.com/u/12619420?s=400&u=eac38b075e4e4463edfb0f0a8972825cf7803d4c&v=4”,
                speakerName: “Pawan Kumar”,
                speakerDesc: “Google Developer Expert, Flutter”,
                speakerSession: “Talk: Getting Started With Flutter For Web”,
                fbUrl: “https://facebook.com/imthepk”,
                githubUrl: “https://github.com/iampawan”,
                linkedinUrl: “https://linkedin.com/in/imthepk”,
                twitterUrl: “https://twitter.com/imthepk”,
            ),
        ]
    ```

1.  Open [GDG-DevFest-App-master\lib\home\team.dart](https://github.com/iampawan/GDG-DevFest-App/blob/master/lib/home/team.dart) file and customise the teams according to your needs. Eg-

    ```
        List<Team> teams = [
            Team(
                name: “Sundar Pichai”,
                desc: “Organizer”,
                contribution: “Google CEO”,
                image:
                    “https://pbs.twimg.com/profile_images/864282616597405701/M-FEJMZ0_400x400.jpg”,
            ),
        ]
    ```

1.  Open [GDG-DevFest-App-master\lib\map\map_page.dart](https://github.com/iampawan/GDG-DevFest-App/blob/master/lib/map/map_page.dart) file and customise the lat long according to your needs. Eg-

    ```
       static final LatLng myLocation = LatLng(37.42796133580664,       -122.085749655962);
    ```

1.  Open [GDG-DevFest-App-master\lib\sponsors\sponsor_page.dart](https://github.com/iampawan/GDG-DevFest-App/blob/master/lib/sponsors/sponsor_page.dart) file and customise the sponsors data according to your needs. Eg-

    ```
       SponsorImage(
            imgUrl: “https://devfest.gdgkolkata.org/assets/img/logos/gd.png”,
        )
    ```

## Contributing

Awesome! Contributions of all kinds are greatly appreciated. To help smoothen the process we have a few non-exhaustive guidelines to follow which should get you going in no time.

### Using GitHub Issues

- Feel free to use GitHub issues for questions, bug reports, and feature requests
- Use the search feature to check for an existing issue
- Include as much information as possible and provide any relevant resources (Eg. screenshots)
- For bug reports ensure you have a reproducible test case
  - A pull request with a breaking test would be super preferable here but isn't required

## Credits
[Pawan Kumar](https://github.com/iampawan)
