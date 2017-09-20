# android things

### 与Brillo相关

* Android Things 本质上是 Brillo 的更新+重命名
* 在 Android Things 上的开发，可以通过相同的 Android 标准开发工具完成。


### Features

整个系统只安装运行一个应用，开机自动全屏启动这一个app。
> The Android Things platform is also streamlined for single application use. System apps are not present, and your app is launched automatically on startup to immerse your users in the app experience.

不要求必须要有屏幕。
> android Things does not require a display.

Peripheral I/O 和 User-Space Drivers
> Peripheral I/O 是方便开发者访问各种 pin 的，支持各种标准：GPIO、PWM、I2C、SPI、UART。
> User-Space Drivers 可以让开发者在不改动操作系统的情况下为自己的设备提供驱动，从而让这些设备可以被 Android Framework 识别，比如各种 sensor 以及输入设备。


### references

* https://www.zhihu.com/question/53623720/answer/137180672




