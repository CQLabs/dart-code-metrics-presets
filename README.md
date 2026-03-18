[![Pub Version](https://img.shields.io/pub/v/dart_code_metrics_presets?logo=dart&logoColor=white)](https://pub.dev/packages/dart_code_metrics_presets/)
[![License](https://img.shields.io/github/license/CQLabs/dart-code-metrics-presets)](https://github.com/CQLabs/dart-code-metrics-presets/blob/main/LICENSE)
[![package publisher](https://img.shields.io/pub/publisher/dart_code_metrics.svg)](https://pub.dev/packages/dart_code_metrics/publisher)

# DCM Presets

DCM is an advanced linter for Dart and Flutter that helps you analyze and improve your code quality. You can find all available lint rules [here](https://dcm.dev/docs/rules/).

This repository contains a list of predefined DCM presets for lints:

- **All:** contains all available lint rules for Dart and Flutter.
- **Recommended:** contains recommended Dart and Flutter rules (with an emphasis on finding errors).
- **Dart:** contains all lint rules applicable to any Dart app.
- **Flutter:** contains all lint rules applicable to any Flutter app.
- **Pub:** contains all lint rules for linting the `pubspec.yaml` files.
- **Flame:** contains all lint rules for the [Flame package](https://pub.dev/packages/flame).
- **Provider:** contains all lint rules for the [Provider package](https://pub.dev/packages/provider).
- **Bloc:** contains all lint rules for the [Bloc package](https://pub.dev/packages/bloc).
- **Riverpod:** contains all lint rules for the [Riverpod package](https://pub.dev/packages/riverpod).
- **Equatable:** contains all lint rules for the [Equatable package](https://pub.dev/packages/equatable).
- **Patrol:** contains all lint rules for the [Patrol package](https://pub.dev/packages/patrol).
- **FakeAsync:** contains all lint rules for the [FakeAsync package](https://pub.dev/packages/fake_async).
- **Mocktail:** contains all lint rules for the [Mocktail package](https://pub.dev/packages/mocktail).
- **GetIt:** contains all lint rules for the [GetIt package](https://pub.dev/packages/get_it).
- **FlutterHooks:** contains all lint rules for the [FlutterHooks package](https://pub.dev/packages/flutter_hooks).
- **FirebaseAnalytics:** contains all lint rules for the [FirebaseAnalytics package](https://pub.dev/packages/firebase_analytics).
- **GetX:** contains all lint rules for the [GetX package](https://pub.dev/packages/get).
- **Intl:** contains all lint rules for the [Intl package](https://pub.dev/packages/intl).
- **EasyLocalization:** contains all lint rules for the [EasyLocalization package](https://pub.dev/packages/easy_localization).

and for metrics:

- **All Metrics**: contains all available metrics with recommended default thresholds.
- **Recommended metrics:** contains recommended metrics with default thresholds.

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

Any other preset can be passed to the `extends` entry. To create a custom preset create a `yaml` file with the same structure as for regular [DCM configuration](https://dcm.dev/docs/configuration/).
