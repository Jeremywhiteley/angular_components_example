These packages provide code generation for the AngularDart Components gallery.

* **[See the gallery](https://dart-lang.github.io/angular_components_example/)**
* [Use the package](https://pub.dartlang.org/packages/angular_components)
* [Browse the API](https://www.dartdocs.org/documentation/angular_components/latest)

This is repo now contains the initial release of two new experimental code 
generating packages.

## `angular_gallery`

A package that generates a the gallery from each page that is generated by the 
`angular_gallery_section` package.

## `angular_gallery_section` 

A package that generates a gallery page containing documentation and examples 
from a `@GallerySectionConfig` annotation.

## `example` 
Contains individual examples for all the components as well as the base package
of the entire gallery `example/angular_components_example`. 

## Development

As of angular: 5.0.0-alpha+5 the pub transformer has been removed in favor of
code generation through package [build]. This package must be built with package
[build_runner].

### Build

Build the entire gallery from the `example/angular_components_example`
directory.

```
pub run build_runner build --output <output directory>
```

### Serve

Run a local development server with a file watcher and incremental rebuilds:

```
pub run build_runner serve web
```

__Known Issues:__

When building and viewing the gallery these issues are expected at this time:

 * Build Warnings:

   `Generator does not support multiple @GallerySectionConfig annotations in a
   single lib directory.`

 * Runtime Warning:

   `SEVERE: OverlayService must be a singleton: Check that there is no nested
   overlayBindings or popupBindings`

 * Loading deferred libraries is not yet supported when _dart2js_ is configured
   as the _build_web_compiler_.

[build_runner]: https://pub.dartlang.org/packages/build_runner
[build]: https://pub.dartlang.org/packages/build
