[![Pub Version](https://img.shields.io/pub/v/dart_code_metrics_presets?logo=dart&logoColor=white)](https://pub.dev/packages/dart_code_metrics_presets/)
[![License](https://img.shields.io/github/license/CQLabs/dart-code-metrics-presets)](https://github.com/CQLabs/dart-code-metrics-presets/blob/main/LICENSE)
[![package publisher](https://img.shields.io/pub/publisher/dart_code_metrics.svg)](https://pub.dev/packages/dart_code_metrics/publisher)

# DCM Presets

DCM is a static analysis tool that helps you analyse and improve your code quality. You can find all available lint rules [here](https://dcm.dev/docs/individuals/rules).

This repository contains a list of predefined presets for DCM:

- **All:** contains all available lint rules for Dart and Flutter.
- **Teams:**: contains all lint rules available only for the Teams version.
- **Dart:** contains all lint rules applicable to any Dart app.
- **Flutter:** contains all lint rules applicable to any Flutter app.
- **Flame:** contains all lint rules for the Flame package.
- **Intl:** contains all lint rules for the Intl package.
- **Bloc:** contains all lint rules for the Bloc package.
- **Equatable:** contains all lint rules for the Equatable package.
- **Pub:** contains all lint rules for linting the `pubspec.yaml` files.

## How to use a preset

Take these steps to enable a preset:

1. Install this package as a dev dependency:

   ```terminal
   dart pub add --dev dart_code_metrics_presets
   ```

   or:

   ```terminal
   flutter pub add --dev dart_code_metrics_presets
   ```

2. For DCM configuration add the `extents` entry:

   ```yaml
   dart_code_metrics:
     extends:
       - package:dart_code_metrics_presets/all.yaml
   ```

## Disabling or reconfiguring a rule from the preset

To disable a rule, simply set its value to false:

```yaml
dart_code_metrics:
  extends:
    - package:dart_code_metrics_presets/all.yaml
  rules:
    - avoid-banned-imports: false
```

To reconfigure a rule, that is included into a preset:

```yaml
dart_code_metrics:
  extends:
    - package:dart_code_metrics_presets/all.yaml
  rules:
    - arguments-ordering:
        child-last: true
```

## Defining a custom preset

Any other preset can be passed to the `extends` entry. To create a custom preset create a `yaml` file with the same structure as for regular [DCM configuration](https://dcm.dev/docs/individuals/configuration/).
