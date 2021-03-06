![Oddworks](http://s3-us-west-2.amazonaws.com/odd-networks-assets/odd-networks.png)

[![Build Status](https://travis-ci.org/oddnetworks/oddworks.svg?branch=master)](https://travis-ci.org/oddnetworks/oddworks)

__Oddworks__ is an open source video distribution platform built to destroy the barriers to streaming television. Use it to:

* Deliver your video content to TV connected devices like Apple TV and Roku.
* Proxy, cache, and bend the space time continuum between your content management system and existing online video platform (Vimeo, YouTube, Ooyala, Brightcove).
* Aggregate usage metrics from your video apps to expand viewership and create custom viewing experiences.
* Distribute content from multiple sources out to your social channels.

_Become your own video distribution channel!_

## Table of contents

* [Platform](#platform)
* [Content Server](#content-server)
* [Device SDKs](#device-sdks)
* [Technology](#technology)
* [Versioning](#versioning)
* [Motivation](#motivation)
* [Community](#community)
* [License](#license)

## Platform
The Oddworks Platform consists of two main concepts:

1. The __Oddworks Content Server__ which maintains a database of your content and provides it to your apps via a strictly specified [JSON API](http://jsonapi.org/).
2. The __Oddworks Device SDKs__ which are designed to consume the content from the Oddworks Content Server as well as report usage data back to it.

## Content Server
The Oddworks Content Server is made up of several loosely coupled components:

* [seneca-odd-catalog](https://github.com/oddnetworks/seneca-odd-catalog) To handle general get, create, and update operations on your published content.
* [seneca-odd-auth](https://github.com/oddnetworks/seneca-odd-auth) Used to compartmentalize the device linking and authentication logic.
* [seneca-odd-identity](https://github.com/oddnetworks/seneca-odd-identity) Provides get, create, and update operations for identity and authentication resources.
* [seneca-odd-views](https://github.com/oddnetworks/seneca-odd-views) A flexible module for building and caching structured views for your apps.
* [odd-schemas](https://github.com/oddnetworks/odd-schemas) Used to type check incoming data entities.
* __Oddworks__ Content Server (you are here)

All of these components are automatically installed as dependencies when you setup the Oddworks Content Server. Oddworks uses [NPM](https://www.npmjs.com/) for dependency and package management (see [Technology](#technology) below).

## Device SDKs

* [Apple iOS & tvOS SDK](https://github.com/oddnetworks/oddworks-ios-tvos-sdk) Used for iPhone, iPad, and Apple TV.
* [Android SDK](https://github.com/oddnetworks/oddworks-android-sdk) Used for mobile, tablet, Android TV, and Fire TV.

Coming soon:

* Roku SDK
* JavaScript SDK for use in [Windows Universal](https://msdn.microsoft.com/en-us/windows/uwp/get-started/universal-application-platform-guide) and web applications.

In addition to the SDKs there are plans to have open source sample apps which leverage the SDKs available to you as well. You could use these as reference implementations, a hobby project, or make some tweaks and ship your own streaming channel!

Although the source repositories are not open source yet there are some [downloads available now](https://www.oddnetworks.com/documentation/sampleapps/) from the website.

## Technology

The Oddworks Platform is written for the [Node.js](https://nodejs.org/) runtime, and uses the well known [Express.js](http://expressjs.com/) framework for HTTP communication.

Oddworks is designed to be database agnostic so long as the underlying database can support JSON document storage, including some RDMSs like PostgreSQL. Currently the only supported and tested database is MongoDB.

Although communication between the devices and the REST API is typically done in a synchronous way, the inner guts of the system is designed to communicate via asynchronous message passing. This makes it easier to extend the platform with plugins and other loosely coupled modules without worrying about upstream changes like you would in tightly coupled platforms.

## Versioning

For transparency into our release cycle and in striving to maintain backward compatibility, Oddworks is maintained under [the Semantic Versioning guidelines](http://semver.org/).

## Motivation

The Oddworks Platform was designed and developed by [Odd Networks](https://www.oddnetworks.com/) to lower the barrier for developers and content owners to create your own streaming content network. Based on our experience in video gaming we thought that TV could use a big improvement. We believe in the future of television and, with the Oddworks open source platform, we hope you'll make that future a reality.

We proudly stand behind our open source work and, in addition to maintaining the Oddworks project, Odd Networks also provides hosted services, a Pro Dashboard, a Live Stream Generator, and a Recommendation Service.

Check out [www.oddnetworks.com](https://www.oddnetworks.com/)

## Community

Get updates on Odd Network's development and chat with the project maintainers and community members.

* Follow [@oddnetworks on Twitter](https://twitter.com/OddNetworks).
* Join [the official Slack room](http://slack.oddnetworks.com/).
* Submit an [issue](https://github.com/oddnetworks/oddworks/issues).
* Check out the [API sample responses](https://www.oddnetworks.com/documentation/oddworks/).
* Read and subscribe to [The Official Odd Networks Blog](http://blog.oddnetworks.com/).

## License

Apache 2.0 © [Odd Networks](http://oddnetworks.com)
