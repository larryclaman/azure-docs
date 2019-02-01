---
title: Release Notes - Speech Services
titlesuffix: Azure Cognitive Services
description: See a running log of feature releases, improvements, bug fixes, and known issues for Azure Speech Services.
services: cognitive-services
author: wolfma61
manager: cgronlun
ms.service: cognitive-services
ms.subservice: speech-service
ms.topic: conceptual
ms.date: 12/18/2018
ms.author: wolfma
ms.custom: seodec18
---

# Release notes

## Speech SDK 1.2.0: 2018-December release

**New Features**

* Python
  * The Beta version of Python support (3.5 and above) is available with this release. For more details [see here](quickstart-python.md).
* JavaScript
  * The Speech SDK for JavaScript has been open-sourced. The source code is available on [GitHub](https://github.com/Microsoft/cognitive-services-speech-sdk-js).
  * We now support Node.js, more info can be found [here](quickstart-js-node.md).
  * The length restriction for audio sessions has been removed, reconnection will happen automatically under the cover.
* Connection Object
  * From the Recognizer you can access a Connection object. This object allows you to explicitly initiate the service connection and subscribe to connect and disconnect events.
    (This is not yet available from JavaScript and Python.)
* Support for Ubuntu 18.04.
* Android
  * Enabled ProGuard support during APK generation.

**Improvements**

* Improvements in the internal thread usage, reducing the number of threads, locks, mutexes.
* Improved error reporting / information. In several cases error messages have not been propagated all the way out.
* Updated development dependencies in JavaScript to use up-to-date modules.

**Bug fixes**

* Fixed memory leaks due to a type mismatch in RecognizeAsync.
* In some cases exceptions were being leaked.
* Fixing memory leak in translation event arguments.
* Fixed a locking issue on reconnect in long running sessions.
* Fixed an issue which could lead to missing final result for failed translations.
* C#: If an async operation wasn't awaited in the main thread, it was possible the recognizer could be disposed before the async task was completed.
* Java: Fixed a problem resulting in a crash of the Java VM.
* Objective-C: Fixed enum mapping; RecognizedIntent was returned instead of RecognizingIntent.
* JavaScript: Set default output format to 'simple' in SpeechConfig.
* JavaScript: Removing inconsistency between properties on the config object in JavaScript and other languages.

**Samples**

* Updated and fixed several samples (for example output voices for translation, etc).
* Added Node.js samples in the [sample repository](https://aka.ms/csspeech/samples).

## Speech SDK 1.1.0

**New Features**

* Support for Android x86/x64.
* Proxy Support: In the SpeechConfig object you can now call a function to set the proxy information (hostname, port, username, and password). This feature is not yet available on iOS.
* Improved error code and messages. If a recognition returned an error, this did already set `Reason` (in canceled event) or `CancellationDetails` (in recognition result) to `Error`. The canceled event now contains two additional members, `ErrorCode` and `ErrorDetails`. If the server returned additional error information with the reported error, it will now be available in the new members.

**Improvements**

* Added additional verification in the recognizer configuration, and added additional error message.
* Improved handling of long-time silence in middle of an audio file.
* NuGet package: for .NET Framework projects, it prevents building with AnyCPU configuration.

**Bug fixes**

* Fixed several exceptions found in recognizers. In addition exceptions are caught and converted into Canceled event.
* Fix a memory leak in property management.
* Fixed bug in which an audio input file could crash the recognizer.
* Fixed a bug where events could be received after a session stop event.
* Fixed some race conditions in threading.
* Fixed an iOS compatibility issue that could result in a crash.
* Stability improvements for Android microphone support.
* Fixed a bug where a recognizer in JavaScript would ignore the recognition language.
* Fixed a bug preventing setting the EndpointId (in some cases) in JavaScript.
* Changed parameter order in AddIntent in JavaScript, and added missing AddIntent JavaScript signature.

**Samples**

* Added C++ and C# samplea for pull and push stream usage in the [sample repository](https://aka.ms/csspeech/samples).

## Speech SDK 1.0.1

Reliability improvements and bug fixes:

* Fixed potential fatal error due to race condition in disposing recognizer
* Fixed potential fatal error in case of unset properties.
* Added additional error and parameter checking.
* Objective-C: Fixed possible fatal error caused by name overriding in NSString.
* Objective-C: Adjusted visibility of API
* JavaScript: Fixed regarding events and their payloads.
* Documentation improvements.

In our [sample repository](https://aka.ms/csspeech/samples), a new sample for JavaScript was added.

## Cognitive Services Speech SDK 1.0.0: 2018-September release

**New features**

* Support for Objective-C on iOS. Check out our [Objective-C quickstart for iOS](quickstart-objectivec-ios.md).
* Support for JavaScript in browser. Check out our [JavaScript quickstart](quickstart-js-browser.md).

**Breaking changes**

* With this release a number of breaking changes are introduced.
  Please check [this page](https://aka.ms/csspeech/breakingchanges_1_0_0) for details.

## Cognitive Services Speech SDK 0.6.0: 2018-August release

**New features**

* UWP apps built with the Speech SDK now can pass the Windows App Certification Kit (WACK).
  Check out the [UWP quickstart](quickstart-csharp-uwp.md).
* Support for .NET Standard 2.0 on Linux (Ubuntu 16.04 x64).
* Experimental: Support Java 8 on Windows (64-bit) and Linux (Ubuntu 16.04 x64).
  Check out the [Java Runtime Environment quickstart](quickstart-java-jre.md).

**Functional change**

* Expose additional error detail information on connection errors.

**Breaking changes**

* On Java (Android), the `SpeechFactory.configureNativePlatformBindingWithDefaultCertificate` function no longer requires a path parameter. Now the path is automatically detected on all supported platforms.
* The get-accessor of the property `EndpointUrl` in Java and C# was removed.

**Bug fixes**

* In Java, the audio synthesis result on the translation recognizer is implemented now.
* Fixed a bug that could cause inactive threads and an increased number of open and unused sockets.
* Fixed a problem, where a long-running recognition could terminate in the middle of the transmission.
* Fixed a race condition in recognizer shutdown.

## Cognitive Services Speech SDK 0.5.0: 2018-July release

**New features**

* Support Android platform (API 23: Android 6.0 Marshmallow or higher). Check out the [Android quickstart](quickstart-java-android.md).
* Support .NET Standard 2.0 on Windows. Check out the [.NET Core quickstart](quickstart-csharp-dotnetcore-windows.md).
* Experimental: Support UWP on Windows (version 1709 or later).
  * Check out the [UWP quickstart](quickstart-csharp-uwp.md).
  * Note: UWP apps built with the Speech SDK do not yet pass the Windows App Certification Kit (WACK).
* Support long-running recognition with automatic reconnection.

**Functional changes**

* `StartContinuousRecognitionAsync()` supports long-running recognition.
* The recognition result contains more fields. They're offset from the audio beginning and duration (both in ticks) of the recognized text and additional values that represent recognition status, for example, `InitialSilenceTimeout` and `InitialBabbleTimeout`.
* Support AuthorizationToken for creating factory instances.

**Breaking changes**

* Recognition events: NoMatch event type was merged into the Error event.
* SpeechOutputFormat in C# was renamed to OutputFormat to stay aligned with C++.
* The return type of some methods of the `AudioInputStream` interface changed slightly:
   * In Java, the `read` method now returns `long` instead of `int`.
   * In C#, the `Read` method now returns `uint` instead of `int`.
   * In C++, the `Read` and `GetFormat` methods now return `size_t` instead of `int`.
* C++: Instances of audio input streams now can be passed only as a `shared_ptr`.

**Bug fixes**

* Fixed incorrect return values in the result when `RecognizeAsync()` times out.
* The dependency on media foundation libraries on Windows was removed. The SDK now uses Core Audio APIs.
* Documentation fix: Added a [regions](regions.md) page to describe the supported regions.

**Known issue**

* The Speech SDK for Android doesn't report speech synthesis results for translation. This issue will be fixed in the next release.

## Cognitive Services Speech SDK 0.4.0: 2018-June release

**Functional changes**

- AudioInputStream

  A recognizer now can consume a stream as the audio source. For more information, see the related [how-to guide](how-to-use-audio-input-streams.md).

- Detailed output format

  When you create a `SpeechRecognizer`, you can request `Detailed` or `Simple` output format. The `DetailedSpeechRecognitionResult` contains a confidence score, recognized text, raw lexical form, normalized form, and normalized form with masked profanity.

**Breaking change**

- Changed to `SpeechRecognitionResult.Text` from `SpeechRecognitionResult.RecognizedText` in C#.

**Bug fixes**

- Fixed a possible callback issue in the USP layer during shutdown.

- If a recognizer consumed an audio input file, it was holding on to the file handle longer than necessary.

- Removed several deadlocks between the message pump and the recognizer.

- Fire a `NoMatch` result when the response from service is timed out.

- The media foundation libraries on Windows are delay loaded. This library is required for microphone input only.

- The upload speed for audio data is limited to about twice the original audio speed.

- On Windows, C# .NET assemblies now are strong named.

- Documentation fix: `Region` is required information to create a recognizer.

More samples have been added and are constantly being updated. For the latest set of samples, see the [Speech SDK samples GitHub repository](https://aka.ms/csspeech/samples).

## Cognitive Services Speech SDK 0.2.12733: 2018-May release

This release is the first public preview release of the Cognitive Services Speech SDK.
