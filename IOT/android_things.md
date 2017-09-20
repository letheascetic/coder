# android things

### Overview

> Apps for embedded devices bring developers closer to hardware peripherals and drivers than phones and tablets. In addition, embedded devices typically present a single app experience to users.
> Android Things extends the core Android framework with additional APIs provided by the Things Support Library. These APIs allow apps to integrate with new types of hardware not found on mobile devices.
> The Android Things platform is also streamlined for single application use. System apps are not present, and your app is launched automatically on startup to immerse your users in the app experience.


### Things Support Library

Peripheral I/O API

> 方便开发者访问各种 pin 的，支持各种标准：GPIO、PWM、I2C、SPI、UART。

User Driver API

> 可以让开发者在不改动操作系统的情况下为自己的设备提供驱动，从而让这些设备可以被 Android Framework 识别，比如各种 sensor 以及输入设备。


### Behavior Changes

Core application packages

> Android Things doesn't include the standard suite of system apps and content providers.

Displays are optional

> In graphical mode, the application window occupies the full real estate of the display. Android Things does not include the system status bar or navigation buttons, giving applications full control over the visual user experience.
> On devices where a graphical display is not present, activities are still a primary component of your Android Things app.

Home activity support

> Android Things expects one application to expose a "home activity" in its manifest as the main entry point for the system to automatically launch on boot.

Support for Google services

> Android Things supports a subset of the Google APIs for Android.
> As a general rule, APIs that require user input or authentication credentials aren't available to apps.

Cloud IoT Core

> a fully managed service that allows you to easily and securely connect, manage, and ingest data from millions of globally dispersed devices. Cloud IoT Core, in combination with other services on Google Cloud IoT platform, provides a complete solution for collecting, processing, analyzing, and visualizing IoT data in real time to support improved operational efficiency.

Permissions

> Declare permissions that you need in your app's manifest file. Normal permissions are granted at install time. Dangerous permissions are granted on the next device reboot and do not require run time checks. This applies to new app installs and updated <uses-permission> elements in existing apps.

Notifications

> Since there is no system-wide status bar and window shade in Android Things, notifications are not supported.



### references

* https://developer.android.google.cn/things/sdk/index.html
* https://www.zhihu.com/question/53623720/answer/137180672





