# Custom Expanded App Bar Behavior Using Flutter SliverAppBar

## TOC

- [Custom Expanded App Bar Behavior Using Flutter SliverAppBar](#custom-expanded-app-bar-behavior-using-flutter-sliverappbar)
  - [TOC](#toc)
  - [Introduction](#introduction)
  - [Let's Discover SliverAppBar Widget 🕵🏼](#lets-discover-sliverappbar-widget-)

## Introduction

Expanded app bar (Collapsing Toolbar) is one of the material design app bar behaviors that is widely used to hide app bar content when scrolling up. A simple use case is AppBar which might show a full profile picture when the user scrolls down and slowly transition to show only the user name when the user scrolls up.

[![Source: Material Design Guide](docs_assets/expanded-app-bar-preview.gif)](https://m2.material.io/components/app-bars-top#behavior)

In Flutter we can achieve the same behavior using [SliverAppBar](https://api.flutter.dev/flutter/material/SliverAppBar-class.html) widget. As the widget name suggests it could only be used inside [CustomScrollView](https://api.flutter.dev/flutter/widgets/CustomScrollView-class.html) widget. This widget helps you in creating various scrolling effects such as lists, grids, and expanding headers by supplying slivers (SliverAppBar, SliverList, SliverGrid ...) directly to it.

**But wait ... What the heck is sliver?** 🧐

*Sliver* is a portion of the scrollable area that is used to achieve a custom scrolling effect. It is a lower-level interface that provides excellent control over implementing a scrollable area. It is useful while scrolling large numbers of children's widgets in a scrollable area. As they are based on the viewport, they can change their shape, size, and extent based on several events and offset.

## Let's Discover SliverAppBar Widget 🕵🏼

```dart
 SliverAppBar(
            pinned: _pinned,
            snap: _snap,
            floating: _floating,
            expandedHeight: 160.0,
            flexibleSpace: const FlexibleSpaceBar(
              title: Text('SliverAppBar'),
              background: FlutterLogo(),
            ),
),
```

As we previously mentioned this widget is used directly in the CustomScrollView and it contains helpful properties to customize its behavior.

The most important properties are:

- `expandedHeight`: a double value that defines the height of the app bar when it's expanded.
- `collapsedHeight`: a double value that defines the height of the app bar when it's collapsed.
