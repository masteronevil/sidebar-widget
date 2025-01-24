# Sidebar_Widget

A Flutter package that provides a curated collection of custom widgets to simplify UI design and app development. With **Sidebar_Widget**, you can quickly create beautiful, reusable, and responsive user interfaces.


# Flutter Custom Sidebar

A highly customizable sidebar navigation package for Flutter applications with support for nested navigation, animations, and hover effects.

## Features

- 🎯 Customizable sidebar navigation
- 📱 Responsive design
- 🎨 Custom themes and colors
- ⚡ Smooth animations
- 🔗 Nested navigation support
- 💫 Hover effects
- 🎈 Overlay support for collapsed mode



## Installation

Add this to your package's `pubspec.yaml` file:

```yaml
dependencies:
  sidebar_widget: ^1.0.0
```

Then run:

```bash
flutter pub get
```

Import the package in your Dart code:

```dart
import 'package:sidebar_widget/sidebar_widget.dart';
```

## Example

Here's a basic example of how to use the sidebar:

```dart
import 'package:flutter/material.dart';
import 'package:sidebar_widget/sidebar_widget.dart';
import 'package:go_router/go_router.dart';
class Sidebar extends StatelessWidget {
  const Sidebar({super.key});

  @override
  Widget build(BuildContext context) {
    final path = GoRouterState.of(context).uri.path;
    return CustomSideBar(
      // currentRoute is As Web Url is current url or item provide usrl are same then it will be selected
      currentRoute: path, // optional  is this is not set then it will be not work onRouteSelected

      items: items,
      backgroundColor: Colors.black87,
      width: 250,
      // if currentRoute is not set then it will be not work onRouteSelected
      onRouteSelected: (route) {
        context.goNamed(route);
      },
    );
  }
}
    
```

```dart

final List<dynamic> items = [
 

  NavigationItem(
    title: 'item1',
    icon: Icons.dashboard,
    route: RouteNames.dashboard,
    
  ),
  // Widget 
  Divider(),
    NavigationItem(
    title: 'item2',
    icon: Icons.dashboard,
    route: '/item-route'
    // 
      navItemOnTap: () {
      print('tap')
    },
    
  ),

  NavigationItem(
    title: 'subitem1',
    icon: Icons.school,
    route: RouteNames.students,
    subItems: [
      Subitem(title: 'subitem2', route: 'RouteNames.subitem1'),
      Subitem(title: 'subitem3', icon: Icons.assignment, route: 'RouteNames.subitem2'),
    
    ],
  ),
  // next widgt 
  Container(child : Text('Widget1'))

];

```





