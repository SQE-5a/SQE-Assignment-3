# Component and Architectural level modularity requirements

Flutter is cross platform UI tool kit, which is designed in such a way that you can reuse the code 
through cross platfoems such as Android and IOS. Their main moto is to build high performance app 
that feel natural on multiple platforms.

During development, Flutter apps run in a VM that offers stateful hot reload of changes without needing a full recompile. For release, Flutter apps are compiled directly to machine code, whether Intel x64 or ARM instructions, or to JavaScript if targeting the web. The framework is open source, with a permissive BSD license, and has a thriving ecosystem of third-party packages that supplement the core library functionality.

This overview is divided into a number of sections:

The layer model: The pieces from which Flutter is constructed.
Reactive user interfaces: A core concept for Flutter user interface development.
An introduction to widgets: The fundamental building blocks of Flutter user interfaces.
The rendering process: How Flutter turns UI code into pixels.
An overview of the platform embedders: The code that lets mobile and desktop OSes execute Flutter apps.
Integrating Flutter with other code: Information about different techniques available to Flutter apps.
Support for the web: Concluding remarks about the characteristics of Flutter in a browser environment.

Flutter is designed as an extensible, layered system. It exists as a series of independent libraries that
each depend on the underlying layer. No layer has privileged access to the layer below, and every part of the
framework level is designed to be optional and replaceable.

![1](https://user-images.githubusercontent.com/105450025/204389128-9ee1134f-6588-4af2-86db-c92badabf1b5.png)

To the underlying operating system, Flutter applications are packaged in the same way as any other native application. A platform-specific embedder provides an entrypoint; coordinates with the underlying operating system for access to services like rendering surfaces, accessibility, and input; and manages the message event loop. The embedder is written in a language that is appropriate for the platform: currently Java and C++ for Android, Objective-C/Objective-C++ for iOS and macOS, and C++ for Windows and Linux. Using the embedder, Flutter code can be integrated into an existing application as a module, or the code may be the entire content of the application. Flutter includes a number of embedders for common target platforms, but other embedders also exist.

# Performance Optimization

In flutter we have following methods to optimize the app
1- Avoid state flutter widgets
2- Use const keyword.
3- Try using Async\Await.
4- Develop and display frames in 16ms
5- Avoiding rebuilding of widget in Animated Builder.
6- Decrease Application size

### Avoid State Flutter widget.

he common mistake we all make is using State Flutter widgets for Flutter App development at the beginning of development. Stateful widgets can be used if your application has a large build function and you want to rebuild.

SetState() and StatefulWidget should only be used to rebuild or update. Moreover, it is better to avoid using it in whole widgets for better Flutter performance.

### Use const keyword

onst keyword works as a constant, which is a type of Flutter widget used at a time of compilation to avoid. Const allows using multiple widgets without reducing performance. Another benefit of using const is that it avoids rebuilding whenever you use different widgets.

### Using Async

Async code is tough to upgrade, and debugging the Asynchronous code is also difficult. However, the code’s readability increases when combined with Async.


### Develop and Display Frames

The display is divided into two parts: structure and picture. Developers have 8ms for structure and another 8ms for the picture to render a 60hz display.

Always divide 16ms equally between structure and picture for better flutter performance in your application

### Avoid Rebuilding widgets

To avoid bad performance issues, you can use CounterWidget, which helps develop animation without rebuilding multiple widgets.

### Decrease Application Size

Flutter’s development tool provides an advantage of reducing the application size. With the help of Gradle, you can reduce the Flutter application size to optimize Flutter performance.
Using the packaging system introduced by Google, you can create bundles of Android applications.