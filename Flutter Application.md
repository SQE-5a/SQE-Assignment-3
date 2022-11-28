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


