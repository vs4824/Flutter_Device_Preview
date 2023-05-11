# Flutter Device Preview

Approximate how your app looks and performs on another device.

## Main features

1. Preview any device from any device

2. Change the device orientation

3. Dynamic system configuration (language, dark mode, text scaling factor, ...)

4. Freeform device with adjustable resolution and safe areas

5. Keep the application state

6. Plugin system (Screenshot, File explorer, ...)

7. Customizable plugins

## Quickstart

### Add dependency to your pubspec file 

Since Device Preview is a simple Dart package, you have to declare it as any other dependency in your pubspec.yaml file.

   ```
   dependencies:
  device_preview: <latest version>
  ```

### Add DevicePreview

Wrap your app's root widget in a DevicePreview and make sure to :

1. Set your app's useInheritedMediaQuery to true.

2. Set your app's builder to DevicePreview.appBuilder.

3. Set your app's locale to DevicePreview.locale(context).

   ```
   import 'package:device_preview/device_preview.dart';
   void main() => runApp(
   DevicePreview(
   enabled: !kReleaseMode,
   builder: (context) => MyApp(), // Wrap your app
   ),
   );
   class MyApp extends StatelessWidget {
   @override
   Widget build(BuildContext context) {
   return MaterialApp(
   useInheritedMediaQuery: true,
   locale: DevicePreview.locale(context),
   builder: DevicePreview.appBuilder,
   theme: ThemeData.light(),
   darkTheme: ThemeData.dark(),
   home: const HomePage(), 
   );
   }
   }
   ```
   
