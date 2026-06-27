# auto_translate_text_widget

[![pub package](https://img.shields.io/pub/v/auto_translate_text_widget.svg)](https://pub.dev/packages/auto_translate_text_widget)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)

> Translate Flutter Text, AutoSizeText, RichText and Animated Text instantly with live language switching, caching, and Google Translator support.

A complete translation UI toolkit for Flutter. Translate any text widget at runtime without restart, without navigation refresh — just call `LanguageService.setLanguage()` and every translated widget updates instantly.

---

## ✨ Features

- ✅ **Live language switching** — no restart required
- ✅ **Global LanguageService** — `ValueNotifier`-based reactive updates
- ✅ **In-memory translation cache** — faster UI, fewer API calls
- ✅ **Google Translator integration** — powered by the `translator` package
- ✅ **Text widget** — `AutoTranslateText`
- ✅ **AutoSizeText** — `AutoTranslateAutoSizeText`
- ✅ **Typewriter animation** — `AutoTranslateTypewriterText`
- ✅ **RichText** — `AutoTranslateRichText` with per-span translation
- ✅ **Shimmer loading** — optional shimmer placeholders
- ✅ **SharedPreferences persistence** — remembers user language
- ✅ **Null-safe** — fully null-safe Dart
- ✅ **Cross-platform** — Android, iOS, Web, macOS, Windows, Linux

---

## 📦 Installation

Add to your `pubspec.yaml`:

```yaml
dependencies:
  auto_translate_text_widget: ^1.0.0
```

Then run:

```bash
flutter pub get
```

---

## 🚀 Quick Start

### Initialize

```dart
import 'package:auto_translate_text_widget/auto_translate_text_widget.dart';

void main() async {
  WidgetsFlutterBinding.ensureInitialized();
  await LanguageService.init();
  runApp(MyApp());
}
```

### Basic Text

```dart
AutoTranslateText(
  'Welcome to our application',
  style: TextStyle(fontSize: 18),
)
```

### AutoSizeText

```dart
AutoTranslateAutoSizeText(
  'This is a very long text',
  maxLines: 2,
)
```

### Typewriter Animation

```dart
AutoTranslateTypewriterText(
  'Welcome to Flutter',
  speed: Duration(milliseconds: 60),
)
```

### RichText

```dart
AutoTranslateRichText(
  spans: [
    TranslateSpan(
      text: 'Hello ',
      style: TextStyle(fontWeight: FontWeight.bold),
    ),
    TranslateSpan(
      text: 'World',
      style: TextStyle(color: Colors.blue),
    ),
  ],
)
```

### Switch Language

```dart
// All translation widgets update automatically!
await LanguageService.setLanguage('bn');
```

### Shimmer Loading

```dart
AutoTranslateText(
  'Hello',
  enableShimmer: true,
)
```

---

## 🏗 Architecture

```text
LanguageService (ValueNotifier)
        │
        ▼
AutoTranslate (Translation Helper)
        │
        ▼
TranslationCache (In-Memory)
        │
        ▼
GoogleTranslator (API)
        │
        ▼
Translated Widgets
```

---

## 📖 API Reference

### LanguageService

| Method | Description |
|---|---|
| `LanguageService.init()` | Initialize and load persisted language |
| `LanguageService.setLanguage(String code)` | Set language and persist |
| `LanguageService.getCurrentLanguage()` | Get current language code |
| `LanguageService.language` | ValueNotifier for reactive updates |

### AutoTranslate

| Method | Description |
|---|---|
| `AutoTranslate.translateText(String text, {String? to})` | Translate text, returns String |
| `AutoTranslate.translate(String text, {String? to})` | Translate text, returns TranslationModel |

### TranslationCache

| Method | Description |
|---|---|
| `TranslationCache.get(lang, text)` | Get cached translation |
| `TranslationCache.set(lang, text, translation)` | Cache a translation |
| `TranslationCache.clear()` | Clear all cache |
| `TranslationCache.clearForLanguage(lang)` | Clear cache for one language |

---

## 🌍 Supported Platforms

| Platform | Supported |
|---|---|
| Android | ✅ |
| iOS | ✅ |
| Web | ✅ |
| macOS | ✅ |
| Windows | ✅ |
| Linux | ✅ |

---

## 📄 License

MIT License. See [LICENSE](LICENSE) for details.

---

## Author

<a href="https://jubayer.starsoftplus.com">
  <img src="https://jubayer.starsoftplus.com/uploads/profile/logo_image-1779555521059-756864562.jpg" width="100" height="100" style="border-radius: 50%;">
</a>

Developed with ❤️ by Md Jubayer Hossain  
[GitHub Profile](https://github.com/jubayerhossain625) | [Portfolio](https://jubayer.starsoftplus.com)

## All Languages

```dart
static const Map<String, String> languages = {
  'af': 'Afrikaans',
  'sq': 'Albanian',
  'am': 'Amharic',
  'ar': 'Arabic',
  'hy': 'Armenian',
  'as': 'Assamese',
  'ay': 'Aymara',
  'az': 'Azerbaijani',
  'bm': 'Bambara',
  'eu': 'Basque',
  'be': 'Belarusian',
  'bn': 'Bengali',
  'bho': 'Bhojpuri',
  'bs': 'Bosnian',
  'bg': 'Bulgarian',
  'ca': 'Catalan',
  'ceb': 'Cebuano',
  'zh-cn': 'Chinese (Simplified)',
  'zh-tw': 'Chinese (Traditional)',
  'co': 'Corsican',
  'hr': 'Croatian',
  'cs': 'Czech',
  'da': 'Danish',
  'dv': 'Dhivehi',
  'doi': 'Dogri',
  'nl': 'Dutch',
  'en': 'English',
  'eo': 'Esperanto',
  'et': 'Estonian',
  'ee': 'Ewe',
  'fil': 'Filipino',
  'fi': 'Finnish',
  'fr': 'French',
  'fy': 'Frisian',
  'gl': 'Galician',
  'ka': 'Georgian',
  'de': 'German',
  'el': 'Greek',
  'gn': 'Guarani',
  'gu': 'Gujarati',
  'ht': 'Haitian Creole',
  'ha': 'Hausa',
  'haw': 'Hawaiian',
  'he': 'Hebrew',
  'hi': 'Hindi',
  'hmn': 'Hmong',
  'hu': 'Hungarian',
  'is': 'Icelandic',
  'ig': 'Igbo',
  'ilo': 'Ilocano',
  'id': 'Indonesian',
  'ga': 'Irish',
  'it': 'Italian',
  'ja': 'Japanese',
  'jv': 'Javanese',
  'kn': 'Kannada',
  'kk': 'Kazakh',
  'km': 'Khmer',
  'rw': 'Kinyarwanda',
  'gom': 'Konkani',
  'ko': 'Korean',
  'kri': 'Krio',
  'ku': 'Kurdish (Kurmanji)',
  'ckb': 'Kurdish (Sorani)',
  'ky': 'Kyrgyz',
  'lo': 'Lao',
  'la': 'Latin',
  'lv': 'Latvian',
  'ln': 'Lingala',
  'lt': 'Lithuanian',
  'lg': 'Luganda',
  'lb': 'Luxembourgish',
  'mk': 'Macedonian',
  'mai': 'Maithili',
  'mg': 'Malagasy',
  'ms': 'Malay',
  'ml': 'Malayalam',
  'mt': 'Maltese',
  'mi': 'Maori',
  'mr': 'Marathi',
  'mni-mtei': 'Meiteilon (Manipuri)',
  'lus': 'Mizo',
  'mn': 'Mongolian',
  'my': 'Myanmar (Burmese)',
  'ne': 'Nepali',
  'no': 'Norwegian',
  'ny': 'Nyanja',
  'or': 'Odia',
  'om': 'Oromo',
  'ps': 'Pashto',
  'fa': 'Persian',
  'pl': 'Polish',
  'pt': 'Portuguese',
  'pa': 'Punjabi',
  'qu': 'Quechua',
  'ro': 'Romanian',
  'ru': 'Russian',
  'sm': 'Samoan',
  'sa': 'Sanskrit',
  'gd': 'Scots Gaelic',
  'nso': 'Sepedi',
  'sr': 'Serbian',
  'st': 'Sesotho',
  'sn': 'Shona',
  'sd': 'Sindhi',
  'si': 'Sinhala',
  'sk': 'Slovak',
  'sl': 'Slovenian',
  'so': 'Somali',
  'es': 'Spanish',
  'su': 'Sundanese',
  'sw': 'Swahili',
  'sv': 'Swedish',
  'tg': 'Tajik',
  'ta': 'Tamil',
  'tt': 'Tatar',
  'te': 'Telugu',
  'th': 'Thai',
  'ti': 'Tigrinya',
  'ts': 'Tsonga',
  'tr': 'Turkish',
  'tk': 'Turkmen',
  'ak': 'Twi',
  'uk': 'Ukrainian',
  'ur': 'Urdu',
  'ug': 'Uyghur',
  'uz': 'Uzbek',
  'vi': 'Vietnamese',
  'cy': 'Welsh',
  'xh': 'Xhosa',
  'yi': 'Yiddish',
  'yo': 'Yoruba',
  'zu': 'Zulu',
};
```
