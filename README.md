# deepseek-builder

DeepSeek builder — tooling for building/searching pipelines

---

## 🎤 Voice-Enabled Multilingual DeepSeek

Now with **dual text + voice output** in 100+ languages, with Chinese accent on all languages (since she's Chinese).

### Features

✅ **Multilingual Auto-Detection** — Detects any language input automatically (Spanish, English, French, German, Portuguese, Chinese, etc.)  
✅ **Dual Output** — Text printed to console + file, voice spoken simultaneously  
✅ **Native Accents** — Each language has native voice profiles (Castilian Spanish, American/British English, etc.)  
✅ **Chinese Accent on All Languages** — DeepSeek speaks every language with her native Chinese accent  
✅ **Dynamic Language Packs** — Loads language support on-the-fly, no predefined limits  
✅ **100+ Language Support** — Via Google Cloud TTS or offline pyttsx3  

### Installation

```bash
# Install voice module dependencies
pip install langdetect google-cloud-texttospeech pyttsx3

# OR just use offline (pyttsx3 only):
pip install pyttsx3 langdetect
```

### Quick Start

```python
from voice_module import UniversalVoiceEngine

# Create engine with Chinese accent
engine = UniversalVoiceEngine(
    native_accent="zh",  # Chinese accent
    auto_detect=True,    # Auto-detect language
    voice_enabled=True,
    output_file="deepseek_output.log"
)

# Speak in any language — auto-detected, spoken with Chinese accent
engine.speak_and_print("¡Hola mundo!")  # Spanish + Chinese accent
engine.speak_and_print("Hello world!")  # English + Chinese accent
engine.speak_and_print("你好世界!")      # Chinese + Chinese accent
```

### API

#### `UniversalVoiceEngine`

```python
engine = UniversalVoiceEngine(
    use_google_tts=True,                        # Use Google Cloud (100+ langs) vs pyttsx3
    output_file="deepseek.log",                 # Log transcripts
    voice_enabled=True,                         # Enable voice
    auto_detect=True,                           # Auto-detect language
    native_accent="zh",                         # Native accent (e.g., "zh" for Chinese)
    apply_native_accent_on_other_languages=True # Apply accent to all languages
)

# Speak with auto-detected language + Chinese accent
engine.speak_and_print("Hola mundo")

# Toggle voice on/off
engine.toggle_voice(False)

# Toggle native accent on/off
engine.toggle_native_accent(True)

# Change native accent
engine.set_native_accent("es")  # Spanish accent

# Manually set language
engine.set_language("pt")  # Portuguese

# List available accent profiles
engine.list_accents()
```

### Supported Languages & Accents

**Natively Supported:**
- Spanish (Castilian, Mexican)
- English (American, British, Australian)
- French (France, Canadian)
- German
- Portuguese (Brazilian, Portugal)
- Mandarin Chinese

**Auto-Detected (100+):**
- Japanese, Korean, Italian, Russian, Arabic, Hindi, Dutch, Polish, Turkish, Vietnamese, Thai, Indonesian, Finnish, Swedish, Norwegian, Danish, Czech, Hungarian, Romanian, Greek, Ukrainian, Hebrew, Filipino, and more

### Text Logging

All spoken output is logged to file with timestamps and accent info:

```
🎤 [Spanish] ¡Hola mundo! (with ZH accent)
🎤 [English] Hello world! (with ZH accent)
🎤 [Chinese] 你好世界! (with ZH accent)
```

### Environment

Google Cloud TTS requires authentication:

```bash
export GOOGLE_APPLICATION_CREDENTIALS="/path/to/service-account-key.json"
```

Or use offline pyttsx3 (no API key needed).

---

## 😄 Dad Joke

Why did the developer go broke?
Because he used up all his cache!

---

**Built for multilinguals who want DeepSeek to actually speak. 🗣️**
