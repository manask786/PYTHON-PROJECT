# PYTHON-PROJECT
from translate import Translator
from gtts import gTTS
import os

def translate_text(text, target_language):
    translator = Translator(to_lang=target_language)
    translation = translator.translate(text)
    return translation

def text_to_speech(text, output_file):
    tts = gTTS(text, lang='en')  # You can specify the language here
    tts.save(output_file)
    os.system(f"start {output_file}")  # This will play the saved audio file on Windows. You can change this for other platforms.

def main():
    print("1. Translate text")
    print("2. Text to speech")
    choice = input("Enter 1 or 2: ")

    if choice == '1':
        text = input("Enter the text to translate: ")
        target_language = input("Enter the target language: ")
        translated_text = translate_text(text, target_language)
        print(f"Translated text: {translated_text}")
    elif choice == '2':
        text = input("Enter the text for text-to-speech: ")
        output_file = "output.mp3"
        text_to_speech(text, output_file)
        print(" Playing the audio.")
    else:
        print("Invalid choice.")

if _name_ == "_main_":
    main()
