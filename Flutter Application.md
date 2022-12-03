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

To the underlying operating system, Flutter applications are packaged in the same way as any other native application. A platform-specific embedder provides an entrypoint; coordinates with the underlying operating system for access to services like rendering surfaces, accessibility, and input; and manages the message event loop. The embedder is written in a language that is appropriate for the platform: currently Java and C++ for Android, Swift Objective-C/Objective-C++ for iOS and macOS, and C++ for Windows and Linux. Using the embedder, Flutter code can be integrated into an existing application as a module, or the code may be the entire content of the application. Flutter includes a number of embedders for common target platforms, but other embedders also exist.

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


# Security Requirements

Following are the sequrity requirements:

### Use code obfuscation:

Hackers can reverse engineer app code. Strings, methods, class names, and API keys can be leaked if hackers launch attacks on the application. Hackers can easily misuse the code if data is stored in plain text. You can secure Flutter apps using code obfuscation techniques that modify an app’s binary. Use the -obfuscate parameter from the Dart side to obfuscate data.


### Use Flutter jailbreak detection:

Flutter_jailbreak_detection package in Flutter helps safeguard apps against security threats from a jailbroken or rooted device.This package can be used to detect whether the app is running on a compromised device. Jailbroken or rooted devices have more privileges and enable easy installation of malware and viruses. Flutter apps with jailbreak detection use RootBeer on Android and DTTJailbreakDetection on iOS to detect if the app is running on a jailbroken or rooted device.


### Ensure Secure Network connection:

A secure network connection between mobile apps and servers is a prerequisite to ensure the protection of apps. Using a Transport Secure Layer (TSL) facilitates the secure exchange of information. Whitelisting your domain can help restrict traffic that is not secure. Implementing certificate pinning is another security best practice that will ensure all connections are secure. This prevents hackers from tampering with data in transit using illegitimate certificates.

### Use Only Necessary permissions

Applications can access hardware and native APIs through app permissions. Avoid adding plugins that contain unnecessary permission requests.

### Secure User Data

Applications sometimes may have to store sensitive data such as PII. Use the Flutter_secure_storage package when there is a need to store PII, auth token, or other sensitive data. This package uses Keystore for Android and Keychains for iOS. You can use Hive which is a Dart package to store data locally and prevent tampering.

# Reliability Requirements

Following are the reliability requirements in flutter

#### Autoscaling

Use AutoScaling wraps Scaffold, you must init AutoScale with two parameters:

baseWidth: baseWidth is your design's width, the unit is dp
child: child is Scaffold
AutoScaling(
	baseWidth: 375,
	child: Scaffold(
		...
  ),
)

In the child Widget of Scaffold，if you want to set specific size of Widget, you must use function AutoScalingSize.scaleSize() to convert size:

Container(
	width: AutoScalingSize.scaleSize(context, 375),
	height: AutoScalingSize.scaleSize(context, 25),
	color: Colors.orange,
)

#### Load Balancing

For load balancing you can use following dart package:

https://grpc.io/docs/languages/dart

#### Running on Server

Following is the simple process:
Build a flutter web: flutter build web —release
Create an instance on AWS ec2 server: mean allocate some memory for your website on the server. An instance is a virtual server in the AWS cloud.
Connect to your server(instance) with the help of putty :
Install Vesta control panel on your server.
Upload your content(website) on the server. With the help of FileZilla, you can easily upload your website content on a server.
If it’s a Firebase project you can use Firebase Hosting. It will ask you to install Firebase Tools on your system and you will have to initialize it on the root folder of your project.

#### Fault tolerance

Fault tolerance is a process that enables an operating system to respond to a failure in hardware or software. This fault-tolerance definition refers to the system’s ability to continue operating despite failures or malfunctions. An operating system that offers a solid definition for faults cannot be disrupted by a single point of failure.In the context of web application delivery, fault tolerance relates to the use of load balancing and failover solutions to ensure availability via redundancy and rapid disaster recovery. Load balancing and failover are both integral aspects of fault tolerance.


# Process Requirements

Following are the process requirements

### Flutter version management

When we work on our flutter project, we need to release the updated flutter and the app, verify it, and switch different types of SDK to test it, which takes us time for development. To avoid this, we use Flutter Version Management, which provides us with different types of Flutter versions for our machines. So that each time Flutter can test the app against the updated Flutter release without waiting for installation and will be able to switch to the Flutter version accordingly.

First of all, we need to make sure that flutter is already installed and whether the flutter is the stable channel. if not then Type the below code in your command line.

// set flutter to stable channel
flutter channel stable
// check flutter channel
flutter channel
// output
Flutter channels:
  master
  dev
  beta
* stable

After this, we have to determine whether our flutter is already installed or not, if not then first we will install FVM.
$ pub global activate fvm

### App life cycle

The life cycle depends on the state and how it changes. A stateful widget has a state so we can clarify the life cycle of flutter dependent on it. Stage of the life cycle:

createState()

initState()

didChangeDependencies()

build()

didUpdateWidget()

setState()

deactivate()

dispose()

### Open Source Contribution Requirements

Following are the steps we have to follow:

#### Step 1

Head over flutter organization on GitHub and select your concerned repository from the repository tab which has 27 repositories as of now. Flutter project on GitHub has several repositories. Some of the important repositories are as following:

Devtools
Engine
Flutter-IntelliJ
Packages
Plugins
Samples
Tests
Website

#### Step 2

Choose an issue of the type you are most experienced at or find issues labeled as ‘easy fix’, ‘good first contribution’, ‘entertaining new contributor project’, ‘documentation’, ‘d: API docs’.

#### Step 3

If you’re not sure about the solutions to an issue, you can talk to maintainers to solve the issue. You can join Flutter project’s Discord server and consult with the exact concerned person about your issue. Explore different channels there and find the one representing relevant purpose to your issue. As mentioned earlier, flutter team is readily available anytime to help you pave out from any issue you’re facing.

#### Step 4

There is an option in GitHub to fork the repository. You can clone it and do the changes to solve the issue. Keep in mind that all the changes you make will remain in your custody until you pull a request.

Moreover, if you have discovered a breaking change, you should design a document presenting the change. You should highlight the root cause, purpose of change, what problem it caused and how possibly it can be rectified.

#### Step 5

Last but not least, after you have pulled the request, wait for reviews and work on it. Once any of the maintainers find your request solid, you’ll receive an LGTM (looks good to me) comment on your PR. It will be ready to be merged into the repository. Congrats!! It’s your success.


# Documentation

Folllowing is the link of user manual
https://docs.flutter.dev/


following is the link of intallation:
https://docs.flutter.dev/get-started/install

following is the link for development 
https://flutter.dev/development


following is the link of tutorials
https://www.youtube.com/watch?v=PKDWinlLfAo&list=PLjVLYmrlmjGfGLShoW0vVX_tcyT8u1Y3E
